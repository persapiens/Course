## Virtual Machine provisioning with CLI program (30)

You will start with a starter code base and modify it to fulfill the homework criteria.
Please do the following before you start the homework.
 
### Clone and set-url

1. Clone the following template repository. Then, modify the git remote url so that it now will point to your HW1-<unity> repo.

```bash
git clone http://github.com/CSC-DevOps/V
cd V
git remote -v
git remote set-url origin https://github.ncsu.edu/cscdevops-spring2021/HW1-<unity>-DevOps
```

### Install and test

2. Install the npm packages, then create a symlink for running your program.
```bash
npm install
npm link
```

Try it out.
```
v up
```

You will see a virtual machine being prepared and booted; however, **the program is incomplete and will not fully work**.

## Choose your path 👣 | 👣

Based on your local development environment, you will need to use a different virtualization platform. For most cases, you will be able to take advantage of the venerable _VirtualBox_, but for others, you might have to travel on a _different road_.

### Base requirements

#### VirtualBox requirements 👣

Add the following required components to your project by editing the `customize(name)` function inside lib/provider/vbox.js. You will want to take advantage of the `VBoxManage.execute` wrapper to execute VirtualBox commands.

* Add a NIC with NAT networking.
* Add a port forward from 2800 => 22 for guestssh.
* Add a port forward from 9000 => 5001 for a node application.

Add the following required components to your project by editing the `postconfiguration(name)` function inside the lib/provider/vbox.js. You will want to take advantage of the `sshExe` command wrapper to send commands to the VM.

* Install nodejs and git
* Clone https://github.com/CSC-DevOps/App
* Install the npm packages


Add a new command by creating a ssh.js inside the commands directory. 
When running `v ssh` it should ssh into your VM.

* Implement and demonstrate running `v ssh`.
* Manually run `node main.js start 5001`.
* Demonstrate you can visit `localhost:9000` to see your running App.

#### Virtualization Framework requirements 👣

* Download [ubuntu focal image for M1](https://github.com/CSC-DevOps/VM/releases/download/v1.0.0/ubuntu-focal-m1.tar.gz)

* Fix cmd_line

* options.kernel, options.initrd, options.rootfs, options.kernel_cmdline
* Fix dns.

  Currently, the VM does not have a proper nameserver configured, meaning while you can access external networks, you can't resolve domain names. 
  ```
  ubuntu@localhost:~$ ping 8.8.8.8
  PING 8.8.8.8 (8.8.8.8): 56 data bytes
  64 bytes from 8.8.8.8: icmp_seq=0 ttl=114 time=27.117 ms
  ubuntu@localhost:~$ host google.com
  ;; connection timed out; no servers could be reached
  ```

  Write code to update the /etc/resolv.conf file:

  ```
nameserver 8.8.8.8
nameserver 8.8.4.4
  ```

* Install git, nodejs
* clone repo...
 
## Screencast (10)

Create a screencast of your assignment:

* Demonstrate running your code to provision the VM (`v up`), running your customization and post-configuration steps, and ssh (`v ssh`) and a starting your App. Demonstrate your app running on your browser. Demonstrate any extra requirements fulfilled.



