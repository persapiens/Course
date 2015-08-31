Configuration Management Workshop
----------------------------------

The goal of this workshop is to demonstrate how to use some tools to aid with the creation of virtual machines and configure software on them.  At the end of this workshop, you should be able to automatically create a virtual machine and configure it to run a simple web server.

# Creating Virtual Machine

Install [vagrant](https://www.vagrantup.com/downloads.html).

Initialize a virtual machine.  A list of virtual machine providers can be found [here](https://atlas.hashicorp.com/boxes/search).

    vagrant init hashicorp/precise32

Init should initiatiate a download of the box, if not, you can manually add it as follows:

    vagrant box add precise32 http://files.vagrantup.com/precise32.box

Start up the virtual machine.

    vagrant up

If you see:

> No usable default provider could be found for your system.
> Vagrant relies on interactions with 3rd party systems, known as
"providers", to provide Vagrant with resources to run development
environments. Examples are VirtualBox, VMware, Hyper-V.

Then make sure to install a virtual machine system,  [e.g. VirtualBox](https://www.virtualbox.org/wiki/Downloads).

    vagrant up
    vagrant ssh

You should be able to connect to the machine.

# Configuration with Ansible

Ansible is a tool for configuring and coordinating software on multiple machines.
In general, Ansible (like Salt, Chef, and Puppet), use a central server that controls other nodes.  Unlike the other tools, Ansible does not require a client service to run on the nodes.

### Let's setup some stuff first

We want to create a master server that runs Ansible. First, use a binary package manager to setup some basic stuff missing.

    sudo apt-get update
    sudo apt-get install git
    sudo apt-get install make
    sudo apt-get install vim
    sudo apt-get install python-dev    
    sudo apt-get install python-pip

Now get ansible itself.

    git clone git://github.com/ansible/ansible.git --recursive
    cd ./ansible
    source ./hacking/env-setup

Install dependencies, using pip, a package manager for Python.
    
    sudo pip install paramiko PyYAML Jinja2 httplib2

Build the software.

    sudo make install

Test ansible

    ansible all -m ping

# Node Machine

We now want to create a new node that will be serving as our web server.  Normally, this could be a server hosted on AWS or a droplet on digitalocean.  Instead, for testing purposes, we will be creating another local virtual machine.  Follow the instructions we previously followed for creating a virtual machine, but with some exceptions:

* Make a new directory, called node, then run the commands in there.
* After running `vagrant init ...`, edit the Vagrantfile, and uncomment the following line: `#config.vm.network "public_network"`.  This will in effect cause the VM to have its own IP address that you can reach, instead of just using port forwarding.
* When launching the VM, you may be asked which network to bridge off of, you can use the same interface as the "wireless" network.

You will need the following information to help connect to this node.

* Run vagrant ssh-config to get path of the private_key, open it up and copy contents into textfile.
* Inside the node machine, run `ifconfig` and note the second ip address listed.

# Back to Ansible Server

Create a `keys/node0.key` file that contains the private_key you previously copied. This will allow you to ssh into your node VM from the Ansible Server. You may need to `chmod 500 keys/node0.key`.

Create a `inventory` file that contains something like the following.  Note use your ip address and private_key:
    
    node0 ansible_ssh_host=192.168.1.103 ansible_ssh_user=vagrant ansible_ssh_private_key_file=./keys/node0.key

Now, run the ping test again to make sure you can actually talk to the node!

    ansible all -m ping -i inventory -vvvv
    
Let's install a web server, called nginx, on the node.

    ansible all -s -m apt -i inventory -a 'pkg=nginx state=installed update_cache=true'
    
Start the web server.
    
    ansible all -s -m shell -i inventory  -a 'nginx'

Open a browser and enter in your node's ip address, e.g. http://192.168.1.103/

# Programming Ansible

Instead of running shell commands, you can directly use Ansible's Python API.  For example, this snippet will execute the simple ping test you've been using before.  See if you can adapt this code snippet to perform the `nginx` install instead of running a shell script.

```
import ansible.runner
from ansible.inventory import Inventory

runner = ansible.runner.Runner(
   module_name='ping',
   module_args='',
   pattern='*',
   forks=10,
   inventory=Inventory('inventory')
)
datastructure = runner.run()
print( datastructure )
```    
    
