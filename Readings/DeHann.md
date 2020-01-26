# Some questions to ask about your infrastructure/ops:

by Michael DeHaan

##### Build/CM
* Are all dependencies version pinned (or is the repo at least snapshotted?)
* Are you protected against web dependencies going away?
* Can you still deploy when github is down?
* Use cloud like cloud where you can for more reliability - image builds where possible, some post-configuration done by cloud init, even locally executing ansible, is ok.
* Is a new build of this server going to look like one I built last week (snapshot of repos, etc) - or does this matter?
* Make sure no builds are done on the remote system
* Where possible, cache artifacts in your datacenter (example: yum reposync in the old days, maybe artifactory) and content get from there, don't DDOS some person's .com website with remote requests to copy a tarball, as this scales to 1000 servers doing it at once it will light things on fire or at least call failures

##### Security

* Is SELinux on? (Honestly I don't like it, but hey).
* What are the insider threat potentials for your application? Do developers have access to production data? If so, how much and why?
* Are the right pieces of the application available SSL-only?
* Is the VPN setup correct - bastion hosts, etc, SSH not open to every machine in production, etc.
* Are you using SSH authorized keys + passwords vs password auth?

##### CI/CD/Pipelines

* How closely does the development environment or QA environment match production? (For instance, how safe is it to develop on Mac and random database / library versions that don't match versions and OS'es in prod)
* Do unit tests block a stage deploy, and do stage/functional tests block a production deploy?
* Does your rolling update stop if problems are hit? Are the servers that have problems not turned back on? (Are there canary deployments?)


##### Infrastructure/Availabiity

* Is every cloud instance load balanced, and is there more than one instance of each? How does it autoscale, or is this a concern?
* Are applications multi-availability-zone or multi-region
* Avoid grabbing random things from dockerhub when you don't know where they come from and who has access to change them
* What kinds of load testing has been performed on the application?
* What are you doing for monitoring?
* What are you doing for logfile aggregration?
* Are services set to restart on reboot?

##### Resilence

* If your datacenter was hit by a tornado, how many clicks does it take to get it up?
* When was the last time you tested a database restoration from backup?
* How many clicks does it take to deploy to a new region or datacenter? Is it all documented?
* How many key people on your team can be eaten by velociraptors before your company must close?
* How locked into a particular provider are you that it would be too hard to change to another option when you stop liking the way it is being run, or it gets too expensive?

### Ansible opinions:

* there really are no rules but...
* it's good if running the playbook content again returns "Changed: 0". To do this, non-idempotent steps like "command/shell" executions need to be gated by when statements, etc.
* templates are cleaner than lineinfile (easier to read, safer against people changing things because the system will completely put it back)
* if it looks like code, you're maybe trying too hard, keep it simple
* breaking things down into smaller roles is useful
* comments are usually a good idea as are the "name" directives - help others understand why things are happening, explain bugs, workarounds, etc
* keep things that look like constants in a variable file
* I wrote MOST of this but it was probably added to a little after my tenure, but looks mostly intact: http://docs.ansible.com/ansible/latest/playbooks_best_practices.html
