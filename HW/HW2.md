# HW #2 Test Generation and Coverage

Continuous deployment and DevOps instrastructure cannot survive without tests. We've learned how to automatically generate tests, a process which can be triggered after a commit, or during other stages of the deployment pipeline.

### 100% Branch and Statement Coverage

In our test generation workshop, we worked with automatically generating sample code. However, there are some paths still missing.

* Statements: 71.43% (35 / 49)
* Branch: 40% (12 / 30)

Your assignment is to complete the automation of new tests to achieve 100% branch and statement coverage.

To help visualize coverage over the code, and get an accurate count of statements and branches you should open the following report that is generated:

    open coverage/lcov-report/TestGeneration/subject.js.html

### Uncovered Items

* There is a branch not covered: `if(q ==undefined) q =1;`
* There is a branch not covered: `if p < 0`
* There is a statement is not covered: `p = -p;`

* In weird(), there is a statement not covered, `z=33;`
* In weird(), there is a statement not covered, `return 1`.
* In weird(), there is a statement not covered, `y = z/x`.
* In weird(), there is another statement not covered, `return 1`.
* In weird(), there is a branch not covered, related to `y < 0`.
* In weird(), there is a branch not covered related to `mode.indexOf`
* In weird(), there the top-level else branch is not covered.
* In weird(), there is a branch not covered, related to inner else.
* In weird(), there is a branch not covered, related to `mode != "strict"`

* There is a branch not covered: `if( buf.length > 0 )`
* There is a statement not covered: `return false;`
* There is a branch not covered: `if (!options || !options.normalize) {`
* There is a branch not covered: `for ( var i = 0, l = phoneNumber.length; i < l; i++ ) {`
* There is a statement not covered: `formatString = formatString.replace("N", phoneNumber[i]);`
* There is a branch not covered: `if( area == "(212)" )`
* There is a statement not covered: 	`return true;`

### Submission

Create a github repository (on github proper or NCSU), place a screenshot of your coverage report in the README.md file and your code in your repository.

Please [submit your assignment here](https://docs.google.com/a/ncsu.edu/forms/d/1dFQ7hJcEoaRyLyokftZ-KPOlJw-RJI4sJ_Wqxyzbxk4/viewform?usp=send_form).

The assignment is due Tuesday, Oct 13th at midnight.

### Evaluation

- No coverage improvement over baseline: 50% 
- Statement coverage meets 38/49 and Branch coverage meets 15/30: 60%
- Statement coverage meets 42/49 and Branch coverage meets 20/30: 70%
- Statement coverage meets 44/49 and Branch coverage meets 22/30: 80%
- Statement coverage meets 46/49 and Branch coverage meets 25/30: 90%
- Statement coverage meets 48/49 and Branch coverage meets 28/30: 100%
- Full coverage: 105%

Hard coding tests will not work. For evaluation, test.js will be deleted.
Your code will be run against "mystery.js" file, which will contain the same structure, but different concrete values.
