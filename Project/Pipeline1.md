# Pipeline > Build

For this milestone and project, you will work in teams of 3 people.

## General Tasks

* Automatically configure a build server with jenkins and ansible.
* Automatically configure a build environment for a node web application (checkbox.io).
* Create a build job.

### 🎛️ Automatically configure a jenkins server

Install jenkins on the build server using ansible. During this phase, you must overcome several challenges of automation, such as turning off jenkins setup wizard, handling authentication, configuring the server, and installing any needed jenkin plugins.

Next, create a node.js project to act as a driver for provisioning and running tasks inside your build server from a host machine.

You must provide the following two commands:

```
# Configure jenkins and build environment
$ pipeline setup
# This command should copy a .vault-pass file, with the password "csc-devops-2020" from the host to VM home directory. The .vault-pass file should be excluded from source control_. 

# Trigger a build job (named checkbox.io), wait for output, and print build log.
$ pipeline build checkbox.io -u <admin> -p <admin>

```

**CM-Template**: Please clone and extend the following template for ensuring a uniform environment running projects across the class:
https://github.com/CSC-DevOps/CM-Template

For triggering the build job and retrieving the build log, you may consider using the [jenkins](https://www.npmjs.com/package/jenkins) npm package or using curl with the [remote api](https://wiki.jenkins.io/display/JENKINS/Remote+access+API).

##### Constraints

* Use bakerx as local provisioner for your VM (named "config-srv"). Keep ansible and jenkins on the same VM.
* Assign static ip address 192.168.33.20 for your VM. 
* Use ansible for configuration. No credit given for use of ansible galaxy roles.
* Run jenkins server on port 9000.
* Use `admin:admin` as username and password for jenkins
* Install jenkins-plugins needed to use Pipelines style build jobs.

### 🛠️Automatically configure a build environment (checkbox.io)

Create a build environment for [checkbox.io](https://github.com/chrisparnin/checkbox.io), a nodejs web application.

> checkbox.io is a site for hosting simple surveys created in markdown. 

The production site has dependencies on nginx, node, monogodb, and additional environmental variable dependencies. However, the build environment will only need a subset of these.

* Install mongodb and nodejs.
* Create mongo user with password and `readWrite` role.
* Define `APP_PORT=3002`,`MONGO_PORT=27017`, `MONGO_USER=<user>`, `MONGO_PASSWORD=<pass>`, and `MONGO_IP=localhost`.

##### Constraints:

* Configure the environment to run on the same build server.
* You are free to construct the build environment for checkbox.io with any technology/tools, as long as it is done automatically.


### 📋Create a build job for jenkins.

The build job should perform the following build steps.

* Clone/checkout https://github.com/chrisparnin/checkbox.io
* Install npm modules.
* Start mongodb (if not already running as service).
* Start `server-side/site/server.js`.
* Successfully pass `npm test` (as provided in server-side/site/package.json)

##### Constraints:

* Use a pipeline style build job.
* You cannot manually create the build job in Jenkins. You may consider using [jenkins-job-builder](https://docs.openstack.org/infra/jenkins-job-builder/) to as a tool for adding/updating the build job in Jenkins.

## Team responsibilities

### 👥 Task leaders 

Each major task should have a team member responsible for implementing the majority of the assigned task.

Use your GitHub Project Board (e.g. Milestone1) to help coordinate and assign tasks.

![Project Board](https://miro.medium.com/max/4976/1*_St3BrB36V05JAuFIC3utQ.png)

_Points will be deducted for non-contributing members, including receiving zero credit._

### Checkpoint and milestone report.

##### Checkpoint

There will be checkpoints where you will be required to report interim progress (CHECKPOINT.md).

* Checkpoint 1 due: March 9th

Document your current progress and team contributions. Note work you have completed and what work will be done next. You may find it useful to take screenshots of your GitHub Projects.

_Points will be deducted for teams not making steady progress throughout the milestone._

##### Milestone report

As you learn how to setup configuration management for this project, document the experiences you have in learning about setting up the system and the issues you had in replicating this process automatically.

This can be described in your submission's README.md.

## Evaluation

* Automatically configure a jenkins server. (40%)
* Automatically configure a build environment. (20%)
* Create a build job. (20%)
* Checkpoint and milestone report. (10%)
* Screencast. (10%)

Points may be deducted for not following constraints, poor quality of implementation, poor task communication and delegation, or failing to include sufficient detail required to evaluate capabilities.

_Points will be deducted for non-contributing members, including receiving zero credit._

## Submission

Commit your all your work related to your project into your designated repository in the master branch before the final deadline. 

When you have finished the submission, create a branch called `M1` to hold a snapshot of your work related to this milestone.

Ensure your repository contains:

* a top-level node.js project supporting the required commands for running your build server.
* a README.md, with your report details.
* a CHECKPOINT.md, with your two checkpoint reports.
* a link to screencast that demostrates each task.

**Due Thursday, March 18nd, before midnight.**
