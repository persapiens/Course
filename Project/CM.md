For this milestone, you will work in teams of 4 people.

# Configuration Management and Build Milestone

In this milestone, you will complete the following tasks:

1. Provisioning and configuring an jenkins server, automatically using ansible.
2. Setup up the build jobs in Jenkins for the two applications, using ansible.
  * A nodejs web application [checkbox.io](https://github.com/chrisparnin/checkbox.io).
  * A software "enterprise" Java system [iTrust](https://github.ncsu.edu/engr-csc326-staff/iTrust-v23)
3. Setup up a `post-build action` that runs ansible scripts to provision and configure a VM for running each application.
  
### Constraints

Abide by the following constraints:

- Setup necessary runtime packages automatically.
- Be able to setup jenkins configuration files and job files automatically (e.g., using templates).
- Overcome challenges of automation, such as turning off jenkins setup wizard, and handling authentication.
- For provisioning, you can remotely acquire a VM from digital ocean or AWS, or locally using vagrant.
- For checkbox.io build job, it is sufficient to run `npm install`.
- For iTrust build job, verify that `mvn compile` works.
- Demonstrate that checkbox.io works in a browser.
- Demonstrate that iTrust works in a browser.

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

##### iTrust

iTrust is a java application used in the undergrad software engineering system. It uses tomcat, mysql, java, and maven. It has a rich set of unit tests.

Using the [following guide](http://agile.csc.ncsu.edu/iTrust/wiki/doku.php?id=home_deployment_instructions), to createan ansible script that can prepare a system to run iTrust. 

### Report

As you learn how to setup configuration management for these to projects, document the experiences you have in learning about setting up the system and the issues you had in replicating this process automatically. This can be described in your submission's README.md.

### Evaluation

* Jenkins automation - 20%
* checkbox.io + iTrust.io build jobs - 20%
* iTrust post-build configuration - 20%
* checkbox.io post-build configuration - 20%
* Screencast and report - 20%

Points may be deducted for not following instructions, poor quality of implementation, or failing to include sufficient detail required to evaluate capability.

Points will be deducted for non contributing members.

## Submission

[Submit a link](https://docs.google.com/forms/d/e/1FAIpQLSfudbWrTbiNqFdAs1Lt0pRTII0qpF1mKXMAgu3om_fUpjys1Q/viewform?usp=sf_link) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* your ansible scripts
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

If you want to reuse the same repo for your whole project, then create a branch for each milestone.

**Due Monday, September 25th, midnight.**

