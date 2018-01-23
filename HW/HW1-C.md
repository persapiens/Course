## HW1 - Configuration Management

Automatically configuring a computational resource will be one of the most important skills for you to master in your career.  You have gained experience using [ansible](http://docs.ansible.com/) to automatically setup tasks on a virtual machine.

### Creating a selenium testing server.

In this homework assignment, you will create two servers, A) One server runing a simple Java Spring Application, and B) Another server capable of executing a selenium test.

##### CoffeeMaker

[CoffeeMaker](https://github.ncsu.edu/engr-csc326-staff/Onboarding) is a simple spring/hibernate/mysql application with an angular js front-end.

* Create configuration management for CoffeeMaker.
* Run CofffeeMaker in a local VM.

##### Create a simple selenium testing server

A simple maven project with selenium tests can be found [here](https://github.com/CSC-326/Onboarding-Selenium). Running `mvn test` should result in three passing tests.

* Create configuration management for Onboarding-Selenium test project.
* Ensure you can test CoffeeMaker by modifying code to a) use environment variable for ip address, or b) use [port forwarding](https://gist.github.com/scy/6781836) to forward localhost:8080 => 192.168.8.8:8080

## Assignment constraints

Abide by the following constraints:
  - Use best practices (use modules to do work, avoid shell/commands, be idempotent, use roles when sensible)
  - Everything is setup automatically. No manual steps.
  - Demo a working version of CoffeeMaker.
  - Demo passing tests.
  - **No credit given for use of ansible galaxy roles**.

## Submission

Please [submit your repo here](https://docs.google.com/forms/d/e/1FAIpQLScnVCRh-4vKz8GljI67AW8y_R5U5VnUuzRZjoTDo_FusLOAsw/viewform?usp=sf_link).

In your repository, have your ansible scripts, README, link to a screencast. Screencast should illustrate a) running ansible scripts to setup your VMs, b) demo using CoffeeMaker and running tests.

The assignment is due Friday, Feburary 2nd before midnight.

## Evaluation

- 50% Ansible scripts.
- 30% Meeting constraints
- 20% Screencast and following instructions