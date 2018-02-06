For this milestone, you will work in teams of 4 people.

# Configuration Management and Build Milestone

In this milestone, you will complete the following tasks:

1. *Provisioning* and *configuring* an jenkins server, automatically using ansible.
2. Using jenkins-job-builder + ansible, setup build jobs for two applications:
  * A nodejs web application [checkbox.io](https://github.com/chrisparnin/checkbox.io).
  * A software "enterprise" Java system [iTrust](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v2)
3. Demonstrate a passing build for each job.
4. Setup up a `post-build action` that runs ansible scripts to provision and configure a VM for running each application.
  
### Constraints

Abide by the following constraints:

- Be able to setup jenkins configuration files and job files automatically (e.g., using templates/jenkins-job-builder).
- Overcome challenges of automation, such as turning off jenkins setup wizard, and handling authentication.
- For provisioning, use a remote VM, such as one from digital ocean or AWS.
- For checkbox.io build job, it is sufficient to run `npm install`.
- For iTrust build job, verify that `mvn clean test verify checkstyle:checkstyle` works.
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

##### iTrust2

iTrust2 is a java application used in the undergrad software engineering system. It using enterprise Java technology. It has a rich set of unit tests.

Using the [following guide](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v2/wiki), to create an ansible script that can prepare a system to run iTrust. 

Tips:

* `mvn process-test-classes` builds the database and creates sample data.
* `mvn jetty:run` launches the server so it can be used like you'd expect.
* `mvn clean test verify checkstyle:checkstyle` runs the unit tests, launches the server, runs the integration tests, and then brings the server back down.
* Note that you _cannot_ run `mvn process-test-classes jetty:run` as a single command
the `HibernateDataGenerator` doesn't nicely terminate without a `System.exit(0);` at the end.

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

[Submit a link](https://docs.google.com/forms/d/e/1FAIpQLSfedIwkUKoEyQjmoUSilVvXLw2h1Aw80RwkAnTRsuwtPe8DIA/viewform?usp=sf_link) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* your ansible scripts
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

**Submit only once per team.**

Tip: If you want to reuse the same repo for your whole project, then create a branch for each milestone. 

**Due Friday, Feb 23rd, before midnight.**
