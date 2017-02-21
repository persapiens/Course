## Build, Test, and Analysis Milestone

You will continue to work with checkbox.io and iTrust.

### Build Server

Extend the materials from the configuration management milestone and Jenkins homework assignment to create a Jenkins build server that contains:

* A build job for checkbox.io
* A build job for iTrust

**Any Jenkins setup steps must be automated.**

### Testing Component

Extend the build definitions for iTrust to include the ability to run its test suite, measure coverage, and report the results.

#### Automated Commit Generation - Test Case Fuzzer

Create a new branch for iTrust, called `testcases`.

Develop a tool that automatically commits new random changes to source code which will trigger a build and run of the test suite.

Some fuzzing operations:

   - change content of "strings" in code.
   - swap "<" with ">"
   - anything else you can think of.

##### Useless test detector

Using your automated commit generator, generate 100 random commits (that still compile). 

Write a "useless" test detector that will, for each test suite run, keep track of the test cases that failed and which ones passed. Generate a report that displays tests cases that always pass.

Bonus (20 points): Extend the [test-stability-plugin](https://github.com/jenkinsci/test-stability-plugin) to calculate and display "useless" tests in Jenkins.

### Analysis Component

Create an analysis tool that runs on checkbox.io's server-side code and implements the following detections.

**Max condition**: Detect the max number of conditions within an if statement in a function (greater than 8).
**Long method**: Detect any long methods (greater than 100 lines of code).
**The Big O**. Detect any method with a big O greater than 3.

**Fail the build if any of these results occur**.

### Evaluation

* Build Jobs and Jenkins setup - 20%
* Test suites, coverage, and test results - 20%
* Test case fuzzer - 20%
* Uselesss test detector - 20%
* Analysis and build failure - 20%

Points may be deducted for not following instructions or including sufficient detail to evaluate capability.

**Any Jenkins setup steps, including any plugin installation, must be automated.**

## Submission

[Submit a link](https://docs.google.com/a/ncsu.edu/forms/d/e/1FAIpQLSe7eaXI9AqZqh5oaR5izPRFiCQLNqMrX2qbnmfp-Zd3_QeVVQ/viewform) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* your ansible scripts
* your fuzzer and detector code
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

If you want to reuse the same repo for your whole project, then create a branch for each milestone.

**Due Wednesday, March 15th, midnight.**
