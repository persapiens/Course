# HW0

This homework will prepare you for basic setup for the course.

**The assignment is due Friday, Jan 29th, before midnight**.

### Basic course setup (5)

Properly setting up your Discord and Moodle profile.

* For Moodle, upload a current headshot picture of you (not anyone else, not a cartoon picture of you, etc.) to your Moodle profile, which will help the teaching staff learn your name. Use [US passport photo guidelines](http://travel.state.gov/passport/pptphotoreq/photocomptemplate/photocomptemplate_5297.html).
* For Discord, make sure you have your first and last name as part of your profile.

### Github (5)

Sign into [NCSU's GitHub](https://github.ncsu.edu/).

1. Create a *private* repo called HW0-DevOps. 
2. Go to Settings, Collaborators and Teams, and add the TA and instructor as a collaborator (using their unity id).

Sara Ghodsi <sghodsi@ncsu.edu>, Rohit Nair <rnair2@ncsu.edu>, Christopher Parnin <cjparnin@ncsu.edu>

### Do class activities (10)

* Make an brief introduction of yourself in #welcome
* Pick and explain the difference between nightly builds, continuous integration, continuous delivery, and continuous deployment in Breakout.

### Do Basics workshop exercises (10)

* Setup: Practice: Installing useful software
* Setup: Exercise: Customize your bash prompt
* Shells: Exercise: Data Science with Bash
* Git: Practice: Creating a Repo
* Markdown: Practice: Create an About Me Page (AboutMe.md) in your homework submission.

**Bonus**: Git: Complete all levels in https://learngitbranching.js.org/ ---just include a screenshot of completed level scrreen in your Homework submission (+10) points.

### Opunit checks (20)

* Acheive 100% pass rate for opunit profile checks:

```sh
opunit profile CSC-DevOps/profile:519.yml
```

Include screenshot of command output in your submission.

By completed the Basics workshop, you should have be able to perform all setup tasks necessary to pass the checks.

### Answer conceptual questions (10)

* What is heredoc, and why might it be useful?
* Explain what does it mean by "Commits are NOT diffs"?
* What are signs of a bad kanban board?
* 
* a
* a 
* Explain "Fast to Deploy, Slow to Release"
* a
* b
* c


### Complete provisioning workshop (20)

Complete all the steps in the provision workshop using [digitalocean](https://developers.digitalocean.com/v2/) api. You must be able to obtain your [own api key](https://www.digitalocean.com/docs/api/create-personal-access-token/) after creating your account.

### Provision with additional cloud provider (20)

As part of any risk management strategy, it is also important to be able to have access to a variety of platforms to avoid vender lock-in and systematic failures. You provisioned a virtual machine from Digital Ocean---Choose [one additional cloud provider listed here](Cloud-Providers.md).

The provisioning code needs to be able to perform the following essential task:

> _create a new VM and print out the ip address of the new server_.

You are free to choose which technology/framework you like for your implementation. You might consider something like the [node aws-sdk package](https://www.npmjs.com/package/aws-sdk), or [boto for Python](https://aws.amazon.com/sdk-for-python/), or just raw REST requests.

Depending on your cloud provider, there may be some manual one-time configuration you need to perform on your account, such as setting up security groups, firewall rules, etc. For this assignment, this can be manually configured.

## Screencast (10)

Create a screencast of your assignment:

* Create a screencast demoing your opunit profile check.
* Demonstrate running your code that provisions the two servers across the different platforms, including the cloud provider interface before and after running the code.

For guidelines, software, and recommendations see [Screencasts](Screencasts.md).

## Evaluation

**Note**: You will receive a **ZERO** if a security token is found to be checked into your repository.

You will be graded for completing the following tasks:

* [ ] Complete moodle and discord account setup by deadline (5).
* [ ] Correct Github repo and collobrator setup (5).
* [ ] Complete class activities (10)
* [ ] Answer conceptual questions (10)
* [ ] Complete basic workshop exercises (10)
* [ ] Pass all `opunit` checks (10)
* [ ] Complete provision workshop (20)
* [ ] Provisioning for another cloud provider (20)
* [ ] Screencast (10)
* [ ] Bonus: Git: Complete all levels in https://learngitbranching.js.org/ (+10)

## Submission

Please a submit a [link to your repo here](https://docs.google.com/forms/d/e/1FAIpQLSc3LEsLc5FPiZbymd03ToIe63UNTMnAV4CrA32z3OyocbJdsg/viewform?usp=sf_link).

In your repository, check in all relevant code, and provide answers, link to relevant files, and link to your screencast the repository's `README.md`. 

**The assignment is due Friday, Jan 29th, before midnight**.