# CSC 591/791 "519" Course Syllabus - DevOps

North Carolina State University

| Information  | &nbsp;                   |
|--------------|--------------------------|
| Instructor   | Dr. Christopher Parnin (cjparnin@ncsu.edu)|
| Readings     | Provided by instructor   |
| Credit-hours | 3                        |

## Prerequisites
CSC510 (Software Engineering) or graduate or senior standing with
at least 3.0 GPA, good knowledge of at least one high
level programming language.

## Outline

Modern software development organizations require entire teams of DevOps to automate  and maintain software engineering processes and infrastructure vital to the organization. In this course, you will gain practical exposure to the skills, tools, and knowledge needed in automating software engineering processes and infrastructure. 
Students will have the chance to build new or extend existing software engineering tools and design a DevOps pipeline.

## Objectives

Students are expected to gain practical exposure to tools, processes, and principles of software engineering through hands-on projects while understanding models and research ideas behind the tools and processes.  Lectures will include workshop style learning experiences, where students get to work on a problemset and receive feedback from the instructor and other classmates.  When possible, guest lectures from industry will help illustrate examples of how the technology is deployed in practice.

## Course Topics

Topics include: Static analysis,  build management, automatic testing, goverance, quality gates, monitoring, and configuration and release management. Additional topics include provisioning, quality assurance, unit testing, test generation, static and dynamic analysis and service, platform, and infrastructure as a service.

## Course Overview

In the course, a mixture of traditional lectures with activities and in-class workshops will be used.  During lectures, we will cover core concepts related to a topic. During the in-class workshops, we will perform sample exercises with relevant tools that reinforce lecture material.  Evaluation will be based on tech talks, homework assignments, workshop attendance, and final project.

### Tech Talks

Students in CSC 591 will organize in groups and present one tech talk during lecture.  For a *tech talk*, students are expected to cover one tool or technology revelant to DevOps in a 15-20 minute presentation.  Students should perform a small demo to help illustrate the tool. Three days during the semester will be reserved for these presentations.

### Homeworks

Homework assignments will be regularly released throughout the semester and reinforce class material.  Homeworks will typically mirror a scenario or common task that a DevOps engineer may face.

### Workshops

Workshops are have required attendance and are vital to the course. During a workshop, you'll be guided in using tools and building specific functionality which you will later use for homeworks and project miles. During the semester, 3 workshops will be randomly selected for attendance. 

* 1 missed workshop, workshop grade = 4
* 2 missed workshops, workshop grade = 2
* 3 missed workshops, workshop grade = 0

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
| Sep 15th  | [Parsing Primer](https://docs.google.com/presentation/d/1PooLd3Bj3cORMyHxLlVV4mXJ52Ra6oFf57FHx23vtDc/edit#slide=id.p)                  |  [Mini-workshop](https://github.com/CSC-DevOps/Parsing)  |  [MILESTONE: BUILD](https://github.com/CSC-DevOps/Course/blob/master/Project/M1.md)     |
| Sep 17th  | [Workshop: Code Complexity](https://github.com/CSC-DevOps/Complexity)            | &nbsp;     |  &nbsp;               |
| Sep 22nd  | [Test Management](https://docs.google.com/presentation/d/1tuGkWE86C-MwajbOVsUgVoJUletVszwhPHecWEd7ZYU/)                  | &nbsp;     |  &nbsp;     |
| Sep 24th  | [Workshop: Test Generation](https://github.com/CSC-DevOps/TestGeneration/blob/master/README.md) | &nbsp;     |  [HW #2 - Test Suite Generation](https://github.com/CSC-DevOps/Course/blob/master/HW/HW2.md) |
| Sep 29th | [Static + Dynamic Analysis](https://docs.google.com/presentation/d/1Bf-9ASmoYrBsiisseGbxMkXCvPyJtB46zP41y7wFKE0/edit)        | [SAGE](http://queue.acm.org/detail.cfm?id=2094081)     |  &nbsp;               |
| Oct 1st | [Workshop: Fuzzing+Minification](https://github.com/CSC-DevOps/Fuzzing)                | &nbsp;     |   |
| Oct 6th | Guest Lecture  | &nbsp;     |  [MILESTONE: TEST+ANALYSIS](https://github.com/CSC-DevOps/Course/blob/master/Project/M2.md)    |
| Oct 8th | ~~~ Fall Break ~~~            | &nbsp;     |  |
| Oct 13th| [Infrastructure Management](https://onedrive.live.com/redir?resid=FF912F1DFCF67A6D%211734)        | [OpenStack](http://www.openstack.org/), [AWS]() | &nbsp;  |
| Oct 15th| [Tech Talks #1](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md) | [NewRelic](https://github.ncsu.edu/ajoshi5/DevOps-TechTalks), [Salt](https://github.com/prashantgupta24/Salt-Stack), [Otto](https://github.com/rarora4/otto-getting-started) | [HW #3 - Infrastructure Fluency](https://github.com/CSC-DevOps/Course/blob/master/HW/HW3.md) |
| Oct 20th | [Feature Flags/Property Sets/Redis](https://docs.google.com/presentation/d/1cqVz0H4t-b7ZWMEbfBaYJDLSePhMOOjWW04CRzsIY5k/) | &nbsp; |
| Oct 22th | [Workshop: Queues, Caches, Proxies](https://github.com/CSC-DevOps/Queues) | &nbsp; |
| Oct 27th |  [Staging + Deployment](https://docs.google.com/presentation/d/1TaiIh6CtkHt-ij8mCVPVrpY0yN2VTVjqfjO_zYX0lEs/edit#slide=id.g2f582368a_0_51)              | &nbsp;     | &nbsp;  | 
| Oct 29th |  [Workshop: Deployment](https://github.com/CSC-DevOps/Deployment)     | &nbsp;     | [HW #4 - Advanced Docker](https://github.com/CSC-DevOps/Course/blob/master/HW/HW4.md) |
| Nov 3rd  |  [Advanced Docker: Deployment + Multiple Containers](https://github.com/CSC-DevOps/Course/blob/master/Workshops/AdvancedDocker.md)                       | &nbsp;   | &nbsp; |
| Nov 5th  |  [Tech Talks #2](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md)         | [SnapCI](https://github.com/KeleiAzz/DevOps-TechTalk), [Mocha](https://github.com/payalsoman/devops-techtalk-mocha), [Kubernetes](https://github.ncsu.edu/jitesh/TechTalk---Kubernetes), [Google App Engine](https://github.com/Shraddha512/TechTalk-GoogleAppEngine)      | [MILESTONE: DEPLOY](https://github.com/CSC-DevOps/Course/blob/master/Project/M3.md#milestone-deployment)  |
| Nov 10th | [Analysis + Monitoring](https://docs.google.com/presentation/d/1swei7oeXWZGnXe9gC1jlh4Gd1h9Ri6I6x2kTgKr1BVw/edit?usp=sharing)          | [Flame Graphs](https://www.usenix.org/conference/lisa13/technical-sessions/plenary/gregg), [Splunk](http://www.splunk.com/), [NewRelic](http://newrelic.com/), [A/B @ Bing](http://www.infoq.com/presentations/controlled-experiments), [Zynga](http://blog.amplitude.com/2015/06/24/zynga-analytics-at-its-peak/)      |
| Nov 12th | [Workshop: Monitoring + Resilience Testing](https://github.com/CSC-DevOps/Monitoring) | [Chaos Monkey](https://github.com/Netflix/SimianArmy) | &nbsp; |
| Nov 17th | [Lorin Hochstein](http://lorinhochstein.org/), Chaos Engineering @ NETFLIX	  | &nbsp;     | &nbsp;                   |
| Nov 19th | [Tech Talks #3](https://github.com/CSC-DevOps/Course/blob/master/TechTalks.md) | [Mesosphere](https://github.com/vinay92/Mesosphere), [BlueMix](https://github.com/kaustubhsant/DevOps-TechTalk), [Nagios](https://github.com/amittal91/DevOps-TechTalk-Nagios), [Puppet](https://github.com/aneeshkher/DevOpsTechTalk) | [MILESTONE: SPECIAL](https://github.com/CSC-DevOps/Course/blob/master/Project/M4.md#milestone-special) | 
| Nov 24th | No class.             | &nbsp;     | &nbsp; |
| Dec 1st | [Demos](https://docs.google.com/spreadsheets/d/18i9fKzY9ewOUUQ0PLF0ijfYAV_XtameItq9OV3Ohs38/edit#gid=0)             | &nbsp;     | &nbsp; |
| Dec 3rd | [Demos](https://docs.google.com/spreadsheets/d/18i9fKzY9ewOUUQ0PLF0ijfYAV_XtameItq9OV3Ohs38/edit#gid=0)             | &nbsp;     | &nbsp; |
| Dec 8th | Final Exam (1-4pm)     | [Study Guide](https://github.com/CSC-DevOps/Course/blob/master/Final.md)     | &nbsp; |

## Resources

##### Books
The following books are not required but may provide useful references.

* [Ansible: Up and Running](http://www.ansiblebook.com/)
* [Continous Delivery](http://continuousdelivery.com/)
* [Continous Integration](http://www.amazon.com/Continuous-Integration-Improving-Software-Reducing/dp/0321336380)
* [Designing Data-Intensive Applications](http://dataintensive.net/)
* [Systems Performance: Enterprise and the Cloud](http://www.brendangregg.com/sysperfbook.html)
* [The Practice of Cloud System Administration](http://the-cloud-book.com/)

## Late Policy
No late assignments will be accepted. Many of your assignments will be collaborative
effort with other members of your group. Thus, late papers by one member
of the group will affect the entire group. The due date for assignments will be
posted on the assignment and will generally be submitted electronically.

## Teaching Philosophy
We will make use of intensive classroom activities and readings. You will be expected to participate actively in discussions. On any given issue, you may be asked to summarize and criticize reading assignments from the text or articles that you have read for your assignments and projects. We view the web as a valuable
resource. Our course website will serve as our ”information system” this semester; you will be expected to visit the site on a daily basis for updates and to obtain your homework / project assignments.
Only you can learn. As the instructors, we can only guide and assist you. Thus, all of the class activities are aimed at helping you learn.

## Academic Integrity
The course will follow all NCSU academic [integrity regulations](http://www.ncsu.edu/provost/academic_policies). All students are expected to maintain traditional standards of academic integrity by giving proper credit for all work. All suspected cases of academic dishonesty will be aggressively pursued. A student shall be guilty of a violation of academic integrity if he or she represents the work of others as his or her own or aid another’s misrepresentation.
Any violation associated with a homework/lab assignment, project
deliverable, examination or quiz will result in a failing grade for the course. Such violations will be reported to the Office of Student Conduct, which may impose penalties beyond those by the instructors.

We encourage you to read the ACM Code of Ethics, particularly Sections 1.3, 1.5, 1.6, 2.2 and 2.4. (http://www.acm.org/constitution/code.html)

## Equity Policy

All persons, regardless of age, race, religion, gender, physical disability or sexual orientation shall have equal opportunity without harassment in this course. Any harassment should be reported immediately to the instructor.

Students are responsible for reviewing the NC State University PRR’s which pertains to their course rights and responsibilities:

#### Equal Opportunity and Non-Discrimination Policy Statement 
https://policies.ncsu.edu/policy/pol-04-25-05 

Additional references at  
https://oied.ncsu.edu/equity/policies/ 

#### Code of Student Conduct 

Students are expected to conduct themselves in a respectful and professional manner at all times. Grades will be adjusted if students do not handle themselves in a respectful and professional manner with all members of the teaching staff and with others in the class - both in person and electronically (email, message board posts).

See more details at:  
https://policies.ncsu.edu/policy/pol-11-35-01

## Students with Disabilities
The course will follow all NCSU regulations relevant to students with disabilities. Any students requiring additional assistance due to disabilities (e.g., learning disabilities), should contact the professor during the first week of the semester. Students requiring extra time for examinations and quizzes are asked to make
arrangements at least three days in advance. You may contact the NCSU Disability Services for Students Office regarding campus services at the Student Health Center for more information and assistance (http://www.ncsu.edu/dso/students/).

## Course Evaluation

Online class evaluations will be available for students to complete during the last two weeks of class. Students will receive an email message directing them to a website where they can login using their Unity ID and complete evaluations. All evaluations are confidential; instructors will never know how any one student responded to any question, and students will never know the ratings for any particular instructors.

| Resources     | &nbsp; |
|---------------|--------|
|Evaluation website:   | https://classeval.ncsu.edu|
|Student help desk:    | classeval@ncsu.edu|
|Info about ClassEval: | http://www2.acs.ncsu.edu/UPA/classeval/index.htm|

## Course Grading

| Category           | Weight |
|--------------------|--------|
| Homework           | 25%    |
| Class workshops    | 5%     |
| Final Exam         | 20%    |
| Tech Talk/Research | 10%    |
| **Final Project**  | 40%    |

The Final Project will be evaluated during each milestone, each worth 10%.

#### Grade Scale

Based on your Weighted Course Average (WCA), you will receive the following letter grade.

| Grade | Range         |
| ----- | ------------- |
| A+    | 97≦WCA        | 
| A     | 93 ≦ WCA < 97 |
| A-    | 90 ≦ WCA < 93 |
| B+    | 87 ≦ WCA < 90 |
| B     | 83 ≦ WCA < 87 |
| B-    | 80 ≦ WCA < 83 |
| C+    | 77 ≦ WCA < 80 |
| C     | 73 ≦ WCA < 77 |
| C-    | 70 ≦ WCA < 73 |
| D+    | 67 ≦ WCA < 70 | 
| D     | 63 ≦ WCA < 67 |
| D-    | 60 ≦ WCA < 63 | 
| F     | WCA < 60      |

See more at:  
https://policies.ncsu.edu/regulation/reg-02-50-03

#### Credit

More information about credit-only courses:
Credit-Only Courses https://policies.ncsu.edu/regulation/reg-02-20-15 
This link will open in a new window
Audits https://policies.ncsu.edu/regulation/reg-02-20-04
