## Test + Analysis Milestone

For this milestone, you will leverage techniques related to fuzzing, test case priorization, and static analysis to improve the quality of checkbox.io and iTrust.

### Coverage/Jenkins Support

Ensure you have the ability to run iTrust's test suite. Add a plugin to jenkins to measure coverage and display a report within Jenkins on every commit.

### Automated Commit Generation - Commit Fuzzer

Develop a tool that automatically commits new random changes to source code which will trigger a build and run of the test suite.

##### Fuzzing operations:

   - change content of "strings" in code.
   - swap "<" with ">"
   - swap "==" with "!="
   - swap 0 with 1
   - any breaking mutation operation you can think of.

To support the commit fuzzer, create a new branch for iTrust, called `fuzzer`.
Create a corresponding jenkins job which enables you to run the test suite against this branch. Finally, you will need to handle rollback (reverting the commit/reseting to head in git) after submitting to jenkins. Create a  ansible playbook that can help you run the fuzzer.

Using your automated commit fuzzer, generate 100 random commits (that still compile) and test runs. 

### Test prioritization analysis

Write a test prioritization analysis that will examine the results of the 100 commit fuzzer runs and test suite runs.  You can extend the workshop we used for analyzing test case results. 

Generate a report that displays the test cases in sorted order, based on time to execute and number of failed tests discovered.

**Note**: Warning, in order to do this you must have a working fuzzer well ahead of the deadline.

### Analysis

##### iTrust

For the iTrust build job, extend to build job to support:

* Running an existing static analysis tool on the source code (e.g. FindBugs, PMD, CheckStyle, etc.), process its results, and report its findings.

* Extend the build job to fail the build minimum testing criteria (e.g. failed test case, or less than 50% statement coverage) and analysis criteria (e.g. fail builds that fail analysis checks, such as FindBug's "Method concatenates strings using + in a loop").

For checkbox.io, extend the build job to support:

* **Custom Metrics**: Calculate your own custom source metrics of source code:

   * Max condition: Count the max number of conditions within an if statement in a function.
   * Long method: Detect a long methods.
   * Free-style: Implement any analysis, such as security-token detection.
   * BONUS (10 points): Detect duplicate code using an AST-based difference algorithm.

* Fail the build if any of these metrics exceed a given threshold.


### Report

Write a report that describes your approaches. Include an analysis of the fuzzer and test priorization. What type of problems do you think the fuzzer discovered? What are some ways fuzzing operations could be extended in the future? Why do you think those tests were ranked the highest?

Describe your approach for analysis. How do you thing these checks might help software developers?


### Constraints

For this milestone we are setting some constraints which you _must_ follow in your submissions. Failure in using these exact formats may result in deductions of your milestone grade. 

1. Sample inventory file (jenkins-executors group below is optional): 
``` ini
[jenkins-srv]
jenkins-srv ansible_host=<ip of jenkins server> ansible_ssh_user=vagrant ansible_python_interpreter=/usr/bin/python3 ansible_ssh_private_key_file=<path to your private key>

[jenkins-executors]
jenkins-srv ansible_host=<ip of executor server> ansible_ssh_user=vagrant ansible_python_interpreter=/usr/bin/python3 ansible_ssh_private_key_file=<path to your private key>
jenkins-srv ansible_host=<ip of executor2 server> ansible_ssh_user=vagrant ansible_python_interpreter=/usr/bin/python3 ansible_ssh_private_key_file=<path to your private key>
... (up to 3 executors allowed)
```

2. Sample variable file (make sure to use the same names for your Ansible variables):
``` yaml
jenkins_user: <value>
jenkins_password: <value>
mysql_user: <value>
mysql_password: <value>
mongo_admin_password: <value>
mongo_checkbox_user: <value>
mongo_checkbox_user: <value>
mongo_checkbox_password: <value>
email_username: <value>
email_password: <value>
checkbox_repo: <url for the checkbox.io repo to use for this assignment -- we should have access to it>
itrust_repo: <url for the itrust repo to use for this assignment -- we should have access to it>
```

3. Only one playbook file, `playbook.yml`, should be run, and it can run other playbooks/roles of your repository.

4. Place inventory file (`inventory.ini`), variables file (`variables.yml`), and playbook (`playbook.yml`) in the root directory of your repository.

Recommendation: Its a good practice to encrypt your credential variables. One option to do this is Ansible vault.

### Evaluation

* Test suites, coverage, and test results, jenkins setup - 10%
* Commit fuzzer - 25%
* Test priorization analysis - 20%
* Analysis and Gates - 30%
* Report - 15%

Points may be deducted for not following instructions or including sufficient detail to evaluate capability. Non-contributed team members may receive reduced or 0 credit.

**Any Jenkins setup steps, including any plugin installation, must be automated.**

## Submission

[Submit a link](https://docs.google.com/forms/d/e/1FAIpQLSfJPzE69558yTFVqXpbu3sNY4yT3m0rLWrgAURfKSfLqpTtpA/viewform?usp=sf_link) to your repository that includes:

* your team (Unity Ids of everyone and their contribution)
* your code and configuration scripts
* a README.md, with your report details,
* screencast that demostrates each evaluation criteria.

If you want to reuse the same repo for your whole project, then create a branch for each milestone.

**Due Sunday, March 17th, before midnight.**
