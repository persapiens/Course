For this milestone, you will work in teams of 4 people.

## Configuration Management Milestone

Setup up configuration management and build environments for two software projects.

* A nodejs web application [checkbox.io](https://github.com/chrisparnin/checkbox.io).
* A software "enterprise" Java system [iTrust](https://github.ncsu.edu/engr-csc326-staff/iTrust-v23)

### checkbox.io

Create an ansible script that can prepare a system to run checkbox.io. Verify the system works.

##### Dependencies

* nginx
* node
* monogodb

##### Software

* Fix any missing npm packages in the package.json.
* Modify the software to load mongo credentials from environment variables. For example, see this [connection string](https://github.com/chrisparnin/checkbox.io/blob/master/server-side/site/routes/admin.js#L20).
* Fix any mongodb configuration issues

### iTrust

iTrust is a java application used in the undergrad software engineering system. It uses tomcat, mysql, java, and maven. It has a rich set of unit tests.

Using the [following guide](http://agile.csc.ncsu.edu/iTrust/wiki/doku.php?id=home_deployment_instructions), create an ansible script that can prepare a system to run iTrust. Verify the system works.

### Report

As you learn how to setup configuration management for these to projects, document the experiences you have in learning about setting up the system and the issues you had in replicating this process automatically. This can be described in your submission's README.md.

### Evaluation

* checkbox.io ansible scripts - 20%
* Verify can run checkbox.io in browser - 20%
* iTrust ansible scripts - 20%
* Verify can run iTrust in browser - 20%
* Screencast and report - 20%

Points may be deducted for not following instructions or including sufficient detail to evaluate capability.

## Submission

[Submit a link](https://docs.google.com/a/ncsu.edu/forms/d/e/1FAIpQLSejgAsKbX_-rs701y_hiUQFK0gGHJJ6nTPpZM1UYWB0U5ufsg/viewform) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* your ansible scripts
* your modified checkbox.io software
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

If you want to reuse the same repo for your whole project, then create a branch for each milestone.

**Due Feburary 16th, midnight.**

