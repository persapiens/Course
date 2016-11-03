# HW4 - Docker Part Deux

In this homework assignment, you'll get to practice advanced features related to docker containers.

1) **Docker Compose (50 points)**: You are ready to launch your cat photo startup company. Use docker compose to setup your HW3 app in the following way:

* Setup a container for redis.
* Setup a container for proxy.
* Setup a container for node app.
* Modify infrastructure.js to spawn new containers instead of new servers.

2) **Docker Deploy (50 points)**: Extend the deployment workshop to run a docker deployment process.

* On post-receive will build a new docker image.
* Push to local registery.
* Deploy the dockerized [simple node.js App](https://github.com/CSC-DevOps/App). Add appropriate hook commands to pull from registery, stop, and restart containers.


3) **File IO (Bonus 20 points)**: You want to create a container for a legacy application. You succeed, but you need access to a file that the legacy app creates.

* Create a container that runs a command that outputs to a file.
* Use socat to map file access to read file container and expose over port 9001 (hint can use SYSTEM + cat).
* Use a linked container that access that file over network. The linked container can just use a command such as curl to access data from other container.

## Submission

Submit your [repo link](https://goo.gl/forms/JuDfdY9X9JEqMe7f1).

* README.md (explaning implementation),
* Docker compose file
* Relevant code, hook scripts, etc.
* Screencast demonstrating docker compose, docker deploy, and bonus.

Due, Thursday, November 17th, midnight.
