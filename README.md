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

## Schedule and Topics—Spring 2021

*The following schedule is subject to change.*

<!-- 
Jan 19 (HW0)
Jan 21 
Jan 26 
Jan 28

Feb 2 Computing Environments [M1] (HW1) 
Feb 4
Feb 11  
Feb 16
Feb 18

Feb 23 Pipelines (M2) HW2
Feb 25
Mar 2
Mar 4

Mar 9  Test  HW3
Mar 11
Mar 16
Mar 18

Mar 23 Infrastructure (M3) HW4 
Mar 25
Mar 30
Apr 1

Apr 6  Deploy HW5
Apr 8
Apr 13
Apr 15

Apr 20  Ops/Chaos
Apr 22
Apr 27
Apr 29

May 6 (Thursday) Exam -->

| Class    | Topics                           |  Resources | Assignments       |
|----------|----------------------------------|------------| ----------------  |
|  ➡️      | [Setup](Boot.md) 
| Jan 19  | [Intro](https://drive.google.com/file/d/1ieVJug_pqDZjZyATphZ6s16c2oNVhxGc/view?usp=sharing) | | [HW0](HW/HW0-Z.md) 
| Jan 21  | [Basics workshop](https://github.com/chrisparnin/EngineeringBasics) 🥾 
| Jan 26  | [What's DevOps?](https://drive.google.com/file/d/195ZTHWSdExT4crsfm7K47N6Fk5BqP8Bn/view?usp=sharing)—[History](https://drive.google.com/file/d/1vUti511jC2R9zXTlSgpw6Ssx7JrP8IrO/view?usp=sharing) | [Summit I](https://github.com/CSC-DevOps/Course/blob/master/Readings/AdagesI.pdf), [Summit II-III](https://github.com/CSC-DevOps/Course/blob/master/Readings/CACM_DevOps.pdf)  |
| Jan 28  | [Cloud Provisioning Workshop](https://github.com/CSC-DevOps/Provision) [📓](https://docable.cloud/chrisparnin/notebooks/provision/do.md) | [Cloud Providers](HW/Cloud-Providers.md) 
| <tr><th colspan=4> 🧱&nbsp;&nbsp;&nbsp;Computing Environments&nbsp;&nbsp;&nbsp; ☢️</th></tr> |
| Feb 2  | [Computing environments](https://drive.google.com/file/d/1JHVo22qVY1H6pm71aDhByaLCh5eYSnhR/view?usp=sharing) | | [HW1](HW/HW1-V.md)
| Feb 4  | [Virtualization Workshop](https://github.com/CSC-DevOps/VM)
| Feb 9   | 😴
| Feb 11  | [Containers/Docker Workshop](https://github.com/CSC-DevOps/Containers)
| Feb 16  | [Configuration Management](https://drive.google.com/file/d/1UXvPSku5R2_Ls_Hl75ukHJ53OtWOjpBF/view?usp=sharing) | | [HW2](HW/HW2-cm.md)
| Feb 18  | [Building Configuration Server](https://github.com/CSC-DevOps/CM)
| Feb 23  | [Ansible Playbooks (Part 3)](https://github.com/CSC-DevOps/CM/blob/master/Playbooks.md)
| <tr><th colspan=4> 🚰 &nbsp;&nbsp;&nbsp;Pipelines&nbsp;&nbsp;&nbsp; 🚀</th></tr> |
| Feb 25  | [Pipelines, CI/CD](https://drive.google.com/file/d/110EJzu-hNUOxDIhmjftraqo68RRvFhC-/view?usp=sharing) | [Verifying Pipelines](Readings/DesirableProperties.pdf) | 💎 [Build Milestone](Project/Pipeline1.md), [HW3](HW/HW3-P.md)
| Mar 2   | [Building Basic Pipelines](https://github.com/CSC-DevOps/Pipelines)
| Mar 4   | [Jenkins](https://github.com/CSC-DevOps/Jenkins)
| <tr><th colspan=4> 🧪&nbsp;&nbsp;&nbsp;Testing+Analysis&nbsp;&nbsp;&nbsp; ✅</th></tr> |
| Mar 9   | Testing + Analysis concepts | | [HW4](HW/HW4-TA.md)
| Mar 11   | [Coverage workshop](https://github.com/CSC-DevOps/TestNAnalysis) ; [Fuzzing workshop](https://github.com/CSC-DevOps/Fuzzing)
| Mar 16   | [Test suites analysis](https://github.com/CSC-DevOps/TestSuites)  | | 💎[Test Milestone[Project/Pipeline2.md]
| Mar 18   | [Static analysis workshop](https://github.com/CSC-DevOps/Complexity)
| <tr><th colspan=4> 🚧&nbsp;&nbsp;&nbsp;Infrastructure&nbsp;&nbsp;&nbsp; 🏗️</th></tr> |
| Mar 23   | Infrastructure concepts | | HW5
| Mar 25  | Building Caches and Queues with Redis
| Mar 30  | TBA
| Apr 1   | TBA
| <tr><th colspan=4> 📦&nbsp;&nbsp;&nbsp;Deploy&nbsp;&nbsp;&nbsp; 🛎️</th></tr> |
| Apr 6   | Deploy Strategies and Feature flags | |  💎Deploy Milestone, HW6
| Apr 8    | Deployment Workshop
| Apr 13    | Monitoring
| Apr 15    | Monitoring Workshop
| <tr><th colspan=4> 📈&nbsp;&nbsp;&nbsp;Ops&nbsp;&nbsp;&nbsp; 🧯</th></tr> |
| Apr 20   | [Incidents](https://learning.acm.org/techtalks/reliability) | [Slides](https://learning.acm.org/binaries/content/assets/leaning-center/webinar-slides/2020/oops_techtalk_lorinhochstein_slides.pdf) |
| Apr 22   | [Incident call](https://www.pagerduty.com/blog/incident-response-reenactment/)
| Apr 27   | Feature experiments and chaos engineering
| Apr 29   | Chaos engineering workshop
| <tr><th colspan=4> 🎬&nbsp;&nbsp;&nbsp;Closing&nbsp;&nbsp;&nbsp; 💯</th></tr> |
| May 6    | Final Exam (6am--23:59pm) |          |                   |

### Project

The primary objective of the course will be to allow students to gain experience in incrementally building a continous delivery pipeline from scratch.  Throughout the semester, students are expected to complete a component of the pipeline by each milestone deadline.

#### Milestones

Details on requirements for milestones will be released throughout the course.  A student's pipeline should demonstrate the following components by the milestone deadline:

[ CM ] -> [ BUILD+TEST+ANALYSIS ] -> [ DEPLOY ] -> [ SPECIAL ]

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

* [Spring 2020](https://github.com/CSC-DevOps/Course/tree/Spring2020)
* [Spring 2019](https://github.com/CSC-DevOps/Course/tree/Spring2019)
* [Spring 2018](https://github.com/CSC-DevOps/Course/tree/Spring2018)
* [Fall 2017](https://github.com/CSC-DevOps/Course/tree/Fall2017)
* [Spring 2017](https://github.com/CSC-DevOps/Course/tree/Spring2017)
* [Fall 2016](https://github.com/CSC-DevOps/Course/tree/Fall2016)
* [Spring 2015 ](https://github.com/CSC-DevOps/Course/tree/Spring2015)
* [Fall 2015 ](https://github.com/CSC-DevOps/Course/tree/Fall2015)
