# HW #2 Test Generation and Coverage

Continuous deployment and DevOps instrastructure cannot survive without tests.
We've learned how to automatically generate tests, a process which can be triggered after a commit, or during other stages of the deployment pipeline.

### 100% Branch and Statement Coverage

In our test generation workshop, we worked with automatically generating sample code.
I've extended the driver to improve its ability to reach even more paths automatically. However, there are some paths still missing.

Statements: 92.31% ( 48/52 )
Branch: 62.5% ( 10/16 )

Your assignment is to complete the automation of new tests to achieve 100% branch and statement coverage.

To help visualize coverage over the code, you should open the following report that is generated:

    open coverage/lcov-report/TestGeneration/subject.js.html

### Uncovered Items

* There is a branch not covered: `if(q ==undefined) q =1;`
* There is a branch not covered: `if p < 0`
* There is a statement is not covered: `p = -p;`
* There is a branch not covered: `if( buf.length > 0 )`
* There is a statement not covered: `return false;`
* There is a branch not covered: `if (!options || !options.normalize) {`
* There is a branch not covered: `for ( var i = 0, l = phoneNumber.length; i < l; i++ ) {`
* There is a statement not covered: `formatString = formatString.replace("N", phoneNumber[i]);`
* There is a branch not covered: `if( area == "(212)" )`
* There is a statement not covered: 	`return true;`

### Submission

Create a github repository (on github proper or NCSU), place your coverage report in the README.md file and your code in your repository.

Please email your TA with the link to your repository in order to submit.

The assignment is due Friday, Feb 13th at midnight.

### Evaluation

- No coverage improvement over baseline: 70% 
- Statement coverage meets 50/52 and Branch coverage meets 12/16: 80%
- Statement coverage meets 50/52 and Branch coverage meets 14/16: 90%
- Full coverage: 100%
