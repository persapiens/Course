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

## Schedule and Topics—Spring 2022

📹 [Live stream and recorded videos](https://ncsu.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx#folderID=36084064-ad92-4b46-a9d0-adff0182a317)

*The following schedule is subject to change.*

| Class    | Topics                           |  Activities | Assignments       |
|----------|----------------------------------|------------| ----------------  |
|  ➡️       | [Setup](https://devops.docable.cloud/chrisparnin/v/61a94512048892b30f3add22)
| Jan 10   | [Intro](https://docs.google.com/presentation/d/1u17QwNV-msmyFp2WvRciVr_qTnuiT2z5WePoVERsCFE/edit?usp=sharing)
|          | _Course overview_                  | Passing opunit checks 
| Jan 12   | [Basics](Content/Basics/README.md) | Basics workshop | [HW-Basics](HW/HW-Basics.md)
|          | _Terminals, making windows awesome, package managers, shells_  | Customize your prompt, install the things | 
|          | _markdown, git, virtualization, kanban_       |
| Jan 17   | No class
| Jan 19   | Basics continued; [What's DevOps?](https://docs.google.com/presentation/d/1pdykQwiow19pw9ipN7YnqMQ6Nk6Wj_huDM0huZdURBk/edit#slide=id.gb1b1a3196c_1_3)
| <tr><th colspan=4> 🧱&nbsp;&nbsp;&nbsp;Computing Environments&nbsp;&nbsp;&nbsp; ☢️</th></tr> |
| Jan 24   | [Computing Environments](https://docs.google.com/presentation/d/1McFvP0k3o1hhn-0CxQfURYm3H9RQa6dcLxqUuqavF04/edit?usp=sharing)
|          | _Headless infrastructure, virtualization concepts_  | [Practice: Node Essentials: Promises](https://devops.docable.cloud/chrisparnin/v/61a91ec418321edaed0f8ea6) |
| Jan 26   | [VM workshop](https://github.com/CSC-DevOps/VM)                                     |  | [HW-V](HW/HW-V.md)
|          | _Virtual Box and Virtualization Framework Internals_| Build vagrant from scratch and bash provisioning script |
| Jan 31   | [Debugging Virtualization Problems](https://docs.google.com/presentation/d/1fkg-5dD790lHlkDr9A0zmIUm_kvzTJbqynzZTtqhZyQ/edit?usp=sharing)
| Feb 2   | [OS Virtualization](Content/Virtualization/Containers/README.md) | 
|          | _Containers, overlayfs, cgroup_                | Build docker from scratch |
| Feb 7         | [Images](Content/Virtualization/Images/README.md) |
|          | _Building disk images, initrd, rootfs, kernel_ | Build packer from scratch |
| Feb 9    |  [Cloud provisioning](https://github.com/CSC-DevOps/Provision)  | Build doctl from scratch  |   [HW-P](HW/HW-P.md)    
| <tr><th colspan=4> 🚰🚀 &nbsp;&nbsp;&nbsp;Pipelines, CI/CD&nbsp;&nbsp;&nbsp; 🧪✅</th></tr> |
| Feb 14   | [Pipelines](https://docs.google.com/presentation/d/1d8-fjqal6FQcrUeH3N4DTOGl0o9hQblIanGwv1WlCuE/edit#slide=id.gc0bfd9f574_0_143)
| Feb 16   | [Pipelines Workshop](https://github.com/CSC-DevOps/Pipelines) | Build a deployment pipeline from scratch | 
|          | _git hooks, pre-commit, post-receive, bare repositories, process managers_ |
| Feb 21   | [Configuration Management](https://docs.google.com/presentation/d/11_0xv1-1Ws8APcpsBlENLDicCkZv2ZZwxH2wRCjnbaw/edit?usp=sharing)  | | [M1](Project/M1.md)
| Feb 23   | [CM, Ansible](https://github.com/CSC-DevOps/CM)
| Feb 28   | [Testing+Analysis](https://docs.google.com/presentation/d/1PY5D1TAn9W7spSMS--B4zt8JwBXAJY4apx36N9so55I/edit?usp=sharing)
| Mar 2    | [Fuzzing](https://github.com/CSC-DevOps/Fuzzing)
| Mar 7    | [Static Analysis/Code Complexity](https://github.com/CSC-DevOps/Complexity)
| Mar 9    | [Code coverage](https://devops.docable.cloud/chrisparnin/v/621f95745872b78ccff50677)
| Mar 14   | Spring break
| Mar 16   | Spring break
| <tr><th colspan=4> 🚧&nbsp;&nbsp;&nbsp;Infrastructure + Operations&nbsp;&nbsp;&nbsp; 🏗️</th></tr> |
| Mar 21   | [Infrastructure concepts](https://discord.com/channels/929425673901178900/929428348197814352/955471473194205204)                                          | | [M2](Project/M2.md)
| Mar 23   | Redis
| Mar 28   | [Deployment strategies](https://docs.google.com/presentation/d/1Dg7x-70LT5KZ5GfojpzByhDa3abt1_mEdSmI8C2ojRE/edit?usp=sharing)
| Mar 30   |
| Apr 4    |
| Apr 6    |
| Apr 11   |
| Apr 13   |
| Apr 18   |
| Apr 20   |
| Apr 25   | Last class
| May 4    | Final Exam (12pm--2:30pm)        |            |                   |

