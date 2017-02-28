# DevOps: CSC 519
-------------------------

Modern software development organizations require entire teams of DevOps to automate  and maintain software engineering processes and infrastructure vital to the organization. In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure. 
Students will have the chance to build new or extend existing software engineering tools and design a DevOps pipeline.

Past versions:
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


### Tech Talks

Students in CSC 591 will organize in groups and present one tech talk during lecture.  For a *tech talk*, students are expected to cover one tool or technology revelant to DevOps in a 15-20 minute presentation.  Students should perform a small demo to help illustrate the tool. Three days during the semester will be reserved for these presentations.

### Homeworks

Homework assignments will be regularly released throughout the semester and reinforce class material.  Homeworks will typically mirror a scenario or common task that a DevOps engineer may face.

### Project

The primary objective of the course will be to allow students to gain experience in incrementally building a continous delivery pipeline from scratch.  Throughout the semester, students are expected to complete a component of the pipeline by each milestone deadline.  Students in CSC 791 are expected to implement a research component to their pipline. 

Students are able to choose their own app and technology choices for building a deployment pipeline.  Otherwise, a default app and technology stack will be provided.

##### Milestones

Details on requirements for milestones will be released throughout the course.  A student's pipeline should demonstrate the following components by the milestone deadline:

* BUILD
* TEST+ANALYSIS
* DEPLOY
* SPECIAL

## Schedule and Topics - Fall 2016

The following schedule is subject to change.

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
| Jan 10   | [Core Concepts](http://tiny.cc/CSC-DevOpsCore) |  [Adages](https://github.com/CSC-DevOps/Course/blob/master/Readings/AdagesI.pdf)          | [HW0](https://github.com/CSC-DevOps/Course/blob/master/HW/HW0.md) |
| Jan 12   | [Bootcamp: Basics](https://github.com/CSC-DevOps/Bootcamp)  |            |                   |
| Jan 17   | Workshop: Provisioning           |            | [HW1](https://github.com/CSC-DevOps/Course/blob/master/HW/HW1.md)|
| Jan 19   | [Configuration Management](http://tiny.cc/devops-cm-slides) |            |                   |
| Jan 24   | [Workshop: Managed Environments](https://github.com/CSC-DevOps/CM/blob/master/README.md)   |            |                   |
| Jan 26   | [Build Management](https://docs.google.com/presentation/d/1PeI-RbsisPtC8tbKMgtB3IDlffLjE6obQkp-tL0Cmsw/edit#slide=id.p)                 |            | [MILESTONE: BUILD](https://github.com/CSC-DevOps/Course/blob/master/Project/M1.md)  |
| Jan 31   | [Workshop: Build Servers](https://github.com/CSC-DevOps/Course/blob/master/Workshops/Build.md)          |            |                   |
| Feb 2   | [Analysis](https://docs.google.com/presentation/d/1EkfcbwXko9gvtel0t4GD_cpE4me-OAIwdYt0p_OAeIs/edit#slide=id.p)                         |            |                   |
| Feb 7   | [Workshop: Complexity](https://github.com/CSC-DevOps/Complexity)                |            |                   |
| Feb 9   | [Test Management](https://docs.google.com/presentation/d/1Wv149dt56DAixTn5BqdyHwVxBWyHU1pk5ohL7jlVAWs/edit#slide=id.p)                  |            |[MILESTONE:TEST/ANALYSIS](https://github.com/CSC-DevOps/Course/blob/master/Project/M2.md)|        
| Feb 14   | No class                         |            |                   |
| Feb 16   | [Workshop: Fuzzing](https://github.com/CSC-DevOps/Fuzzing)        |            | [HW2](https://github.com/CSC-DevOps/Course/blob/master/HW/HW2.md)               |
| Feb 21   | [Workshop: Test Generation](https://github.com/CSC-DevOps/TestGeneration)                              |            |                   |
| Feb 23   | [Workshop: Test Suites]()                        |            |                   |
| Feb 28   |                        |            |                   |
| Mar 2    | Midterm Review                       |            |                   |
| Mar 7    | Spring Break                       |            |                   |
| Mar 14   | [Infrastructure Management](https://1drv.ms/p/s!AG169vwdL5H_jUY)        |            |                   |
| Mar 16   | [Tech Talks #1](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                    |     |                   |
| Mar 21   | Feature Flags/Property Sets/Redis|            | [MILESTONE: DEPLOY](https://github.com/CSC-DevOps/Course/blob/master/Project/M3.md) |
| Mar 23   | [Workshop: Queues, Caches, Proxies](https://github.com/CSC-DevOps/Queues)|            | [HW3](https://github.com/CSC-DevOps/Course/blob/master/HW/HW3.md)               |            
| Mar 28   | [Staging + Deployment](https://docs.google.com/presentation/d/1TaiIh6CtkHt-ij8mCVPVrpY0yN2VTVjqfjO_zYX0lEs/edit#slide=id.p)             |            |                   |
| Mar 30    | [Workshop: Deployment](https://github.com/CSC-DevOps/Deployment/blob/master/README.md)             |            |                   |
| Apr 4   | [Advanced Docker: Deployment](https://github.com/CSC-DevOps/Course/blob/master/Workshops/AdvancedDocker.md)      |            |                   |
| Apr 6   | [Tech Talks #2](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                    |   | [HW4](https://github.com/CSC-DevOps/Course/blob/master/HW/HW4.md)    |
| Apr 11   | [Analysis + Monitoring](https://docs.google.com/presentation/d/1swei7oeXWZGnXe9gC1jlh4Gd1h9Ri6I6x2kTgKr1BVw/edit?usp=sharing)            |            | [MILESTONE: SPECIAL](https://github.com/CSC-DevOps/Course/blob/master/Project/M4.md)|
| Apr 13   | Workshop: Monitoring + Resilience|  [Chaos Engineering](https://www.facebook.com/notes/tpm-networking-group/notes-from-chaos-community-day-nov-4th-2015/1042668315800057)          |                   |
| Apr 18   | TBD/Guest                        |            |                   |
| Apr 20   | [Tech Talks #3](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                    |                         |            |                   |
| Apr 25   | Demos          |                   |
| Apr 28   | Demos                     |            |                   |
| May 2nd   | Exam (8:00AM - 11:00AM)           |            |                   |

### Resources

[Slack](https://csc519-s17.slack.com/)

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
