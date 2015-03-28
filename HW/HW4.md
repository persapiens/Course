# Homework 4

In the deployment workshop, we learned how to deploy a simple web application using a blue-green strategy.

In this homework, you will be completing the deployment process, but also handle data migration, by deploying the application developed in the redis workshop/homework 3, and handling migration of the data between the blue and green slice.

Deploy the web application with the following additional considerations:

* Complete git/hook setup for triggering deployment on push.
* Create blue/green infrastructure for deployment, including a blue redis instance and green redis instance.
* Default infrastructure will route traffic to the blue instance.
* Introduce a new route, `/switch`, that will trigger a switch from "blue" to "green" and vice versa.
* Recall, the `/upload` and `/meow` routes.  Extend `/switch` so that if a redis instance currently has values in the picture list, then migrate those instances over to the new instance.
* Introduce a feature flag in the application, "mirroring", which when turned on, will forward information added to the picture list, to the other slice.

### Evaluation 

* Complete git/hook setup: 50%
* Create blue/green infrastructure: 60%
* Demonstrate `/switch` route: 70%
* Demonstrate migration of data on switch: 85%
* Demonstrate mirroring: 100%

### Submission

Create a github repository (on github proper or NCSU), with a basic report in the README.md file and your code in your repository.

Please email your TA with the link to your repository in order to submit.

The assignment is due Monday, April 6th at midnight.
