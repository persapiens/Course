# Pipeline > Deploy

For this milestone and project, you will continue to work in teams of 3 people.

## General Tasks

* Provision cloud instances and setup monitoring infrastructure.
* Implement deployment to cloud instances.
* Implement canary analysis (checkbox.io preview microservice)

### Project Driver

Ensure the following command still operates in order to bring up your configuration and jenkins server:

```bash
# Configure jenkins, build environments, build jobs
# --gh-user and --gh-pass should be used for accessing iTrust repo on github.ncsu.edu
$ pipeline setup --gh-user <username> --gh-pass <password>
# This command should copy a .vault-pass file, with the password "csc-devops-2020" from the host to VM home directory. The .vault-pass file should be excluded from source control_. 
```

Extend your node.js project to support the following commands:

```bash
# Provision cloud instances
$ pipeline prod up
<output inventory.ini with production assets>

# Setup monitoring infrastructure on given infrastructure 
$ pipeline monitor-setup -i inventory.ini

# Perform a deployment of checkbox.io with given inventory
$ pipeline deploy checkbox.io -i inventory.ini

# Trigger a build job (named iTrust), wait for output, and print build log.
# Extend your jenkins build job to create a war file for deployment.
$ pipeline build iTrust -u <admin> -p <admin>

# Perform a deployment of iTrust with given inventory
$ pipeline deploy iTrust -i inventory.ini

# Construct canary infrastructure, collect data, and perform analysis on the given branches.
$ pipeline canary master broken
<report and canary score and whether passed or failed>
...
```

### Provision cloud instances and and setup monitoring.

Your `prod up` command should provision instances for your target infrastructure on a cloud provider. It should also generate an inventory.ini with your cloud resources. You may reuse/extend code from the [provision workshop](https://github.com/CSC-DevOps/Provision) to accomplish this goal.

##### Monitoring

Your `monitor-setup -i inventory.ini` command should deploy a monitoring dashboard that can report metrics associated with the deployed applications. You will need to devise a strategy for collecting metrics from deployed applications (checkbox.io and iTrust). You may reuse/extend code from the [Monitoring workshop](https://github.com/CSC-DevOps/Monitoring) or automatically configure a monitoring tool.

Expose the dashboard endpoint on `http://<monitoring ip>/dashboard`.

##### Local development

For local development and testing purposes, you should be able to swap out your dynamically created inventory with this static one:

```
[monitor]
192.168.33.24 ansible_ssh_private_key_file=~/.bakerx/insecure_private_key ansible_user=vagrant

[itrust]
192.168.33.22 ansible_ssh_private_key_file=~/.bakerx/insecure_private_key ansible_user=vagrant

[checkbox]
192.168.33.23 ansible_ssh_private_key_file=~/.bakerx/insecure_private_key ansible_user=vagrant
```

You can provision and configure your local instances with:

```
bakerx run monitor bionic --ip 192.168.33.24
bakerx run checkbox bionic --ip 192.168.33.23
bakerx run itrust bionic --ip 192.168.33.22

pipeline setup --gh-user <username> --gh-pass <password>
pipeline monitor-setup -i inventory.ini

pipeline deploy checkbox.io -i inventory.ini
pipeline build iTrust -u <admin> -p <admin>
pipeline deploy iTrust -i inventory.ini
```

### Deploy checkbox.io and iTrust

Deploy checkbox.io and iTrust to your production environment provided in inventory.ini. You should be able to mostly reuse your previous roles for building the configuration server and production. Be mindful of places you may have hard-coded paths (e.g. `/home/vagrant`) and variables, as this likely to change for production.

##### iTrust

You will need to extend your jenkins build job to create a war file for deployment---add the step `mvn package` to create the war file, if the build is successful. Your `deploy` command will then use the last built project as part of the deployment process. Optionally, you may consider using the artifact mechanism in jenkins: https://www.jenkins.io/doc/pipeline/steps/core/#archiveartifacts-archive-the-artifacts

The production environment will need a tomcat webserver (Tomcat 9) that can serve the iTrust war file.

You will also need to seed the database on the production site. One strategy to have the deploy step export the itrust database (as created from `mvn clean process-test-classes -f pom-data.xml`), store the database as in .sql file (`mysqldump`), and then import in production (`mysql -u username -p database_name < file.sql`).

##### checkbox.io

You will need to configure nginx to route api requests for checkbox.io to your running server: `/api => localhost:3002`. See [example configuration](https://github.com/chrisparnin/checkbox.io/tree/master/local-conf) in checkbox.io repo.

You will also need a process supervisor, such as forever or pm2, to ensure the server.js is running on checkbox.io.

### Canary Analysis

Implement Netflix style red-black deployment with canary analysis of a microservice.

You will be targeting the preview microservice extracted from checkbox.io:
https://github.com/chrisparnin/checkbox.io-micro-preview

![img](/imgs/canary.png)

Create an automated analysis that can perform the following tasks and generate canary score and report:

1. Construct a computing environment with three VMs as shown in diagram (locally)
2. Generate load to the proxy server by requesting the `/preview` service.
3. For the first 1 minute, send the load to the blue instance, collect health metrics.
4. Next, send traffic to the green instance for 1 minute, collect health metrics.
5. Report a statistical comparision between health values and compute a canary score. Determine whether canary has "passed" or "failed". 

You should be able to reuse/extend code from the [Monitoring](https://github.com/CSC-DevOps/Monitoring) and [Deployment workshop](https://github.com/CSC-DevOps/Deployment). You might find [this package](https://github.com/juhis/genstats) useful for doing statistical tests. You are strongly encouraged to explore and measure multiple metrics in order to maximize your likelihood of detecting differences between the control and canary server.

## Team responsibilities

### 👥 Task leaders 

Each major task should have a team member responsible for implementing the majority of the assigned task.

Use your GitHub Project Board (e.g. Milestone1) to help coordinate and assign tasks.

![Project Board](https://miro.medium.com/max/4976/1*_St3BrB36V05JAuFIC3utQ.png)

_Points will be deducted for non-contributing members, including receiving zero credit._

### Checkpoint and milestone report.

##### Checkpoint

There will be one checkpoints where you will be required to report interim progress (CHECKPOINT.md).

* Checkpoint 1 due: July 15th

Document your current progress and team contributions. Note work you have completed and what work will be done next. You may find it useful to take screenshots of your GitHub Projects.

_Points will be deducted for teams not making steady progress throughout the milestone._

##### Milestone report

Document the experiences you have in learning about setting up the system, and implementing your deployment techniques. This can be described in your submission's README.md.

## Evaluation

* Provision instances and monitoring (20%).
* Implement configuration steps for deployment (20%).
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

**Due Friday, July 24th, before midnight.**
