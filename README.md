# DevOps: CSC 591/791-008
-------------------------

Modern software development organizations require entire teams of DevOps to automate  and maintain software engineering processes and infrastructure vital to the organization. In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure. 
Students will have the chance to build new or extend existing software engineering tools and design a DevOps pipeline.

Past versions:
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

## Schedule and Topics - Fall 2015

The following schedule is subject to change.

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
| Aug 18   | Core Concepts + Skills           |            | [HW0](https://github.com/CSC-DevOps/Course/blob/master/HW/HW0.md)               |
| Aug 23   | Bootcamp: Basics                 |            |                   |
| Aug 25   | Workshop: Provisioning           |            | HW1               |
| Aug 30   | Configuration Management	        |            |                   |
| Sep  1   | Workshop: Managed Environments   |            |                   |
| Sep  6   | Build Management                 |            | MILESTONE: BUILD  |
| Sep  8   | Workshop: Build Servers          |            |                   |
| Sep 13   | Analysis                         |            |                   |
| Sep 15   | Workshop: Fuzzing                |            |                   |
| Sep 20   | Test Management                  |            |MILESTONE:TEST/ANALYSIS|        
| Sep 22   | Workshop: Test Generation        |            | HW2               |
| Sep 27   | TBD                              |            |                   |
| Sep 29   | TBD                              |            |                   |
| Oct  4   | No class                         |            |                   |
| Oct  6   | Fall Break                       |            |                   |
| Oct 11   | Infrastructure Management        |            |                   |
| Oct 13   | Tech Talks #1                    |            |                   |
| Oct 18   | Feature Flags/Property Sets/Redis|            | MILESTONE: DEPLOY |
| Oct 20   | Workshop: Queues, Caches, Proxies|            | HW3               |            
| Oct 25   | Staging + Deployment             |            |                   |
| Oct 27   | Workshop: Deployment             |            |                   |
| Nov  1   | Advanced Docker: Deployment      |            |                   |
| Nov  3   | Tech Talks #2                    |            | HW4               |
| Nov  8   | Analysis + Monitoring            |            | MILESTONE: SPECIAL|
| Nov 10   | Workshop: Monitoring + Resilience|            |                   |
| Nov 15   | TBD/Guest                        |            |                   |
| Nov 17   | TBD/Guest                        |            |                   |
| Nov 22   | Tech Talks #3                    |            |                   |
| Nov 24   | Thanksgiving                     |            |                   |
| Nov 29   | Demos                            |            |                   |
| Dec  1   | Demos                            |            |                   |
| Dec  6   | Exam (8:00AM--10:00AM)           |            |                   |

### Resources

[Slack](https://csc-devopsfall16.slack.com)

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
