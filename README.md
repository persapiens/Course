# DevOps: CSC 519
-------------------------

Modern software development organizations require entire teams of DevOps to automate  and maintain software engineering processes and infrastructure vital to the organization. In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure. 
Students will have the chance to build new or extend existing software engineering tools and design a DevOps pipeline.

Past versions:
* [Spring 2017](https://github.com/CSC-DevOps/Course/tree/Spring2017)
* [Fall 2016](https://github.com/CSC-DevOps/Course/tree/Fall2016)
* [Spring 2015 ](https://github.com/CSC-DevOps/Course/tree/Spring2015)
* [Fall 2015 ](https://github.com/CSC-DevOps/Course/tree/Fall2015)

## Course Overview

In the course, a mixture of traditional lectures with activities and in-class workshops will be used.  During lectures, we will cover core concepts related to a topic. During the in-class workshops, we will perform sample exercises with relevant tools that reinforce lecture material.  Evaluation will be based on tech talks, homework assignments, workshop attendance, and final project.

After the course, students are able to:

* Programmatically **provision** images.
* Automatically apply **configuration management** to production environments.
* Automatically create and maintain **build** environments.
* Maintain test suites and measure **testing quality** and coverage.
* Automatically **generate new tests**, using feedback-directed random testing, fuzzing, and data-flow analysis.
* Programmatically measure **code quality** via static and dynamic code analysis.
* Understand components of **infrastructure**.
* Remotely regulate behavior of deployed software via **feature flags** and configuration servers.
* Apply advanced strategies for **deployment** of software.
* Monitor and analyze **telemetry** data.
* Implement **resilience testing** on production environments (e.g., Chaos Monkey).

### Project

The primary objective of the course will be to allow students to gain experience in incrementally building a continous delivery pipeline from scratch.  Throughout the semester, students are expected to complete a component of the pipeline by each milestone deadline.

##### Milestones

Details on requirements for milestones will be released throughout the course.  A student's pipeline should demonstrate the following components by the milestone deadline:

* CM
* BUILD+TEST+ANALYSIS
* DEPLOY
* SPECIAL

## Schedule and Topics - Fall 2017

The following schedule is subject to change.

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
| Aug 17   | [Core Concepts](http://tiny.cc/CSC-DevOpsCore) |  [Adages](https://github.com/CSC-DevOps/Course/blob/master/Readings/AdagesI.pdf)        | [HW0](https://github.com/CSC-DevOps/Course/blob/master/HW/HW0.md) |
| Aug 22   | [Configuration Management](http://tiny.cc/devops-cm-slides)  |            | |
| Aug 24   | [Workshop: Managed Environments](https://github.com/CSC-DevOps/CM/blob/master/README.md) |            | [HW1](HW/HW1.md) |
| Aug 29   | [Workshop: Ansible](https://github.com/CSC-DevOps/CM/blob/master/README.md) |  |   |
| Aug 31   | Workshop: Provisioning   |            |                   |
| Sep 5    | [Build Management](https://docs.google.com/presentation/d/1PeI-RbsisPtC8tbKMgtB3IDlffLjE6obQkp-tL0Cmsw/edit#slide=id.p)   |             | [MILESTONE: CM+BUILD](Project/CM.md) |
| Sep 7   |  [Workshop: Build Servers](https://github.com/CSC-DevOps/Course/blob/master/Workshops/Build.md)       |            |                   |
| Sep 12   | [Analysis](https://docs.google.com/presentation/d/1EkfcbwXko9gvtel0t4GD_cpE4me-OAIwdYt0p_OAeIs/edit#slide=id.p)                         |            |                   |
| Sep 14   | [Workshop: Complexity](https://github.com/CSC-DevOps/Complexity)                |            |                   |
| Sep 19   | [Test Management](https://docs.google.com/presentation/d/1Wv149dt56DAixTn5BqdyHwVxBWyHU1pk5ohL7jlVAWs/edit#slide=id.p)                  |            | |        
| Sep 21   | [Workshop: Test Suites](https://github.com/CSC-DevOps/TestSuites)    |      |    |
| Sep 26   | [Workshop: Fuzzing](https://github.com/CSC-DevOps/Fuzzing) |   |   MILESTONE: TEST/ANALYSIS |
| Sep 28   | [Workshop: Test Generation](https://github.com/CSC-DevOps/TestGeneration)   |   |  HW2   |
| Oct 3   |  [Tech Talks #1](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)  |     |  |
| Oct 5&mdash;6    | Fall Break                       |            |                   |
| Oct 10   | [Infrastructure Management](https://1drv.ms/p/s!AG169vwdL5H_jUY)        |            |                   |
| Oct 12  |  [Tech Talks #2](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                   |     |                   |
| Oct 17   | [Feature Flags/Property Sets/Redis](https://docs.google.com/presentation/d/1cqVz0H4t-b7ZWMEbfBaYJDLSePhMOOjWW04CRzsIY5k/edit#slide=id.p)|            | MILESTONE: DEPLOY |
| Oct 19   | [Workshop: Queues, Caches, Proxies](https://github.com/CSC-DevOps/Queues)|            | HW3       |            
| Oct 24   | [Staging + Deployment](https://docs.google.com/presentation/d/1J3oDEPSGzDGa0B41Ppe8yA02tYicSgstVXHU5mGxU5w/edit#slide=id.g1da8fd6af9_0_196)             |            |                   |
| Oct 26    | [Workshop: Deployment](https://github.com/CSC-DevOps/Deployment/blob/master/README.md)             |            |                   |
| Oct 31   | [Tech Talks #3](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)   |            |                   |
| Nov 2   | [Advanced Docker: Deployment](https://github.com/CSC-DevOps/Course/blob/master/Workshops/AdvancedDocker.md)                    |   | HW4    |
| Nov 7   | [Analysis + Monitoring](https://docs.google.com/presentation/d/1swei7oeXWZGnXe9gC1jlh4Gd1h9Ri6I6x2kTgKr1BVw/edit?usp=sharing)            |            | MILESTONE: SPECIAL|
| Nov 9   | Workshop: Monitoring + Resilience|  [Chaos Engineering](https://www.facebook.com/notes/tpm-networking-group/notes-from-chaos-community-day-nov-4th-2015/1042668315800057)          |                   |
| Nov 14   |  DevOps at Work I   |            |             |
| Nov 16   |  DevOps at Work II  |            |             |
| Nov 21   | [Tech Talks #4](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)          |                   |
| Nov 23   | Thanksgiving                     |            |                   |
| Nov 28   | Demos                     |            |                   |
| Nov 30   | Demos                     |            |                   |
| Dec 5   | Exam (1:00PM - 4:00PM)           |            |                   |
### Resources

[Slack](https://cscdevops-fall2017.slack.com)

##### Papers

* [An empirical study on principles and practices of continuous delivery and deployment](https://peerj.com/preprints/1889.pdf)

##### Books

* [Effective DevOps](https://www.amazon.com/Effective-DevOps-Building-Collaboration-Affinity/dp/1491926309)
* [Ansible: Up and Running](http://www.ansiblebook.com/)
* [Continous Delivery](http://continuousdelivery.com/)
* [Continous Integration](http://www.amazon.com/Continuous-Integration-Improving-Software-Reducing/dp/0321336380)
* [Designing Data-Intensive Applications](http://dataintensive.net/)
* [Systems Performance: Enterprise and the Cloud](http://www.brendangregg.com/sysperfbook.html)
* [The Practice of Cloud System Administration](http://the-cloud-book.com/)
* [DevOps: A Software Architect's Perspective, SEI](http://www.amazon.com/DevOps-Software-Architects-Perspective-Engineering/dp/0134049845)

##### Glossary of Tools

* [http://newrelic.com/devops/toolset](http://newrelic.com/devops/toolset)
