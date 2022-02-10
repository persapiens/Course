# Docker on your system

If you want to run docker on your system, what's the best available option?

🐧 If you're running Linux, there isn't much more to do---you can simply install the docker-cli tool and take advantage of a few extra native options.

🍏 If you're running a Mac, whether Intel or M1/Arm64, using Docker Desktop for Mac will be your best option. You can take advantage of paravirtualization offered by Mac OS, meaning your docker environment will be relatively performant. You can also still use VirtualBox images.

🪟 If you're Windows, you can run Docker, by there isn't a simple solution that let's you fully take advantage of everything you'd want to do.

   1. You can install Docker Desktop for Windows---however, you won't be able to easily run virtualization software, such as VirtualBox at the same time.

   In this scenario, you can toggle between using Docker or VirtualBox, by toggling whether you have a hypervisor running, and then rebooting each time you change it.
   
   ```
   bcdedit /set hypervisorlaunchtype auto
   bcdedit /set hypervisorlaunchtype off
   ```

   2. Alternatively, you can try to use Hyper-V as a virtualization provider. The primary limitation of this approach is that not many linux distributions provide out of the box headless VM images that will work in Hyper-V. But if you did get it working, you can use Docker and Hyper-V at the same time.

   3. You can simply install the `docker-cli` tools and run the docker engine in a VM in VirtualBox. To use the docker-engine, you just need to set your environment variables to set the ip address of your VM.

   Prepare your docker vm
   ```
   bakerx run docker-vm focal --ip 192.168.99.101
   bakerx ssh docker-vm
   
   #Update the docker daemon to listen to outside connections:
   vagrant@ubuntu-focal:/etc/systemd$ cat /lib/systemd/system/docker.service | grep dockerd
    ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock -H tcp://0.0.0.0:2375
   # Restart service 
 
   # Check dockerd is running with additional host
   vagrant@ubuntu-focal:/etc/systemd$ ps -aux | grep dockerd
    root       10440  0.8  6.9 1087792 69368 ?       Ssl  18:08   0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock -H tcp://0.0.0.0:2375
   ```

   Install docker command line tools and point it to the docker engine running in your VM:
   ```
   choco install docker-cli -y
   SETX DOCKER_HOST tcp://192.168.99.101:2375
   
   docker run run-hello
   ```
  
   You can also use the `docker-machine` tool to manage this process for you. [See more here](https://github.com/ottomatica/docable-notebooks/blob/master/docs/examples/advanced/installs/docker-engine.md).
