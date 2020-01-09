# HW0

This homework will prepare you for basic setup for the course.

## Basic course setup (10)

Properly setting up your Mattermost, Stack Overflow, and Moodle profile.

* For Moodle, upload a current headshot picture of you (not anyone else, not a cartoon picture of you, etc.) to your Moodle profile, which will help the teaching staff learn your name. Use [US passport photo guidelines](http://travel.state.gov/passport/pptphotoreq/photocomptemplate/photocomptemplate_5297.html).
* For Mattermost, make sure you have your first and last name as part of your profile.
* For your Stack Overflow account, you are not required to use a full name or photo.

## Github (10)

Sign into [NCSU's GitHub](https://github.ncsu.edu/).

1. Create a *private* repo called HW0-DevOps. 
2. Go to Settings, Collaborators and Teams, and add the TAs and instructor as a collaborator (using their unity id).

Samim Mirhosseini Ghamsa <smirhos@ncsu.edu>, Jeremiah Percy Dsouza <jdsouza@ncsu.edu>, Christopher Parnin <cjparnin@ncsu.edu>

## Asking a Question, Answering a Question (10)

Practice asking a question (Q) on Stack Overflow Teams. Provide an answer (A) to at least one question on Stack Overflow Teams.

## Opunit checks (10)

* Acheive 100% pass rate for opunit profile checks:

```sh
opunit profile CSC-DevOps/profile:519.yml
```

Include screenshot of command output in your submission.

## Provisioning (50)

Automatically provisioning a computational resource will be one of the most important skills for you to master in your career.  You have gained experience using [digitalocean](https://developers.digitalocean.com/v2/) to automatically create virtual images on a cloud platform and perform simple tasks with the droplets. As part of any risk management strategy, it is also important to be able to have access to a variety of platforms to avoid vender lock-in and systematic failures.

In this homework assignment, you will complete the following tasks:

* Be able to automatically provision using a code api from **two cloud providers**. Logically, you should complete the provision workshop, to have digitalocean count as one. Choose [one additional cloud provider listed here](Cloud-Providers.md).

* The provisioning code needs to be able to perform the following:
  - create a new VM, with a registered ssh key. *This will allow you ssh directly into your account without being emailed a temporary root password.*
  - print out the ip address of the new server.

* You are free to choose which technology/framework you like for your implementation. You might consider something like the [node aws-sdk package](https://www.npmjs.com/package/aws-sdk), or [boto for Python](https://aws.amazon.com/sdk-for-python/), or just raw REST requests.

* Use proper and source control and configuration management practices e.g., using package managers and their associated files (package.json/requirements.txt) to declare software dependencies. Remember, someone else should be able to run your code.

* Depending on your cloud provider, there may be some manual one-time configuration you need to perform, such as setting up security groups, firewall rules, etc. For this assignment, this can be manually configured.

## Screencast (10)

Create a screencast of your assignment:

* Create a screencast demoing your opunit profile check.
* Demonstrate running your code that provisions the two servers across the different platforms, including the cloud provider interface before and after running the code. Demonstrate being able to ssh into your box with your registered ssh key.

For guidelines, software, and recommendations see [Screencasts](HW/Screencasts.md).

## Evaluation

You will receive a **ZERO** if a security token is found to be checked into your repository.

* Complete moodle, mattermost, stack overflow profiles by deadline (10).
* Github repo and collobrator settings (10).
* Ask and answer a question (10)
* Opunit checks (10)
* Provision code for two cloud providers (40)
* Screencast (10)

## Submission

Please a submit a [link to your repo here](https://docs.google.com/forms/d/e/1FAIpQLScpsVVjgEdDWxL1ejbi8tg1HArv3B4yva98_jhUd_hIF_CQnA/viewform?usp=sf_link).

In your repository, have your code, link to a screencast.

The assignment is due Friday, Jan 17th before midnight.

