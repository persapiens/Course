# Advanced Docker

We cover deployment, composing, and linking containers, and the ambassador pattern.


### Deploy

This example shows you how to create deploy a nodejs container to a private repository. 
A server can pull from the private repostory and get the latest code.

##### Registery

Start a private registery on port 5000.

```
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

More information about setting up a [TLS-secured registery](https://docs.docker.com/registry/deploying/), which is remotely accessible.

##### Node App and Dockerfile

Can get app from `git clone https://github.com/CSC-DevOps/App.git`

Note how Dockerfile uses "COPY" command to place contents from local filesystem into container.

```
FROM    centos:centos6

# Enable EPEL for Node.js
RUN     rpm -Uvh http://download.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
# Install Node.js and npm
RUN     yum install -y npm

# Bundle app source
COPY . /src
# Install app dependencies
RUN cd /src; npm install

EXPOSE  8080
CMD ["node", "/src/main.js", "8080"]
```

##### Build and test 

Build a container for a node js app.

```
cd App
docker build -t ncsu-app .
docker run -p 50100:8080 -d --name app
docker logs <containerid>
```

##### Deploy to registry

If successful, can deploy to a private registery.

```
docker tag ncsu-app localhost:5000/ncsu:latest
docker push localhost:5000/ncsu:latest
```

##### Server update script

A script like this can run after a git hook or deploy command. The server will pull from registery, stop existing app container and run new instance.

```
docker pull localhost:5000/ncsu:latest  
docker stop app  
docker rm app
docker rmi localhost:5000/ncsu:current  
docker tag localhost:5000/ncsu:latest localhost:5000/ncsu:current
docker run -p 50100:8080 -d --name app localhost:5000/ncsu:latest  
```

##### Test

`curl -i localhost:50100`

### Linking.

Containers can be [linked to each other](https://docs.docker.com/userguide/dockerlinks/). This allows a secure and private channel of communication between containers on the same host.


### Patterns and Tools

* **Ambassador pattern**: Pattern that allows containers to communicate with other containers on different hosts. Essentially works using a reverse-proxy. [See](https://docs.docker.com/articles/ambassador_pattern_linking/).
* **socat**: Tool for mapping sockets to files or other networking ports. Useful for connecting services and linking file systems to other containers.

Example of using an ambassador container:

```
docker build -t svendowideit/ambassador .
docker run -t -i -link redis:redis -name redis_ambassador -p 6379:6379 svendowideit/ambassador
```

Dockerfile
```
FROM	alpine:3.2
MAINTAINER	SvenDowideit@home.org.au

RUN apk update && \
	apk add socat && \
	rm -r /var/cache/

CMD	env | grep _TCP= | sed 's/.*_PORT_\([0-9]*\)_TCP=tcp:\/\/\(.*\):\(.*\)/socat -t 100000000 TCP4-LISTEN:\1,fork,reuseaddr TCP4:\2:\3 \& wait/' | sh
```

### Orchestration

There are several tools that help assist in combining several containers under one configuration scheme.

* http://decking.io/
* fig
* Docker Compose

Other tools work on a larger scale, such as http://kubernetes.io/

### Other

Cleanup

`docker images -q --filter "dangling=true" | xargs docker rmi`

