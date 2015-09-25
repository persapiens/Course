# Build Server

The goal of this workshop is to create a simple build server.
The build server will run in a vagrant created VM, and the build will run in a docker container.  The following is a [good resource](https://serversforhackers.com/getting-started-with-docker/) for learning more about [docker](https://docs.docker.com/reference/commandline/cli/).

## VM

If you have a USB with a box image, copy to the following folder.

* Mac OS x: ~/.vagrant.d/boxes
* Windows: C:/Users/USERNAME/.vagrant.d/boxes

Create a VM to host your build server.  Note, it must be a 64 bit image, otherwise docker will not be supported!

    vagrant init ubuntu/trusty64


### Install docker

Use one of this options:

* curl -sSL https://get.docker.com/ | sh

### Creating docker image

Build a docker environment for running build.  Create a "Dockerfile" and place this content inside:

    FROM ubuntu:14.04
    MAINTAINER Chris Parnin, chris.parnin@ncsu.edu
        
    RUN apt-get -y update
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
    mvn compile -DskipTests -Dmaven.javadoc.skip=true

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

A simple http server in node:

```
//Lets require/import the HTTP module
var http = require('http');

//Lets define a port we want to listen to
const PORT=8080;

//We need a function which handles requests and send response
function handleRequest(request, response){
    response.end('Building: ' + request.url);
}

//Create a server
var server = http.createServer(handleRequest);

//Lets start our server
server.listen(PORT, function(){
    //Callback triggered when server is successfully listening. Hurray!
    console.log("Server listening on: http://localhost:%s", PORT);
});
```


Extend server to run build when a http request is made.

```
var exec = require('child_process').exec;
var cmd = 'YOUR docker command';

function handleRequest(request, response)
{
	console.log("Request received");

	var child = exec(cmd, {maxBuffer: 1024 * 5000}, function(error, stdout, stderr) 
	{
		if( error )
      	    console.log(error)
	});

	// Stream results
	child.stdout.pipe( response );
	child.stderr.pipe( process.stderr );

	child.on('exit', function()
	{
   	    console.log('built');
   	    return true;
	});
}
```

Update your VM to have a private network, visit http://192.168.33.10:8080, and trigger a build.

# Errors

For older kernels, you may need to do the following:

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

