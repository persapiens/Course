# DevOps: CSC 519
-------------------------

In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure necessary for continuous deployment of software. Students will have the chance to build new or extend existing software engineering tools and design an automated deployment pipeline.

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

#### Milestones

Details on requirements for milestones will be released throughout the course.  A student's pipeline should demonstrate the following components by the milestone deadline:

[ CM ] -> [ BUILD+TEST+ANALYSIS ] -> [ DEPLOY ] -> [ SPECIAL ]

## Schedule and Topics—Spring 2019

Location: Engineering Building I, Room 1005, 10:15--11:30am.

*The following schedule is subject to change.*

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
| Jan 7    | [Pipeline Basics](https://github.com/CSC-DevOps/Pipelines) | [Get a Handle on the Basics](https://github.com/chrisparnin/EngineeringBasics)           |  [HW0](HW/HW0-Pipelines.md)                  |
| Jan 9    | Computing Environments | | |
| Jan 14   | [Core Concepts](https://docs.google.com/presentation/d/1-LyXc798R08AaPQI4yCVCCVZryP0kgQY5KqQgzAfmuc/edit#slide=id.g24e9a36457_3_292) |  [Summit I](https://github.com/CSC-DevOps/Course/blob/master/Readings/AdagesI.pdf), [Summit II-III](https://github.com/CSC-DevOps/Course/blob/master/Readings/CACM_DevOps.pdf)        |
| Jan 16   | [Provisioning workshop](https://github.com/CSC-DevOps/Provision) |   |[HW1](HW/HW1-A.md) |
| Jan 21   | No class         |            |                |
| Jan 23   | [Configuration Management](https://docs.google.com/presentation/d/1PO_QTieMkRvW9MDEIMVS0dD5bk50fK5fvSgj5zNyPfw/edit#slide=id.g117c3bc2e1_0_0)  |             | 
| Jan 28   | [Ansible](https://github.com/CSC-DevOps/CM#configuration-management-workshop)                   |            |                [HW2](HW/HW2-mm.md)   |
| Jan 30   | ... | |
| Feb 4    | [Build](https://docs.google.com/presentation/d/1PeI-RbsisPtC8tbKMgtB3IDlffLjE6obQkp-tL0Cmsw/edit#slide=id.g1a769f3281_0_0)                          |            | [CM+Build Milestone](Project/CM.md) |
| Feb 6    | [Build server workshop]()            |            |                   |
| Feb 11   | [Test Management](https://docs.google.com/presentation/d/1Wv149dt56DAixTn5BqdyHwVxBWyHU1pk5ohL7jlVAWs/edit)         |            |                   |
| Feb 13   | [Suites](https://github.com/CSC-DevOps/TestSuites)               |            |                   |
| Feb 18   | [Fuzzing](https://github.com/CSC-DevOps/Fuzzing)                 |            |  |
| Feb 20   | Team Work Day           |            |         |
| Feb 25   | [Analysis](https://docs.google.com/presentation/d/1EkfcbwXko9gvtel0t4GD_cpE4me-OAIwdYt0p_OAeIs/edit)                |            |  [Test+Analysis Milestone](Project/BuildTestAnalysis.md)                 |
| Feb 27   | Complexity              |            |                   |
| Mar 4    | Deploy                  |            |                   |
| Mar 6    | Deploy Strategies       |            |                   |
| Mar 11   | SPRING                  |            |                   |
| Mar 15   | BREAK                   |            |                   |
| Mar 18   | Operation Concepts      |            |   DEPLOY+INFRA Milestone            |
| Mar 20   | Feature Flags/Redis     |            |                |
| Mar 25   |                         |            |                   |
| Mar 27   |                         |            |                   |
| Apr 1    | Monitoring/Analysis     |            |                   |
| Apr 3    | Monitoring Workshop     |            |                   |
| Apr 8    | Chaos Engineering       |  [Notes on Resilience Engineering](https://github.com/lorin/resilience-engineering)          |    SPECIAL MILESTONE               |
| Apr 10   | Chaos Workshop          |            |                   |
| Apr 15   | Tech Talks              |            |                   |
| Apr 17   | Tech Talks              |            |                   |
| Apr 22   | Demos                   |            |                   |
| Apr 24   | Demos                   |            |                   |
| May 1    | Final Exam (8:00--11:00am)|          |                   |

### Resources

* [Mattermost](https://chat.alt-code.org)  
* [NC State - Stack Overflow](https://stackoverflow.com/c/ncsu/)

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

## Past versions

* [Spring 2018](https://github.com/CSC-DevOps/Course/tree/Spring2018)
* [Fall 2017](https://github.com/CSC-DevOps/Course/tree/Fall2017)
* [Spring 2017](https://github.com/CSC-DevOps/Course/tree/Spring2017)
* [Fall 2016](https://github.com/CSC-DevOps/Course/tree/Fall2016)
* [Spring 2015 ](https://github.com/CSC-DevOps/Course/tree/Spring2015)
* [Fall 2015 ](https://github.com/CSC-DevOps/Course/tree/Fall2015)
