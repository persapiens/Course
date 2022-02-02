

# Containers

## 📒 Online Exercise: Understanding Containers

↳ Click the following to start the exercise.

<a href="https://devops.docable.cloud/chrisparnin/v/61fa97d5b405b677b416a7c5">
<img src="imgs/containers-notebook-preview.png">
</a>

## Intermission: Images demo...

live class demo.

## Introducing Docker containers.

If we worked on our script for several more years and took advantage of other capabilities of the Linux kernel, such as cgroups and namespaces, we could overcome many of the limitations we saw with our homegrown containers. Thankfully, someone has done this work for us.

### Setup 

#### Create a headless VM

Pull an ubuntu focal image and create a VM called, `docker-vm`.

```bash
bakerx pull focal cloud-images.ubuntu.com
bakerx run docker-vm focal
```

```bash
vm pull ubuntu:focal
vm run docker-vm ubuntu:focal
```

#### Install docker inside your VM.

📹 **Watch**: [Video demo of these steps](https://www.youtube.com/embed/xSXXUJYNrxg), then try to complete these steps on your own:

The recommended method for installing docker on ubuntu can be [found here](https://docs.docker.com/install/linux/docker-ee/ubuntu/#install-docker-ee-1).  But in the interest of time: 😬

```
curl -sSL https://get.docker.com/ | sh
```

After installation, it is recommended you allow docker to be run without needing sudo. **IMPORTANT** You'd need to restart your shell (exit and log back in) to see the changes reflected.

```
sudo usermod -aG docker $(whoami)
```

Verify you can run docker:
```
docker run hello-world
```

### Playing with Docker

Pull an ubuntu image.

```
$ docker pull ubuntu:18.04
```

Check the size of the images.

```bash
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ubuntu              18.04               ccc6e87d482b        6 days ago          64.2MB
hello-world         latest              fce289e99eb9        12 months ago       1.84kB
```

Let's create a simple container.

```bash
docker run ubuntu:18.04 sh
```

Unfortunately, that doesn't quite do what we want, because a pseudo-tty allocated to the container, so we can use the terminal.

```
$ docker run -t ubuntu:18.04 sh
# ls

exit
.exit
^C
```

Unfortunately, that's still not enough. Docker isn't necessarily the most intuitive system, you see. You also need to allow input (`-i` Keep STDIN open even if not attached).

```
$ docker run -it ubuntu:18.04 sh
```

Finally, we can get to a terminal, and see we can run shell commands in our own private snapshot of the ubuntu image.


```bash
$ docker run -it ubuntu:18.04 sh
# ls
# rm -rf --no-preserve-root /
# exit
```

Oh no, what have we done? Is everything okay?

```bash
$ docker run -it ubuntu:18.04 sh
```



### Building Images

We can create our own images.
Create a "Dockerfile" and place this content inside:

```
FROM ubuntu:18.04

RUN apt-get -y update

# update packages and install
RUN apt-get install -y openjdk-11-jre-headless wget curl unzip

RUN apt-get -y install git
RUN apt-get -y install maven

ENV JAVA_HOME /usr/lib/jvm/java-11-openjdk-amd64
```

Build the docker image, and name it "java11".

```bash
docker build -t java11 .
```

We can see our image listed, now:

```bash
docker images
```

Now, let's use it to run `mvn` to check our environment setup.

```bash
docker run java11 mvn --version
```

### Understanding containers

Look at all the containers you've created by running commands above.

```
docker ps -a 
```

The container "graveyard" contains all the dead containers that ran a process, then exited.
If we want a container to stick around, we need it to run in daemon mode, but adding the `-d` arg. We also provide a name for easy reference.

```
docker run --name test-d -it -d ubuntu:18.04
```

Let's use an one-liner to write a file to our running container.

```bash
docker exec -it test-d script /dev/null -c "echo 'Hello' > foo.txt"
```

Make sure we can see change. Note we add `-t` to improve the output of `ls`:

```bash
docker exec -t test-d ls
```

Now, let's commit this to our image. Any new container will now have 'foo.txt' inside it.

```bash
docker commit test-d ubuntu:18.04
```

We can confirm that new containers do indeed have 'foo.txt' inside:

```bash
$ docker run -t ubuntu:18.04 ls
bin   dev  foo.txt  lib    media  opt	root  sbin  sys  usr
boot  etc  home     lib64  mnt	  proc	run   srv   tmp  var
```

### Volumes

Imagine you wanted to create a simple build script and run against an image. It could be incredible tedious to create a new image per project, just to add the build script. Furthermore, getting data *out* of a container could be unwieldy. Alternatively, we can use volumes, to share our filesystem of our host with a container.

```
docker run -v /home/vagrant/:/vol java11 ls -a /vol/
```

We should be able to see our host's directory home directory. Now, we can have a simple "escape hatch" to get data in and out of the container at the cost of losing true immutability. 

### Build script demo

In your host VM, create 'build.sh' and place the following inside:

```bash
git clone https://github.com/CSC-326/JSPDemo
cd JSPDemo
mvn compile -DskipTests -Dmaven.javadoc.skip=true
```

```
chmod +x build.sh
docker run -v /home/vagrant/:/vol java11 sh -c /vol/build.sh
```

We can confirm the code is greatly out of date and does not work with Java 11!
```
[INFO] 31 errors 
[INFO] -------------------------------------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  29.052 s
[INFO] Finished at: 2020-01-22T22:06:57Z
[INFO] ------------------------------------------------------------------------
```

```bash | {type:'repl'}
```

### Reviewing principles

Recall we want to maintain efficiency and isolation. Here is how Docker enables this.

![docker-vs-vm](imgs/docker-vs-vm.png)

##### Images

* A docker image contains a set of layers, which can be composed for efficient storage on the system.
* An image can be based on other images (`FROM ubuntu:18.04`).
* You can build your own images by running commands inside a Dockerfile. 
* A base image is usually created with hand-crafted rootfs (`FROM scratch` ... `COPY /rootfs /`).
* More advanced ways to build images, include using the [Builder pattern](https://matthiasnoback.nl/2017/04/docker-build-patterns/), for multi-staged builds.

##### Containers

* A container contains an overlay of the image's rootfs.
* Containers are generally stateless, that is any change to a container has no effect on its image; however, you can commit a change to a new image.
* A docker container only stays alive as long as there is an active process being run in it. You can keep a long running container by running a process that does not exist (a server), or running in daemon mode (`-d`).
* A container cannot generally access other processes, the host filesystem, or other resources. The entry point is PID 1. 
* While greatly useful, running programs inside containers can result in many different quirky behavior.
