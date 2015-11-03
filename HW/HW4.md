# Homework 4 - Advanced Docker

In this homework assignment, you'll get to practice several common architectural patterns for dealing with multiple docker containers.

1) **File IO**: You want to create a container for a legacy application. You succeed, but you need access to a file that the legacy app creates.

* Create a container that runs a command that outputs to a file.
* Use socat to map file access to read file container and expose over port 9001 (hint can use SYSTEM + cat).
* Use a linked container that access that file over network.

2) **Ambassador pattern**: Implement the remote ambassador pattern to encapsulate access to a redis container by a container on a different host.

* Use Docker Compose to configure containers.
* Use two different VMs to isolate the docker hosts. VMs can be from vagrant, DO, etc.
* The client should just be performing a simple "set/get" request.
* In total, there should be 4 containers.

3) **Docker Deploy**: Extend the deployment workshop to run a docker deployment process.

* A commit will build a new docker image.
* Push to local registery.
* Deploy the dockerized [simple node.js App](https://github.com/CSC-DevOps/App) to blue or green slice.
* Add appropriate hook commands to pull from registery, stop, and restart containers.

### Evaluation

* File IO (20%)
* Ambassador pattern (40%)
* Docker Deploy (40%)

### Submission

[Submit a README.md](https://docs.google.com/a/ncsu.edu/forms/d/1oioay5bF5Le7PpuH1VAzxHCSNsOdkTvEqfrymHI1wjk/viewform?usp=send_form#start=invite) with a screencast (or .gif) for each component. Include code/scripts/configuration files in repo.

Assignment is due, Wednesday, November 18th midnight
