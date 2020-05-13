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

## Schedule and Topics—Summer 2020

*The following schedule is subject to change.*
<!-- 
May 14 Intro (HW0)
May 19 
May 21

May 26 Computing Environments  (HW1)
May 28
Jun 2
Jun 4   

Jun 9 Pipelines  (M1) HW2 
Jun 11
Jun 16 
Jun 18

Jun 23 Test (M2) HW3
Jun 25 
Jun 30
Jul 2

Jul 7  Deploy (M3) HW4
Jul 9
Jul 14
Jul 16 

Jul 21 Ops 
Jul 23

Jul 28 Exam -->

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
|  ➡️       | [Setup](Boot.md)             | 🥾[Engineering Basics](https://github.com/chrisparnin/EngineeringBasics) 🥾
| May 14    | [Intro+Computing Environments](https://docs.google.com/presentation/d/16PWFvEY_qVIbL1FsOgCATIsY-FgUiBaXhw2C1s1anQA/edit)
| May 19    | [Provisioning](https://github.com/CSC-DevOps/Provision) | [Cloud Providers](HW/Cloud-Providers.md) |  
| May 21  | [Continuous Deployment Concepts](https://docs.google.com/presentation/d/1w5QnWQUciQAq-NA12AI14gv6evv6oONnljcPCF29JDY/edit#slide=id.g6d986c4882_1_0) | [Summit I](https://github.com/CSC-DevOps/Course/blob/master/Readings/AdagesI.pdf), [Summit II-III](https://github.com/CSC-DevOps/Course/blob/master/Readings/CACM_DevOps.pdf)  | [HW0](HW/HW0-Provision.md)
| <tr><th colspan=4> 🧱&nbsp;&nbsp;&nbsp;Computing Environments&nbsp;&nbsp;&nbsp; ☢️</th></tr> |
| May 26   | [Virtualization concepts](https://docs.google.com/presentation/d/1VdSRYFxTFvdJvxq4JZMn7itdYJjiutrpj525Kw2JX-U/edit) | | [HW1](HW/HW1-V.md)
| May 28   | [Virtualization Workshop](https://github.com/CSC-DevOps/VM)
| Jun 2  | [Containers/Docker Workshop](https://github.com/CSC-DevOps/Containers)
| Jun 4  | [Configuration Management](https://docs.google.com/presentation/d/1i18CWaZaiBBWPlT71iOuEPYYaZcK1VMvtdynwCLAVU0/edit#slide=id.g6e582f9f77_0_0)
| Jun 7   | [Building Configuration Server](https://github.com/CSC-DevOps/CM) | | [HW2](HW/HW2-mm.md)
|   | [Ansible Playbooks](https://github.com/CSC-DevOps/CM/blob/master/Playbooks.md)
| <tr><th colspan=4> 🚰 &nbsp;&nbsp;&nbsp;Pipelines&nbsp;&nbsp;&nbsp; 🚀</th></tr> |
| Jun 9   | [Pipelines, CI/CD](https://docs.google.com/presentation/d/1vEp14SgKc0hC4-RrjZ1rzFMgK2kr3W7p70ra5_sUOUY/edit) | [Verifying Pipelines](Readings/DesirableProperties.pdf) | [Build Milestone](Project/Pipeline1.md)
| Jun 11   | [Building Basic Pipelines](https://github.com/CSC-DevOps/Pipelines)
| Jun 16   | [Jenkins](https://docs.google.com/presentation/d/1oEJQ953LUQ1rYhRMKL-B262Bx8rkENW2aaAj-2e_N7I/edit#slide=id.p)
| <tr><th colspan=4> 🧪&nbsp;&nbsp;&nbsp;Testing+Analysis&nbsp;&nbsp;&nbsp; ✅</th></tr> |
| Jun 23   | [Testing + Analysis concepts](https://docs.google.com/presentation/d/1PY5D1TAn9W7spSMS--B4zt8JwBXAJY4apx36N9so55I/edit#slide=id.g7e3970db34_0_58)
| Jun 25   | [Fuzzing workshop](https://github.com/CSC-DevOps/Fuzzing)
| Jun 30   | [Test suites analysis and coverage workshop](https://github.com/CSC-DevOps/TestSuites)
| Jul 2    | [Static analysis workshop](https://github.com/CSC-DevOps/Complexity) | | [Test Milestone](Project/Pipeline2.md)
| <tr><th colspan=4> 🚧&nbsp;&nbsp;&nbsp;Infrastructure+Deploy&nbsp;&nbsp;&nbsp; 🏗️</th></tr> |
| Jul 7  | [Infrastructure concepts](https://docs.google.com/presentation/d/1HjPY0979qEVkN7mJhcjxA7LYXubBpHWwj84BcItbzwo/edit#slide=id.g720af242e7_0_5)
| Jul 9   | [Building Caches and Queues with Redis](https://github.com/CSC-DevOps/Caches) | | [HW3](HW/HW3.md)
| Jul 14   | [Deploy Strategies and Feature flags](https://docs.google.com/presentation/d/1O26CMKrFE-UCqV5AQ5VNiCWv3x-XF0IfI0McIhxlMcw/edit)
|     | [Deployment Workshop](https://github.com/CSC-DevOps/Deployment) | | [Deploy Milestone](Project/Pipeline3.md)
| Jul 16    | [Monitoring](https://docs.google.com/presentation/d/1f_yw2KS02Uzt-3qnadk9wjiKS0sgBsxSOpQIxd8YaJ0/edit#slide=id.g73980477ab_0_0)
|     | [Monitoring Workshop](https://github.com/CSC-DevOps/Monitoring) | | [HW4](HW/HW4-monitor.md)
| <tr><th colspan=4> 📈&nbsp;&nbsp;&nbsp;Ops&nbsp;&nbsp;&nbsp; 🧯</th></tr> |
| Jul 21   | [Incidents](https://learning.acm.org/techtalks/reliability) | [Slides](https://learning.acm.org/binaries/content/assets/leaning-center/webinar-slides/2020/oops_techtalk_lorinhochstein_slides.pdf) |
|    | [Incident call](https://www.pagerduty.com/blog/incident-response-reenactment/)
| Jul 23   | [Feature experiments and chaos engineering](https://docs.google.com/presentation/d/1a4BJ0lUkis9x0HQy3YPOaTWw-wJfktwyE3Mw7AnGfmE/edit#slide=id.g74b88b11b0_0_73)
|    | [Chaos engineering workshop](https://github.com/CSC-DevOps/Chaos)
| <tr><th colspan=4> 🎬&nbsp;&nbsp;&nbsp;Closing&nbsp;&nbsp;&nbsp; 💯</th></tr> |
| Jul 28    | Final Exam (6am--23:59pm) |          |                   |

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
