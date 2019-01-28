# HW 2 - Configuration Management

Automatically configuring a computational resource will be one of the most important skills for you to master in your career.  You have gained experience using [ansible] to automatically run configuration tasks on a virtual machines.

In this homework assignment, you will complete the following tasks:

Using ansible, be able to automatically configure a server running mattermost.

Perform the following tasks listed in the [installation guide](https://docs.mattermost.com/install/install-ubuntu-1604.html) for mattermost. 

* Installing Ubuntu Server 16.04 LTS
* Installing MySQL Database Server (5.7.x is recommended)
* Installing Mattermost Server
* Configuring Mattermost Server

Your goal is to translate those instructions into ansible playbooks.

Follow the following constraints when creating your server:

  - Use best practices (use modules to do work, avoid shell/commands, be idempotent, use your own roles when sensible)
  - Everything is setup automatically. No manual steps.
  - Demo a working version of mattermost.
  - **No credit given for use of ansible galaxy roles**.

## Submission

Please [submit your repo here](https://docs.google.com/forms/d/e/1FAIpQLSe2MIgnenAbfroyzWwryEB_BBsu1UZkwnAXvXmhJE5s1ycq1g/viewform?usp=sf_link)

### Replication instructions

You repo must contain full instructions/code for running your ansible playbooks, including baker.yml or Vagrantfile for provisioning VM. We will replicate running the playbooks.

Include a section in your README.md that includes a set of instructions that will allow another person to create a target VM and then run your ansible scripts.

The assignment is due Friday, Feburary 8th before midnight.

## Evaluation

- 40% Ansible scripts for configuring mattermost (10 points per each task).
- 20% Quality of scripts and following best practices.
- 20% Replication of ansible playbooks.
- 20% Screencast and following instructions