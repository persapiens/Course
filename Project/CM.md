For this milestone, you will work in teams of 4 people.

# Configuration Management and Build Milestone

In this milestone, you will complete the following tasks:

1. *Provisioning* and *configuring* an jenkins server (on a remote VM), automatically using ansible.
2. Using a combination of (jenkins-job-builder or Jenkinsfile) and ansible, automatically setup build jobs for two applications:
  * A nodejs web application [checkbox.io](https://github.com/chrisparnin/checkbox.io).
  * An "enterprise" Java system [iTrust](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v4)
3. Using a combination of mocha/pm2, create a test script that will start and stop the checkbox.io service on the server. A starting place might be [the App](https://github.com/CSC-DevOps/App/blob/master/test/simple.js) we used in the Pipelines workshop.
4. Create a simple git hook or GitHub webhook to trigger a build when a push is made to the repo.   _You may use a forked/cloned version of the two systems._ Demonstrate a passing build for each job after a commit.
  
### Constraints

Abide by the following constraints:

- Be able to setup jenkins configuration files and job files automatically (e.g., using jenkins-job-builder/Jenkinsfile).
- Overcome challenges of automation, such as turning off jenkins setup wizard, and handling authentication.
- For provisioning, use a remote VM, such as one from digital ocean or AWS.
- For checkbox.io build job, it is sufficient to run `npm test`.
- For iTrust build job, verify that `mvn clean test verify checkstyle:checkstyle` works.
- - **No credit given for use of ansible galaxy roles**.

### Systems

##### checkbox.io 

checkbox.io is a site for hosting simple surveys created in markdown. It has dependencies on nginx, node, monogodb.

The following are environment variables that are required to be set:

* MONGO_PORT
* MONGO_IP
* MONGO_USER
* MONGO_PASSWORD
* MAIL_USER
* MAIL_PASSWORD
* MAIL_SMTP

##### iTrust2

iTrust2 is a java application used in the undergrad software engineering system. It using enterprise Java technology. It has a rich set of unit tests.

Using the [following guide](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v2/wiki), to create an ansible script that can prepare a system to run iTrust. 

Tips:

* `mvn -f pom-data.xml process-test-classes` builds the database and creates sample data.
* `mvn jetty:run` launches the server so you can run the system.
* `mvn clean test verify checkstyle:checkstyle` runs the unit tests, launches the server, runs the integration tests, and then brings the server back down.

### Report

As you learn how to setup configuration management for these to projects, document the experiences you have in learning about setting up the system and the issues you had in replicating this process automatically. This can be described in your submission's README.md.

### Evaluation

* Jenkins setup and automation - 40%
* checkbox.io npm test - 20%
* checkbox.io + iTrust.io build jobs - 20%
* Screencast and report - 20%

Points may be deducted for not following instructions, poor quality of implementation, or failing to include sufficient detail required to evaluate capabilities.

_Points will be deducted for non-contributing members._

## Submission

[Submit a link](https://docs.google.com/forms/d/e/1FAIpQLScNDT4FAvo2PaXjQltKUrFCg6pX0HiqNQZK3szGg_RqF36ATA/viewform?usp=sf_link) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* A repo with all scripts required to replicate your submission.
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

**Submit only once per team.**

Tip: If you want to reuse the same repo for your whole project, then create a branch for each milestone. 

**Due Friday, Feb 22rd, before midnight.**
