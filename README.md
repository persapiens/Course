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

## Schedule and Topics—Spring 2020

Location: Monteith Engineering Research Center, Room 0313, 1:30-2:45pm.

*The following schedule is subject to change.*

Watch [Lecture Videos](https://www.engineeringonline.ncsu.edu/course/csc-519-devops-modern-software-engineering-practices/?display=course-home).

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
|  ➡️       | [Setup](Boot.md)             | 🥾[Engineering Basics](https://github.com/chrisparnin/EngineeringBasics) 🥾
| Jan 7    | [Intro+Computing Environments](https://docs.google.com/presentation/d/16PWFvEY_qVIbL1FsOgCATIsY-FgUiBaXhw2C1s1anQA/edit)
| Jan 9    | [Provisioning](https://github.com/CSC-DevOps/Provision) | [Cloud Providers](HW/Cloud-Providers.md) | [HW0](HW/HW0-Provision.md) 
| <tr><th colspan=4> 🧱&nbsp;&nbsp;&nbsp;Computing Environments&nbsp;&nbsp;&nbsp; ☢️</th></tr> |
| Jan 14   | [Continuous Deployment Concepts](https://docs.google.com/presentation/d/1w5QnWQUciQAq-NA12AI14gv6evv6oONnljcPCF29JDY/edit#slide=id.g6d986c4882_1_0) | [Summit I](https://github.com/CSC-DevOps/Course/blob/master/Readings/AdagesI.pdf), [Summit II-III](https://github.com/CSC-DevOps/Course/blob/master/Readings/CACM_DevOps.pdf)  
| Jan 16   | [Virtualization Workshop](https://github.com/CSC-DevOps/VM)
| Jan 21   | [Virtualization concepts](https://docs.google.com/presentation/d/1VdSRYFxTFvdJvxq4JZMn7itdYJjiutrpj525Kw2JX-U/edit) | | [HW1](HW/HW1-V.md)
| Jan 23   | [Containers/Docker Workshop](https://github.com/CSC-DevOps/Containers)
| <tr><th colspan=4> ⚗️ &nbsp;&nbsp;&nbsp;Configuration Management&nbsp;&nbsp;&nbsp; 🎛️</th></tr> |
| Jan 28  | [CM](https://docs.google.com/presentation/d/1i18CWaZaiBBWPlT71iOuEPYYaZcK1VMvtdynwCLAVU0/edit#slide=id.g6e582f9f77_0_0)
| Jan 30  | [Building Configuration Server](https://github.com/CSC-DevOps/CM) | | [HW2](HW/HW2-mm.md)
| Feb 4   | [Ansible Playbooks](https://github.com/CSC-DevOps/CM/blob/master/Playbooks.md)
| Feb 6   | Slim/Packer
| <tr><th colspan=4> 🚰 &nbsp;&nbsp;&nbsp;Pipelines&nbsp;&nbsp;&nbsp; 🚀</th></tr> |
| Feb 11   | [Pipelines, CI/CD](https://docs.google.com/presentation/d/1vEp14SgKc0hC4-RrjZ1rzFMgK2kr3W7p70ra5_sUOUY/edit) | [Verifying Pipelines](Readings/DesirableProperties.pdf) | [Build Milestone](Project/Pipeline1.md)
| Feb 13   | [Building Basic Pipelines](https://github.com/CSC-DevOps/Pipelines)
| Feb 18   | [Jenkins](https://docs.google.com/presentation/d/1oEJQ953LUQ1rYhRMKL-B262Bx8rkENW2aaAj-2e_N7I/edit#slide=id.p)
| Feb 20   | Project Workday
| <tr><th colspan=4> 🧪&nbsp;&nbsp;&nbsp;Testing+Analysis&nbsp;&nbsp;&nbsp; ✅</th></tr> |
| Feb 25   | [Testing + Analysis concepts](https://docs.google.com/presentation/d/1PY5D1TAn9W7spSMS--B4zt8JwBXAJY4apx36N9so55I/edit#slide=id.g7e3970db34_0_58)
| Feb 27   | [Fuzzing workshop](https://github.com/CSC-DevOps/Fuzzing)
| Mar 3    | [Test suites analysis and coverage workshop](https://github.com/CSC-DevOps/TestSuites)
| Mar 5    | [Static analysis workshop](https://github.com/CSC-DevOps/Complexity) | | [Test Milestone](Project/Pipeline2.md)
| Mar 9--19| 🌱SPRING BREAK 🌱
| <tr><th colspan=4> 🚧&nbsp;&nbsp;&nbsp;Infrastructure+Deploy&nbsp;&nbsp;&nbsp; 🏗️</th></tr> |
| Mar 24   | [Infrastructure concepts](https://docs.google.com/presentation/d/1HjPY0979qEVkN7mJhcjxA7LYXubBpHWwj84BcItbzwo/edit#slide=id.g720af242e7_0_5)
| Mar 26   | [Building Caches and Queues with Redis](https://github.com/CSC-DevOps/Caches) | | [HW3](HW/HW3.md)
| Mar 31   | Deploy Strategies and feature flags
| Apr 2    | Clusters
| <tr><th colspan=4> 📈&nbsp;&nbsp;&nbsp;Ops&nbsp;&nbsp;&nbsp; 🧯</th></tr> |
| Apr 7    | Monitoring
| Apr 9    | Monitoring
| Apr 14   | Incidents
| Apr 16   | Incidents
| Apr 21   | Resilience engineering
| Apr 23   | Chaos engineering
| <tr><th colspan=4> 🎬&nbsp;&nbsp;&nbsp;Closing&nbsp;&nbsp;&nbsp; 💯</th></tr> |
| May 5    | Final Exam (1:00--4:00pm)|          |                   |

### Project

The primary objective of the course will be to allow students to gain experience in incrementally building a continous delivery pipeline from scratch.  Throughout the semester, students are expected to complete a component of the pipeline by each milestone deadline.

#### Milestones

Details on requirements for milestones will be released throughout the course.  A student's pipeline should demonstrate the following components by the milestone deadline:

[ CM ] -> [ BUILD+TEST+ANALYSIS ] -> [ DEPLOY ] -> [ SPECIAL ]

### Communication channels

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

* [Spring 2019](https://github.com/CSC-DevOps/Course/tree/Spring2019)
* [Spring 2018](https://github.com/CSC-DevOps/Course/tree/Spring2018)
* [Fall 2017](https://github.com/CSC-DevOps/Course/tree/Fall2017)
* [Spring 2017](https://github.com/CSC-DevOps/Course/tree/Spring2017)
* [Fall 2016](https://github.com/CSC-DevOps/Course/tree/Fall2016)
* [Spring 2015 ](https://github.com/CSC-DevOps/Course/tree/Spring2015)
* [Fall 2015 ](https://github.com/CSC-DevOps/Course/tree/Fall2015)
