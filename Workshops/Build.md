# Build Server

The goal of this workshop is to create a simple build server.
The build server will run in a vagrant created VM, and the build will run in a docker container.  The following is a [good resource](https://serversforhackers.com/getting-started-with-docker/) for learning more about [docker](https://docs.docker.com/reference/commandline/cli/).

## VM

Create a VM to host your build server.  Note, it must be a 64 bit image, otherwise docker will not be supported!

    vagrant init hashicorp/precise64

## Preparing machine for docker

install the backported kernel

    sudo apt-get update
    sudo apt-get -y install linux-image-generic-lts-raring linux-headers-generic-lts-raring

reboot

    sudo reboot

Add the repository to your APT sources

    sudo sh -c "echo deb https://get.docker.com/ubuntu docker main > /etc/apt/sources.list.d/docker.list"

Then import the repository key

    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 36A1D7869245C8950F966E92D8576A8BA88D21E9

Install docker

    sudo apt-get update
    sudo apt-get install -y lxc-docker

Install some basics    
   
    sudo apt-get -y install git vim


### Creating docker image

Build a docker environment for running build.  Create a "Dockerfile" and place this content inside:

    FROM ubuntu:13.10
    MAINTAINER Chris Parnin, chris.parnin@ncsu.edu
    
    RUN echo "deb http://archive.ubuntu.com/ubuntu saucy main universe" > /etc/apt/sources.list
    RUN apt-get -y update && apt-get -y upgrade
    RUN apt-get install -y wget openjdk-7-jdk curl unzip

    RUN apt-get -y install git
    RUN apt-get -y install maven
    RUN apt-get -y install libblas*
    RUN ldconfig /usr/local/cuda/lib64
    
    ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

Build the docker image

    sudo docker build -t ncsu/buildserver .
    
Test your image

    sudo docker images
    sudo docker run -it ncsu/buildserver mvn --version

### Playing around in Docker

Run an interactive terminal.

    sudo docker run -it ncsu/buildserver

Inside docker

    ls
    sudo rm -rf --no-preserve-root /
    exit
    
Check if its still there.

    sudo docker run -it ncsu/buildserver

##### Containers

Look at all the containers you've created by running commands above.

    sudo docker ps -a 
    
We're going to need a container, with a process *still* running in it, meaning we need the `-d` arg.

    sudo docker run -it -d ncsu/buildserver

This will show you last container id created.    

    sudo docker ps -l

Let's take last container, and update it.

    sudo docker exec -it 674183b76a10 script /dev/null -c "echo 'Hello' > foo.txt"

Make sure we can see change:

    docker exec -it 674183b76a10 ls

Now, let's commit this to our image.

    docker commit 674183b76a10 ncsu/buildserver

**Now, any new container created from this image will have the new chanage.**

### Building

In your host VM, create 'build.sh' and place the following inside: 

    git clone https://github.com/SkymindIO/nd4j
    cd nd4j
    mvn clean install -DskipTests -Dmaven.javadoc.skip=true

Execute script

    chmod +x build.sh
    sudo docker run -v /home/vagrant/:/vol ncsu/buildserver sh -c /vol/build.sh
    
### Server

Install node (on your VM).

```
curl https://raw.githubusercontent.com/creationix/nvm/v0.16.1/install.sh | sh
source ~/.profile
nvm ls-remote
nvm install v0.11.13
nvm use 0.11.13
```

Extend server to run build when a http request is made.

```
var exec = require('child_process').exec;
var cmd = 'YOUR docker command';

exec(cmd, function(error, stdout, stderr) {
  // command output is in stdout
});
```
