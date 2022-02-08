# Packaging and Provisioning

## Building a Virtual Machine Image

### Setup

1. Find a suitable option for [running docker on your system](../Content/Virtualization/Containers/DockerOptions.md).


2. Clone the following template repository. Then, modify the git remote url so that it now will point to your HW2-<unity> repo.

```bash
git clone http://github.com/CSC-DevOps/P
cd P
git remote -v
git remote set-url origin https://github.ncsu.edu/CSC-DevOps-S22/HW2-<unity>-DevOps
```

3. Install node packages and test.

```bash
npm i
npm link
# Build your custom docker image
p init
# Build rootfs, extract kernel, initrd and package as iso.
p build
```

### Base Requirements

Extend the program to perform the following tasks.

1. Build Docker image.

Build a docker image that will contain all the tools needed for performing your image build. For example, you will want to install `mkiofs` for creating an ISO, and `e2fsprogs` for formating a filesystem of a raw image.

Extend the `images/Dockerfile` to complete this step.

2. Create a rootfs.

Extend the `scripts/make-rootfs.sh` script that executes inside your custom docker image, to perform the following steps:

a) Download and extract an appropriate base rootfs: [Ubuntu 20.04 Intel/AMD](https://cloud-images.ubuntu.com/focal/current/focal-server-cloudimg-amd64-root.tar.xz) | [Ubuntu 20.04 ARM64](https://cloud-images.ubuntu.com/focal/current/focal-server-cloudimg-arm64-root.tar.xz)

b) Install the necessary packages to install python, pip, and dependencies needed to install [jupyter "classic" notebook](https://jupyter.org/install) by mounting disk and using `chroot`.

c) Create file content.

Save the following [csv file](https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv) to `/data` in the rootfs. 

Eventually, when you have a working jupyter notebook, you will test if you can successfully run the following code snippet in the notebook interface.

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

titanic = pd.read_csv('/data/titantic.csv')

# Countplot
sns.catplot(x ="Sex", hue ="Survived",
kind ="count", data = titanic)
```

3. Package kernel, initrd + bootloader as iso

You will run a script to package your virtual machine content as an ISO.
Perform the following steps.

a. Modify your rootfs script to install the `linux-virt` apt package. This will create a vmlinuz and initrd file in the /boot directory of your rootfs. 

b. Make a directory called `iso`. Structure your content as:

```
iso/
  isolinux/
    - isolinux.bin
    - isolinux.cfg
    - idlinux.c32
  boot/
    - vmlinuz
    - initrd
```

c. Generate iso

```
mkisofs -o jn.iso -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J iso
```



## Screencast

Demonstrate building, booting iso in screencast.



# Diagram of concepts

Draw diagram of your program's architecture.

Draw diagram explaining VM and docker concepts.

