[Setup](Setup.md#setup) | [Shells](Shells.md#shells) | [Markdown and IDEs](MarkdownEditors.md#markdown) | [Git](Git.md#git) |[Virtual Environments](Environments.md#virtualization) | [Task Management](OnlineTools.md#online-tools) | [Advanced Shells](Advanced.md#advanced)

# Virtualization

Virtual machines/containers can provide a useful solution for automating the creation and management of your computing environment and development workflow. Unfortunately, when developers think about virtual machines, a common idea that comes to mind is a dedicated heavy-weight virtualized system with a full graphics Desktop. Alternatively, you may think of dual-booted systems. While these types of systems can be useful, in this context, we will largely be talking about *headless* virtual machines, which are more directly useful for automating infrastructure tasks and supporting large-scale software development.

## Setting up Virtualization

[VirtualBox](https://www.virtualbox.org/wiki/Downloads) is an ubiquitous virtualization provider for Intel-based machines. It is very effective for creating *headless* virtual machines that run without any GUI/Desktop interface.

Install VirtualBox.

```bash|{type:'command', privileged: true, platform: 'win32'}
choco install virtualbox -y
```

```bash|{type:'command', platform: 'darwin'}
brew cask install virtualbox
```

> Mac: `virtualbox` requires a kernel extension to work.
> If the installation fails, retry after you enable it in:
>    System Preferences → Security & Privacy → General

### Ensure virtualization is enabled

To be able to run virtual machines, your machine needs to support virtualization. 
Ensure virtualization (Intel VT-x or AMD-V) is enabled on your system using the instructions for your operating system:  
- **Windows:** open Task Manager and go to Performance tab, and you should see virtualization is enabled.
  <img src="resources/imgs/win-taskmanager.jpg" data-canonical-src="resources/imgs/win-taskmanager.jpg" width="600" />

- **Mac:** run the command below to see the list of supported CPU flags. If you see **VMX**, your machine supports hardware virtualization:  

   ```bash |{type:'command', platform: 'darwin'}
   sysctl -a | grep machdep.cpu.features | grep VMX
   ```
   <img src="resources/imgs/mac-cpu-flags.png" data-canonical-src="resources/imgs/mac-cpu-flags.png" width="600" />
   
- **Linux:** run the command below to see the list of supported CPU flags. If you see **VMX** or **SVM** flag, youre machine supports hardware virtualization:

   ```
   grep -E "vmx|svm" /proc/cpuinfo
   ```
   <img src="resources/imgs/linux-cpu-flags.png" data-canonical-src="resources/imgs/linux-cpu-flags.png" width="600" />

### Debugging virtualization issues

> Windows: If you're running Hyper-V and VirtualBox, and you're experiencing crashes when you try to start a VM, you may need to [turn off Hyper-V](https://superuser.com/questions/540055/convenient-way-to-enable-disable-hyper-v-in-windows-8) (which exclusively locks use of CPU for virtualization).


These commands will enable to you to toggle on/off hyper-v as needed. However, a restart may be necessary after running the command.

To disable hyper-v:
```bash
bcdedit /set hypervisorlaunchtype off
```

To re-enable:

```bash
bcdedit /set hypervisorlaunchtype auto
```

> Linux: If you run `vboxmanage list vms` command and you get `WARNING: The vboxdrv kernel module is not loaded...` error, see the dicussion [here](https://askubuntu.com/a/229908) for how to fix it.

## M1 Machines?

If you're a Mac-M1 ("Apple Silcon") machine, they you're CPU is *arm-based* and not Intel/Amd. As a result, virtualization tools such as VirtualBox will not work on your machine!

Luckily, you can take advantage of the [virtualization framework](https://developer.apple.com/documentation/virtualization), which allows you to create virtual machines using MacOS. Unfortunately, there are limited tools that support this framework---yet. Keep posted!

## Creating a Virtual Machine

While it is possible to use the VirtualBox GUI to manually install a virtual machine (and run through the OS installation script); this is not an effective automation approach!

### Install bakerx

`bakerx` is a simple tool for creating and managing virtual machines.

```bash|{type:'command'}
npm install ottomatica/bakerx -g
```

### Using `bakerx`

#### Pulling images

First, you need to pull an existing virtual machine image from a registry. Registries are basically the assets in a GitHub repository releases. Then you can pull an image by running the following commands:

```bash|{type:'command'}
bakerx pull focal cloud-images.ubuntu.com
```

#### Creating VMs

After pulling images, you can create VMs that run those images. Simply run the command below:

```bash|{type:'command', stream: true, failed_when:'exitCode!=0'}
bakerx run v1 focal
```

#### Connecting to VMs

Finally, bakerx will give you an `ssh` command similar to what is shown below, which you can use to connect to the VM.

```bash|{type:'command', interactive: true}
bakerx ssh v1
```

#### Deleting VMs

When you're done, you can stop and delete the VM.

```bash|{type:'command'}
bakerx delete vm v1
```