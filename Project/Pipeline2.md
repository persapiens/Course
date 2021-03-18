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
$ pipeline setup --gh-user <username> --gh-pass <password>
# This command should copy a .vault-pass file, with the password "csc-devops-2020" from the host to VM home directory. The .vault-pass file should be excluded from source control_.

# Trigger a build job (named iTrust), wait for output, and print build log.
$ pipeline build iTrust -u <admin> -p <admin>

# Checkout the iTrust2 repository.
# Initiate analysis of test suite for iTrust to run `-c` numbers of times.
# Output list of tests, ordered from most useful to least useful, based on the number of times the test has detected a failed build.
$ pipeline useful-tests -c 1000 --gh-user <username> --gh-pass <password>
# The output should appear something like this...
Overall mutation coverage: 490/1000 (49%) mutations caught by the test suite.

Useful tests
============
70/100 edu.ncsu.csc.itrust.unit.action.GenerateCalendarActionTest.testGetApptsTable
   - <mutations_dir>/1/iTrust2/
   - <mutations_dir>/3/iTrust2/
   - <mutations_dir>/17/iTrust2/
   ...
60/100 edu.ncsu.csc.itrust.unit.report.DemographicReportFilterTest.testToString
   - <mutations_dir>/1/iTrust2/
   - <mutations_dir>/19/iTrust2/
   ...
50/100 edu.ncsu.csc.itrust.unit.action.AddPatientFileActionTest.testRequiredFieldMissing
10/100 edu.ncsu.csc.itrust.unit.model.officeVisit.OfficeVisitValidatorTest.testSetInvalidHospital
...

# Trigger a build job (named checkbox.io), wait for output, and print build log. 
# Extend existing build job to add a static analysis phase.
# Static analysis should fail build job if any code smells are detected.
$ pipeline build checkbox.io -u <admin> -p <admin>
```

##### Constraints

* Previous constraints from M1 hold.
* Store `gh-password` in Jenkins credentials manager. It is recommended that you generate a developer token as a password.
* The command `useful-tests` should be run on the config-srv; however, it does not necessarily need to run within a Jenkins job.

### 🛠️Automatically configure a build environment and build job (iTrust)

Create a build environment for [iTrust2-v8](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v8), an "enterprise" Java system.

> `iTrust2` is a java application used in the undergrad software engineering system. It using enterprise Java technology. It has a rich set of unit and integration tests. 

Use the [following guide](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v8/wiki/developers-guide), to help you understand how to construct a build environment for running iTrust. _Note:_ as you are not using Eclipse, you do not need to configure or install anything related to it.

**Job:** The build job will need to run the following steps:
* Replace the file/content `iTrust2/src/main/resources/application.yml` with the appropriate settings.
* `mvn clean test integration-test checkstyle:checkstyle` runs the unit tests, launches the server, runs the integration tests, and then brings the jetty server back down.
* After the build, test, analysis step (regardless if build failed or canceled), perform the following clean up:
  - Ensure that any data/schemas will not be present in the database: `DROP DATABASE IF EXISTS iTrust2_test`
  - Kill any remaining chrome processes
  - Look for any stray jetty processes (listening on port 9001).

**Checkstyle and code coverage:** Additionally, the build job should also configure a plugin that measures and report code coverage. Furthermore, both the checkstyle and code coverage plugins should be configured to *gate* the build, which means, if certain thresholds are exceeded, then the build will be failed.

For debugging purposes, you can run `mvn jetty:run`, which will launch a http server and allow you to interact with the system at `http://localhost:8080/iTrust2`.

##### Constraints:

* Use a pipeline style build job.
* Your build job should pass all tests, including the integration tests (which will require running headless Chrome).
* Install additional plugins for viewing checkstyle checks and test coverage reports (recommend `jacoco`).
* You cannot manually create the build job in Jenkins. You may consider using [jenkins-job-builder](https://docs.openstack.org/infra/jenkins-job-builder/) to as a tool for adding/updating the build job in Jenkins.
  
### 🧪 Implement a test suite analysis for detecting useful tests

Your goal is to using fuzzing to simulate potential error developers could make to source code and identify tests that can catch them (essentially an implementation of [mutation testing](https://pedrorijo.com/blog/intro-mutation/)). In other words, if you had to run X test cases, which ones would be the most statistically useful to run?

##### Automated Code Fuzzer

Develop a component that randomly generates changes to source code. You may extend the workshop code. Implement a fuzzer that performs the following operations:

**Required fuzzing operations**:  

   - swap "==" with "!="
   - swap 0 with 1
   - change content of "strings" in code.
   - swap "<" with ">". Be mindful of potential impact on generics.
   - 2 more mutation operations of your choice.

Each run, you should randomly change 1 source files and up to 10% of its source lines of a file with a random subset of the fuzzing operations. Remember, if you're too aggressive in generating mutations, you will not be able to properly explore the space of failures (remember `array.reverse()`).

##### Test prioritization analysis

After you have the ability to generate randomly changed source code, perform the following test prioritization analysis on the iTrust code base.

Generate 1000 test suite runs---for each test suite run, perform the following steps:

* Generate random changes with your code fuzzer.
* If your changes would result in compile failures, discard changes and restart process.
* Run units tests with `mvn clean test`.
* Record which test cases have failed, and which have passed.
* Reset code, *drop database*, discarding your changes.

After you have generated your 1000 test suite runs, generate a report that displays the test cases in sorted order, based on the number of failed tests discovered. Indicate the number of failed test cases and overall mutation coverage of the test suite in the output. Reference the suggested output format in the project driver spec.

**Note**: Warning, in order to do this you must have a working fuzzer well ahead of the deadline. If a test run takes a few minutes to run, it might take a while to generate this analysis---start early!

##### Constraints:

* Do not fuzz the test cases themselves.
* Do not accumulate changes, start from fresh each run.
* You should discard changes that would result in compile failures.
* You should have 1000 test suite runs to perform your test suite analysis.
* You should calculate failure/passed results for *individual test cases and not *test classes*.

### ✅ Implement a static analysis for checkbox.io

Extend the checkbox.io build job to support a static analysis stage that is run before running `npm test`. Print a report that will be visible in the build log.

##### Code smells

Implement a static analysis using *esprima* and *visitor* patterns to calculate the following metrics. You may extend the workshop code. Fail the build if any threshold is exceeded.

   * Long method: Detect long methods (>100 LOC).
   * Message Chains: Detect message chains (for `.`) (> 10 chains)
   * MaxNestingDepth: Count max depth of if statements in a function (> 5)

##### Constraints:

* Run the analysis on all javascript files inside of the server-side/ directory (excluding `node_modules/`). You may limit your analysis to content inside `FunctionDeclaration` nodes.
* Report **all violations** discovered in build log (not just the first encountered).
* Fail the build if *any* of these metrics exceed the given threshold.

## Team responsibilities

### 👥 Task leaders 

Each major task should have a team member responsible for implementing the majority of the assigned task.

Use your GitHub Project Board (e.g. Milestone1) to help coordinate and assign tasks.

![Project Board](https://miro.medium.com/max/4976/1*_St3BrB36V05JAuFIC3utQ.png)

_Points will be deducted for non-contributing members, including receiving zero credit._

### Checkpoint and milestone report.

##### Checkpoint

There will be one checkpoints where you will be required to report interim progress (CHECKPOINT.md).

* Checkpoint due: March 29th

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
* Screencast (10%). [For screencast, you may record a `useful-tests` command with a smaller -c]

Points may be deducted for not following constraints, poor quality of implementation, poor task communication and delegation, or failing to include sufficient detail required to evaluate capabilities.

_Points will be deducted for non-contributing members, including receiving zero credit._

## Submission

Commit your all your work related to your project into your designated repository before the final deadline. Create a branch called `M2` to hold a snapshot of your work related to this milestone.

Ensure your repository contains:

* a top-level node.js project supporting the required commands for running your build server.
* a file containing the **full output** of the useful-tests command with 1000 iterations.
* a README.md, with your milestone report details.
* a CHECKPOINT.md, with your checkpoint report.
* a link to screencast that demostrates each task.

**Due Thursday, April 8th, before midnight.**
