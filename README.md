# DevOps: CSC 591/791-004
-------------------------

Modern software development organizations require entire teams of DevOps to automate  and maintain software engineering processes and infrastructure vital to the organization. In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure. 
Students will have the chance to build new or extend existing software engineering tools and design a DevOps pipeline.

## Course Overview

In the course, a mixture of traditional lectures with activities and in-class workshops will be used.  During lectures, we will cover core concepts related to a topic. During the in-class workshops, we will perform sample exercises with relevant tools that reinforce lecture material.  Evaluation will be based on tech talks, homework assignments, workshop attendance, and final project.

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

## Schedule and Topics - Spring 2015

The following schedule is subject to change.

| Class    | Topics                           |  Resources |  Deadlines |
|----------|----------------------------------|------------| ----------            |
| Jan 8th  | Hello                            | &nbsp;     |  &nbsp;               | 
| Jan 13th | Core Concepts + Skills           | [Slides](https://docs.google.com/presentation/d/1gawFfJyPssbtiLs1-4FGow4Ph1-AHJeEo9B_S8Kvr70/edit)     |  &nbsp;               |
| Jan 15th | Workshop: Git, Branches, Servers | [Site](https://github.ncsu.edu/CSC-DevOps-Spring2015/ServersWorkshop)     |  &nbsp;               |
| Jan 20th | Configuration Management         | [Slides](https://docs.google.com/presentation/d/1sVDyCBwFnb1C0xKTswzmhsNn-FKwCXl434uZkAunI6M/edit#slide=id.g3ab49d3b9_154)     |  &nbsp;               |
| Jan 22nd | [Workshop: Managed Environments](https://github.com/CSC-DevOps/Course/blob/master/Workshops/CM.md)   | [Docker](https://www.docker.com/), [Chef](https://www.chef.io/chef/), [Vagrant](https://www.vagrantup.com/), [Ansible](http://www.ansible.com/get-started)     |  [HW #1 - Provisioning Servers](https://github.com/CSC-DevOps/Course/blob/master/HW/HW1.md) |
| Jan 27th | Build Management                 | [Slides](https://docs.google.com/presentation/d/1KoMQark9bdaNMBpSBfEewjR1qEic_Fi0nJxN6si6BgA/)     |  &nbsp;               |
| Jan 29th | [Workshop: Build Servers](https://github.com/CSC-DevOps/Course/blob/master/Workshops/Build.md)          | [Jenkins](http://jenkins-ci.org/), [CruiseControl](http://cruisecontrol.sourceforge.net/), [GoCd](http://www.go.cd/)     | &nbsp; |
| Feb 3rd  | Test Management                  | [Slides](https://docs.google.com/presentation/d/1tuGkWE86C-MwajbOVsUgVoJUletVszwhPHecWEd7ZYU/)     |  [MILESTONE: BUILD](https://github.com/CSC-DevOps/Course/blob/master/Project/BuildMilestone.md)     |
| Feb 5th  | [Workshop: Test Generation](https://github.com/CSC-DevOps/TestGeneration/blob/master/README.md)            | &nbsp;     |  &nbsp;               |
| Feb 10th | Static + Dynamic Analysis        | [Slides](https://docs.google.com/presentation/d/1Bf-9ASmoYrBsiisseGbxMkXCvPyJtB46zP41y7wFKE0/edit)     |  &nbsp;               |
| Feb 12th | [Workshop: Fuzzing+Minification](https://github.com/CSC-DevOps/Fuzzing)                | &nbsp;     |  [HW #2 - Test Suite Generation](https://github.com/CSC-DevOps/Course/blob/master/HW/HW2.md) |
| Feb 17th | Project Planning (no class)      | &nbsp;     |  &nbsp;               |
| Feb 19th | [Tech Talks #1](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                    | &nbsp;     |  &nbsp;               |
| Feb 24th | Operations + Concepts            | &nbsp;     |  &nbsp;               |
| Feb 26th | [Tech Talks #2](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                    | &nbsp;     |  HW #3 - Mass Refactoring |
| March 3rd| [Infrastructure Management](https://onedrive.live.com/fullscreen?cid=ff912f1dfcf67a6d&id=documents&resid=FF912F1DFCF67A6D%211734&filename=DevOpsInfrastructure.pptx&wx=p&wv=s&wc=officeapps.live.com&wy=y&wdSlideId=273&wdModeSwitchTime=1425393995253)        | [OpenStack](http://www.openstack.org/), [AWS]() | &nbsp;  |
| March 5th| Workshop: Queues, Proxies, Caches| &nbsp;     | [MILESTONE: TEST+ANALYSIS](https://github.com/CSC-DevOps/Course/blob/master/Project/M2.md) |
| March 7th-13th  | ~~~ Spring Break ~~~      | &nbsp;     | &nbsp;                |
| March 17th | Staging Patterns               | &nbsp;     | &nbsp;                |
| March 19th | Workshop: Staging Servers      | &nbsp;     | &nbsp;                |
| March 24th | Deployment                     | &nbsp;     | &nbsp;                |
| March 26th | Workshop: Deflighting          | &nbsp;     | HW #4 - Data Migration                |
| March 31st | [Tech Talks #3](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)                  | &nbsp;     | MILESTONE: DEPLOY     |
| April 2nd  | ~~~ Spring Holiday ~~~         | &nbsp;     | &nbsp;                |
| April 7th  | Analysis + Monitoring          | [Flame Graphs](https://www.usenix.org/conference/lisa13/technical-sessions/plenary/gregg), [Splunk](http://www.splunk.com/), [NewRelic](http://newrelic.com/), [A/B @ Bing](http://www.infoq.com/presentations/controlled-experiments) | &nbsp;                   |
| April 9th  | Workshop: A/B + Resilience Testing | [Chaos Monkey](https://github.com/Netflix/SimianArmy)     | &nbsp;                   |
| April 14th | Auditing              | &nbsp;     | &nbsp;                   |
| April 16th | [Nick Carver, Operations @ Stack Overflow](http://nickcraver.com/blog/)            | &nbsp;     | MILESTONE: SPECIAL       |
| April 21st | TBD/Demos             | &nbsp;     | &nbsp;                   |
| April 23rd | TBD/Demos             | &nbsp;     | HW #5 - Server Inventory |

### Resources

[Piazza Class Forum](https://piazza.com/class/i5dyy1jtzh4yy)

##### Books

* [Ansible: Up and Running](http://www.ansiblebook.com/)
* [Continous Delivery](http://continuousdelivery.com/)
* [Continous Integration](http://www.amazon.com/Continuous-Integration-Improving-Software-Reducing/dp/0321336380)
* [Designing Data-Intensive Applications](http://dataintensive.net/)
* [Systems Performance: Enterprise and the Cloud](http://www.brendangregg.com/sysperfbook.html)
* [The Practice of Cloud System Administration](http://the-cloud-book.com/)

##### Glossary of Tools

* [http://newrelic.com/devops/toolset](http://newrelic.com/devops/toolset)
