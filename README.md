# DevOps: CSC 591/791-007
-------------------------

Modern software development organizations require entire teams of DevOps to automate  and maintain software engineering processes and infrastructure vital to the organization. In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure. 
Students will have the chance to build new or extend existing software engineering tools and design a DevOps pipeline.

Past versions:
* [Spring 2015 ](https://github.com/CSC-DevOps/Course/tree/Spring2015)

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

| Class    | Topics                           |  Resources |  Deadlines |
|----------|----------------------------------|------------| ----------            |
| Aug 20th  | Hello                            | [Previous Demos](https://docs.google.com/spreadsheets/d/1BdqdwARU_VVfLXXCQSp6gMiggDYUfsrVgxUQeOJMu68/edit#gid=0)     |  &nbsp;               | 
| Aug 25th | [Core Concepts + Skills](https://docs.google.com/presentation/d/1gawFfJyPssbtiLs1-4FGow4Ph1-AHJeEo9B_S8Kvr70/edit)           | &nbsp;     |  &nbsp;               |
| Aug 27th | [Workshop: Git, Branches, Servers, Hooks](https://github.ncsu.edu/CSC-DevOps-Spring2015/ServersWorkshop) (*internal link*) | &nbsp; |  [HW #0 - Hooks](https://github.com/CSC-DevOps/Course/blob/master/HW/HW0.md)               |
| Sep 1st | [Configuration Management](https://docs.google.com/presentation/d/1sVDyCBwFnb1C0xKTswzmhsNn-FKwCXl434uZkAunI6M/edit#slide=id.g3ab49d3b9_154)         | &nbsp;     |  &nbsp;  |
| Sep 3rd | [Workshop: Managed Environments](https://github.com/CSC-DevOps/Course/blob/master/Workshops/CM.md)   | [Docker](https://www.docker.com/), [Chef](https://www.chef.io/chef/), [Vagrant](https://www.vagrantup.com/), [Ansible](http://www.ansible.com/get-started)     |  [HW #1 - Provisioning Servers](https://github.com/CSC-DevOps/Course/blob/master/HW/HW1.md) |
| Sep 8th | [Build Management](https://docs.google.com/presentation/d/1KoMQark9bdaNMBpSBfEewjR1qEic_Fi0nJxN6si6BgA/)                  | &nbsp;    |  &nbsp;               |
| Sep 10th | [Workshop: Build Servers](https://github.com/CSC-DevOps/Course/blob/master/Workshops/Build.md)          | [Jenkins](http://jenkins-ci.org/), [CruiseControl](http://cruisecontrol.sourceforge.net/), [GoCd](http://www.go.cd/)     | &nbsp; |
| Sep 15th  | Parsing + Static Analysis                  |      |  [MILESTONE: BUILD](https://github.com/CSC-DevOps/Course/blob/master/Project/BuildMilestone.md)     |
| Sep 17th  | [Workshop: Code Complexity]()            | &nbsp;     |  &nbsp;               |
| Sep 22nd  | [Test Management](https://docs.google.com/presentation/d/1tuGkWE86C-MwajbOVsUgVoJUletVszwhPHecWEd7ZYU/)                  | &nbsp;     |  &nbsp;     |
| Sep 24th  | [Workshop: Test Generation](https://github.com/CSC-DevOps/TestGeneration/blob/master/README.md) | &nbsp;     |  [HW #2 - Test Suite Generation](https://github.com/CSC-DevOps/Course/blob/master/HW/HW2.md) |
| Sep 29th | [Static + Dynamic Analysis](https://docs.google.com/presentation/d/1Bf-9ASmoYrBsiisseGbxMkXCvPyJtB46zP41y7wFKE0/edit)        | [SAGE](http://queue.acm.org/detail.cfm?id=2094081)     |  &nbsp;               |
| Oct 1st | [Workshop: Fuzzing+Minification](https://github.com/CSC-DevOps/Fuzzing)                | &nbsp;     |   |
| Oct 6th | [Tech Talks #1](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)  | &nbsp;     |  [MILESTONE: TEST+ANALYSIS](https://github.com/CSC-DevOps/Course/blob/master/Project/M2.md)    |
| Oct 8th | ~~~ Fall Break ~~~            | &nbsp;     |  |
| Oct 13th| [Infrastructure Management](https://onedrive.live.com/redir?resid=FF912F1DFCF67A6D%211734)        | [OpenStack](http://www.openstack.org/), [AWS]() | &nbsp;  |
| Oct 15th| [Tech Talks #2](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md) | &nbsp; | [HW #3 - Infrastructure Fluency](https://github.com/CSC-DevOps/Course/blob/master/HW/HW3.md) |
| Oct 20th | Feature Flags/Property Sets/Redis | &nbsp; |
| Oct 22th | [Workshop: Queues, Caches, Proxies](https://github.com/CSC-DevOps/Queues) | &nbsp; |
| Oct 27th |  [Staging + Deployment](https://docs.google.com/presentation/d/1TaiIh6CtkHt-ij8mCVPVrpY0yN2VTVjqfjO_zYX0lEs/edit#slide=id.g2f582368a_0_51)              | &nbsp;     | &nbsp;  | 
| Oct 29th |  [Workshop: Deployment](https://github.com/CSC-DevOps/Deployment)     | &nbsp;     | [HW #4 - Data Migration](https://github.com/CSC-DevOps/Course/blob/master/HW/HW4.md) |
| Nov 3rd  |  Advanced Deployment Architectures                       | &nbsp;   | &nbsp; |
| Nov 5th  |  [Tech Talks #3](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)         | &nbsp;     | [MILESTONE: DEPLOY](https://github.com/CSC-DevOps/Course/blob/master/Project/M3.md#milestone-deployment)  |
| Nov 10th | [Analysis + Monitoring](https://docs.google.com/presentation/d/1swei7oeXWZGnXe9gC1jlh4Gd1h9Ri6I6x2kTgKr1BVw/edit?usp=sharing)          | [Flame Graphs](https://www.usenix.org/conference/lisa13/technical-sessions/plenary/gregg), [Splunk](http://www.splunk.com/), [NewRelic](http://newrelic.com/), [A/B @ Bing](http://www.infoq.com/presentations/controlled-experiments), [Zynga](http://blog.amplitude.com/2015/06/24/zynga-analytics-at-its-peak/)      |
| Nov 12th | [Workshop: Monitoring + Resilience Testing](https://github.com/CSC-DevOps/Monitoring) | [Chaos Monkey](https://github.com/Netflix/SimianArmy) | &nbsp; |
| Nov 17th | [Lorin Hochstein](http://lorinhochstein.org/), Chaos Engineering @ NETFLIX	  | &nbsp;     | &nbsp;                   |
| Nov 19th | [Auditing](https://docs.google.com/presentation/d/1lfx-hseYOuriY1STi7Cdtgbd1-LqMmqIxsaWh6ZT5y0/edit)/[Tech Talks #4](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md) | &nbsp; | [MILESTONE: SPECIAL](https://github.com/CSC-DevOps/Course/blob/master/Project/M4.md#milestone-special) | 
| Nov 24th | No class.             | &nbsp;     | &nbsp; |
| Dec 1st | [Demos](https://docs.google.com/spreadsheets/d/1BdqdwARU_VVfLXXCQSp6gMiggDYUfsrVgxUQeOJMu68/edit?usp=sharing)             | &nbsp;     | &nbsp; |
| Dec 3rd | [Demos](https://docs.google.com/spreadsheets/d/1BdqdwARU_VVfLXXCQSp6gMiggDYUfsrVgxUQeOJMu68/edit?usp=sharing)             | &nbsp;     | &nbsp; |
| Dec 8th | Final Exam (1-4pm)     | &nbsp;     | &nbsp; |


### Resources

[Slack](https://csc-devops.slack.com/)

##### Books

* [Ansible: Up and Running](http://www.ansiblebook.com/)
* [Continous Delivery](http://continuousdelivery.com/)
* [Continous Integration](http://www.amazon.com/Continuous-Integration-Improving-Software-Reducing/dp/0321336380)
* [Designing Data-Intensive Applications](http://dataintensive.net/)
* [Systems Performance: Enterprise and the Cloud](http://www.brendangregg.com/sysperfbook.html)
* [The Practice of Cloud System Administration](http://the-cloud-book.com/)
* [DevOps: A Software Architect's Perspective, SEI](http://www.amazon.com/DevOps-Software-Architects-Perspective-Engineering/dp/0134049845)

##### Glossary of Tools

* [http://newrelic.com/devops/toolset](http://newrelic.com/devops/toolset)
