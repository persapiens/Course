## Test + Analysis Milestone

For this milestone, you will leverage techniques related to fuzzing, test case priorization, and automated test generation to improve the quality of checkbox.io and iTrust.

### Coverage/Jenkins Support

Ensure you have the ability to run iTrust's and checkbox.io* test suite. You need to have your build server have a jetty/mysql instance in order to properly run the unit + integration tests. Add a plugin to jenkins to measure coverage and display a report within Jenkins on every commit.

*You will have an automatically created test suite for checkbox.io created below.

### Automated Commit Generation - Commit Fuzzer

Develop a tool that automatically commits new random changes to source code which will trigger a build and run of the test suite.

##### Fuzzing operations:

   - change content of "strings" in code.
   - swap "<" with ">"
   - swap "==" with "!="
   - swap 0 with 1
   - any operation you can think of.

To support the commit fuzzer, create a new branch for iTrust, called `fuzzer`.
Create a corresponding jenkins job which enables you to run the test suite against this branch. Finally, you will need to handle rollback (reverting the commit/reseting to head in git) after submitting to jenkins. Create a  ansible playbook that can help you run the fuzzer.

Using your automated commit fuzzer, generate 100 random commits (that still compile) and test runs. 


### Test prioritization analysis

Write a test priorization analysis that will examine the results of the 100 commit fuzzer runs and test suite runs.  You can extend the workshop we used for analyzing test case results. 

Generate a report that displays the test cases in sorted order, based on time to execute and number of failed tests discovered.

**Note**: Warning, in order to do this you must have a working fuzzer well ahead of the deadline.

### Automated Test Generation

Using esprima and AST visitor patterns, write an automated test generation algorithm to analyze checkbox.io's server-side code and automatically generate test cases for the API routes.

**Tips**: You will want to use the route path, params, and contents of the route handler  `app.get('/api/study/load/:id', study.loadStudy );` to guide your test generation.

You may use the auto generated testing workshop as a starting place for code. You may want to use a mocking framework, such as sinon-mongoose and nock, to mock access to the MongoDB instance and REST apis, during an unit test.

### Report

Write a report that describes your approaches. Include an analysis of the fuzzer and test priorization. What type of problems do you think the fuzzer discovered? What are some ways fuzzing operations could be extended in the future? Why do you think those tests were ranked the highest?

Describe your approach for automated test generation. How many tests were you able to achieve and what was the resulting coverage?


### Evaluation

* Test suites, coverage, and test results, jenkins setup - 10%
* Commit fuzzer - 25%
* Test priorization analysis - 25%
* Automated Test Generation - 25%
* Report - 15%

Points may be deducted for not following instructions or including sufficient detail to evaluate capability. Non-contributed team members may receive reduced or 0 credit.

**Any Jenkins setup steps, including any plugin installation, must be automated.**

## Submission

[Submit a link](https://docs.google.com/forms/d/e/1FAIpQLScPDgKPJBzBwUD152Fex9eR0Vu42gX5JD6hTKr3CdZCb2abOg/viewform?usp=sf_link) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* your ansible scripts
* your code and configuration
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

If you want to reuse the same repo for your whole project, then create a branch for each milestone.

**Due Monday, March 19th, midnight.**
