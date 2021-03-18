# Pipeline > Test+Analysis

For this milestone and project, you will continue to work in teams of 3 people.

> Note: your project should retain the functionality of the previous milestone.

## General Tasks

* Automatically configure a build environment and build job for a Java application (iTrust).
* Implement a test suite analysis for detecting useful tests.
* Implement a static analysis for detecting code smells.

### Project Driver

Extend your node.js project to support the following commands:

```bash
# Configure jenkins, build environments, build jobs
# --gh-user and --gh-pass should be used for accessing iTrust repo on github.ncsu.edu
# It is recommended that you generate a developer token.
# Store password in Jenkins vault.
$ pipeline setup --gh-user <username> --gh-pass <password>
# This command should copy a .vault-pass file, with the password "csc-devops-2020" from the host to VM home directory. The .vault-pass file should be excluded from source control_.

# Trigger a build job (named iTrust), wait for output, and print build log.
$ pipeline build iTrust -u <admin> -p <admin>

# Initiate analysis of test suite for iTrust to run `-c` numbers of times.
# Output list of tests, ordered from most useful to least useful, based on the number of times 
# the test has detected a failed build.
$ pipeline useful-tests -c 100
90/100 edu.ncsu.csc.itrust.unit.action.GenerateCalendarActionTest.testGetApptsTable
80/100 edu.ncsu.csc.itrust.unit.report.DemographicReportFilterTest.testToString
70/100 edu.ncsu.csc.itrust.unit.action.AddPatientFileActionTest.testRequiredFieldMissing
10/100 edu.ncsu.csc.itrust.unit.model.officeVisit.OfficeVisitValidatorTest.testSetInvalidHospital
...

# Trigger a build job (named checkbox.io), wait for output, and print build log. 
# Extend existing build job to add a static analysis phase.
# Static analysis should fail build job if any code smells are detected.
$ pipeline build checkbox.io -u <admin> -p <admin> --with-static
```

##### Constraints

* Use bakerx as local provisioner for your VM (named "config-srv").
* Assign static ip address 192.168.33.20 for jenkins server. 
* Use ansible for configuration. No credit given for use of ansible galaxy roles.
* Run jenkins server on port 9000. Note that iTrust will need port 8080.

### 🛠️Automatically configure a build environment and build job (iTrust)

Create a build environment for [iTrust](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v6), an "enterprise" Java system.

iTrust2 is a java application used in the undergrad software engineering system. It using enterprise Java technology. It has a rich set of unit tests. Using the [following guide](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v6/wiki/developers-guide), to help you understand how to construct a build environment for running iTrust.

The build job will need to run the following commands:
* `mvn clean process-test-classes -f pom-data.xml` builds the database and creates sample data. Ensure database is dropped between builds.
* `mvn clean test verify org.apache.maven.plugins:maven-checkstyle-plugin:3.1.0:checkstyle` runs the unit tests, launches the server, runs the integration tests, and then brings the server back down.

For debugging purposes, you can run `mvn jetty:run`, which will launch a http server and allow you to interact with the system at `http://localhost:8080/iTrust2`.

##### Constraints:

* Configure the environment to run on the same build server.
* You are free to construct the build environment for iTrust with any technology/tools, as long as it is done automatically.
* Your build job should pass all tests, including the integration tests.
  
### 🧪 Implement a test suite analysis for detecting useful tests

Your goal is to using fuzzing to simulate potential error developers could make to source code and identify tests that can catch them (essentially an implementation of [mutation testing](https://pedrorijo.com/blog/intro-mutation/)). In other words, if you had to run X test cases, which ones would be the most statistically useful to run?

##### Automated Code Fuzzer

Develop a component that randomly generates changes to source code.
Example fuzzing operations:  

   - swap "==" with "!="
   - swap 0 with 1
   - change content of "strings" in code.
   - swap "<" with ">". Be mindful of potential impact on generics.
   - any other mutation operation you can think of.

You should randomly change up to 10% of the source files and up to 10% of the source lines of a file.  

##### Test prioritization analysis

After you have the ability to generate randomly changed source code, perform the following test prioritization analysis on the iTrust code base.

Generate 100 test suite runs---for each test suite run, perform the following steps:

* Generate random changes with your code fuzzer.
* If your changes would result in compile failures, discard changes and restart process.
* Run tests with `mvn clean test`.
* Record which test cases have failed, and which have passed.
* Reset code, discarding your changes.

After you have generated your 100 test suite runs, generate a report that displays the test cases in sorted order, based on the number of failed tests discovered. Indicate the number of failed test cases in the output.

**Note**: Warning, in order to do this you must have a working fuzzer well ahead of the deadline. If a test run takes 5--10 minutes to run (if integration tests are enabled), it might take a while to generate this analysis.

##### Constraints:

* Do not fuzz the test cases themselves.
* Do not accumulate changes, start from fresh each run.
* You should discard changes that would result in compile failures.
* You should have 100 test suite runs to perform your test suite analysis.
* You should calculate results for individual test cases and not test classes.

### ✅ Implement a static analysis for checkbox.io

Extend the checkbox.io build job to support a static analysis stage that is run before running `npm test`.

##### Code smells

Implement a static analysis using esprima and visitor patterns to calculate the following metrics.

   * Long method: Detect long methods (>100 LOC).
   * Message Chains: Detect message chains (for `.`) (>10 chains)
   * MaxNestingDepth: Count the max number of if statements in a function (>5)

##### Constraints:

* Run the analysis on all javascript files inside of the server-side/ directory (excluding `node_modules/`).
* Report all metrics discovered in build log.
* Fail the build if any of these metrics exceed a given threshold.

## Team responsibilities

### 👥 Task leaders 

Each major task should have a team member responsible for implementing the majority of the assigned task.

Use your GitHub Project Board (e.g. Milestone1) to help coordinate and assign tasks.

![Project Board](https://miro.medium.com/max/4976/1*_St3BrB36V05JAuFIC3utQ.png)

_Points will be deducted for non-contributing members, including receiving zero credit._

### Checkpoint and milestone report.

##### Checkpoint

There will be one checkpoints where you will be required to report interim progress (CHECKPOINT.md).

* Checkpoint 1 due: July 1st

Document your current progress and team contributions. Note work you have completed and what work will be done next. You may find it useful to take screenshots of your GitHub Projects.

_Points will be deducted for teams not making steady progress throughout the milestone._

##### Milestone report

Document the experiences you have in learning about setting up the system, and implementing your test and analysis techniques.
This can be described in your submission's README.md.

## Evaluation

* Automatically configure a build environment and build job (20%).
* Test prioritization analysis (30%).
* Static analysis (30%).
* Checkpoint and milestone report (10%).
* Screencast (10%).

Points may be deducted for not following constraints, poor quality of implementation, poor task communication and delegation, or failing to include sufficient detail required to evaluate capabilities.

_Points will be deducted for non-contributing members, including receiving zero credit._

## Submission

Commit your all your work related to your project into your designated repository before the final deadline. Create a branch called `M2` to hold a snapshot of your work related to this milestone.

Ensure your repository contains:

* a top-level node.js project supporting the required commands for running your build server.
* a README.md, with your report details.
* a CHECKPOINT.md, with your two checkpoint reports.
* a link to screencast that demostrates each task.

**Due Monday, July 6th, before midnight.**
