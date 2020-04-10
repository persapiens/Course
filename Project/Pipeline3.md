# Pipeline > Deploy

For this milestone and project, you will continue to work in teams of 3 people.

## General Tasks

* Provision cloud instances, monitoring control plane.
* Implement deployment to cloud instances.
* Implement canary analysis (checkbox.io preview microservice)

### Project Driver

Extend your node.js project to support the following commands:

```bash
# Provision cloud instances and control plane. 
$ pipeline prod up

# Perform a deployment of checkbox.io with given inventory
$ pipeline deploy checkbox.io -i inventory.ini

# Perform a deployment of iTrust with given inventory
$ pipeline deploy iTrust -i inventory.ini

# Construct canary infrastructure, collect data, and perform analysis on the given branches.
$ pipeline canary master broken
<report and canary score and whether passed or failed>
...
```

### Provision cloud instances and monitoring control plane.

Provision instances for your target infrastructure in a cloud provider. Implement a monitor VM with a dashboard that can report metrics associated with the deployed applications. Devise a strategy for collecting metrics from deployed applications (checkbox.io and iTrust).

### Deploy checkbox.io and iTrust

Deploy checkbox.io and iTrust to your production environment provided in inventory.ini. You will need to configure nginx for checkbox.io. For iTrust, you will need to deploy a war file and tomcat webserver.

### Canary Analysis

Implement Netflix style red-black deployment with canary analysis of a microservice.

You will be targeting the preview microservice extracted from checkbox.io:
https://github.com/chrisparnin/checkbox.io-micro-preview

![img](/imgs/canary.png)

Create an automated analysis that can perform the following tasks and generate canary score and report:

1. Construct a computing environment with three VMs as shown in diagram (locally)
2. Generate load to the proxy server by requesting the `/preview` service.
3. For the first 5 minutes, send the load to the blue instance, collect health metrics.
4. Next, send traffic to the green instance for 5 minutes, collect health metrics.
5. Report a statistical comparision between health values and compute a canary score. Determine whether canary has "passed" or "failed".

## Team responsibilities

### 👥 Task leaders 

Each major task should have a team member responsible for implementing the majority of the assigned task.

Use your GitHub Project Board (e.g. Milestone1) to help coordinate and assign tasks.

![Project Board](https://miro.medium.com/max/4976/1*_St3BrB36V05JAuFIC3utQ.png)

_Points will be deducted for non-contributing members, including receiving zero credit._

### Checkpoint and milestone report.

##### Checkpoint

There will be one checkpoints where you will be required to report interim progress (CHECKPOINT.md).

* Checkpoint 1 due: Monday 4/20th

Document your current progress and team contributions. Note work you have completed and what work will be done next. You may find it useful to take screenshots of your GitHub Projects.

_Points will be deducted for teams not making steady progress throughout the milestone._

##### Milestone report

Document the experiences you have in learning about setting up the system, and implementing your deployment techniques. This can be described in your submission's README.md.

## Evaluation

* Implement configuration steps for deployment (20%).
* Provision instances and monitoring (20%).
* Canary analysis (40%).
* Checkpoint and milestone report (10%).
* Screencast (10%).

Points may be deducted for not following constraints, poor quality of implementation, poor task communication and delegation, or failing to include sufficient detail required to evaluate capabilities.

_Points will be deducted for non-contributing members, including receiving zero credit._

## Submission

Commit your all your work related to your project into your designated repository before the final deadline. Create a branch called `M3` to hold a snapshot of your work related to this milestone.

Ensure your repository contains:

* a top-level node.js project supporting the required commands for running your build server.
* a README.md, with your report details.
* a CHECKPOINT.md, with your checkpoint report.
* a link to screencast that demostrates each task.

**Due Tuesday, April 28th, before midnight.**
