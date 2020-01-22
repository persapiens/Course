# HW1

This homework will all you to practice with basic virtualization technology and familiarize you with building node CLI programs.

You will start with a starter code base and modify it to fulfill the homework criteria.

## Setup

Please do the following before you start the homework.

### Prepare your GitHub Repo.

Sign into [NCSU's GitHub](https://github.ncsu.edu/).

1. Create a *private* repo called HW1-DevOps. 
2. Go to Settings, Collaborators and Teams, and add the TAs and instructor as a collaborator (using their unity id).

Samim Mirhosseini Ghamsa <smirhos@ncsu.edu>, Jeremiah Percy Dsouza <jdsouza@ncsu.edu>, Christopher Parnin <cjparnin@ncsu.edu>

**Do not create any content, yet**

### Clone and set-url

Clone the following repo. Then modify the remote so that it now will point to your HW1-DevOps repo.

```bash
git clone http://github.com/CSC-DevOps/V
cd V
git remote -v
git remote set-url origin https://ncsu.github.edu/<unity>/HW1-DevOps
```

### Install and test

Install the npm packages, then create a symlink for running your program.
```bash
npm install
npm link
```

Try it out.
```
V up
```

It is expected to see some errors, as the program is not complete.

```
Executing VBoxManage import "/Users/cjparnin/.bakerx/.persist/images/bionic/box.ovf" --vsys 0 --vmname V--Users-cjparnin-classes-519-V
Executing VBoxManage modifyvm "V--Users-cjparnin-classes-519-V" --memory 1024 --cpus 1
Executing VBoxManage modifyvm V--Users-cjparnin-classes-519-V  --uart1 0x3f8 4 --uartmode1 disconnected
Running VM customizations...
Executing VBoxManage startvm V--Users-cjparnin-classes-519-V --type emergencystop
Executing VBoxManage startvm V--Users-cjparnin-classes-519-V --type headless
Waiting 60000ms for machine to boot.
```

## Base Requirements

#### VM setup (40 points)

Add the following required components to your project by editing the `customize(name)` function inside commands/up.js. You will want to take advantage of the `VBoxManage.execute` wrapper to execute VirtualBox commands.

* Add a NIC with NAT networking.
* Add a port forward from 2800 => 22 for guestssh.
* Add a port forward from 8080 => 9000 for a node application.

#### Post-Configuration (25 points)

Add the following required components to your project by editing the `postconfiguration(name)` function inside the commands/up.js. You will want to take advantage of the ssh command wrapper to send commands to the VM.

* Install nodejs, npm, git
* Clone https://github.com/CSC-DevOps/App
* Install the npm packages

#### SSH and App (25 points)

Add a new command by creating a ssh.js inside the commands directory. 
When running `V ssh` it should ssh into your VM (25 points).

* Implement and demonstrate running `V ssh`.
* Manually run `node main.js start 9000`.
* Demonstrate you can visit `localhost:8080` to see your running App.

#### Extra Requirements

You can complete some or all of the following activities for extra credit by modifying your code.

* Create a second NIC with either host-only or bridged networking enabled. Demonstrate that you can use your IP address to visit `<address>:9000` to see your running App. (5 points)
* Create a shared sync folder. This is fairly involved, only attempt if experienced---limited help will be provided from teaching staff. (10 points)

## Screencast (10)

Create a screencast of your assignment:

* Demonstrate running your code to provision the VM (`V up`), running your customization and post-configuration steps, and ssh (`V ssh`) and a starting your App. Demonstrate your app running on your browser. Demonstrate any extra requirements fulfilled.

For guidelines, software, and recommendations see [Screencasts](Screencasts.md).

## Evaluation

* Compete VM setup (40)
* Post-Configuration (25)
* SSH/APP (25)
* Screencast (10)
* Extra requirements (+5/+10)
* Answer a question (+5)

Max possible score: 120/100.

## Submission

Please a submit a [link to your repo here](https://docs.google.com/forms/d/e/1FAIpQLSdwHHnWteyH2UdIPaQs2_vrjcty2Rk7o1AMZEyRg6WUEo2itA/viewform?usp=sf_link).

In your repository, have your code, link to a screencast.

The assignment is due Friday, Jan 31st before midnight.
