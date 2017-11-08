# HW4 - Chaos Engineering

In this homework assignment, you'll get to practice setting up a [chaos engineering experiment](https://medium.com/netflix-techblog/chap-chaos-automation-platform-53e6d528371f).

1) Using simple express servers, create a local service topology as follows:

[Api] => [Ratings]

2) Implement a simple request from the API service to Ratings Service that will fail (500) if Ratings service goes down.

3) Introduce a gateway to the api service. In the experimental cluster, disable the link to Ratings service endpoint (using your own strategy).

![image](https://user-images.githubusercontent.com/742934/32567363-14a0e4f2-c489-11e7-96f7-434ea3b851ae.png)

4) Conduct an expertiment with the above topology.  Use 100 requests. Log/record the status of requests. Write code that can automatically analyze whether the Api service can gracefully handle the Ratings service going down.

4) **Report**. Write a report of your observations and experiences.

## Evaluation

* Experiment topology code - 25%
* Experiment implementation - 50%
* Report - 25%

## Submission

Submit your [repo link](https://docs.google.com/forms/d/e/1FAIpQLSfe_tlZudWpwjZJmb8mjb2uh9s1H5WGA1cYQPu7wz6QxUExrQ/viewform?usp=sf_link).

* README.md (explaning implementation and report)

Due, Tuesday, November 21st, midnight.
