# Building images


### Making initramfs

Building initramfs

```
find . | cpio -o -H newc 2>/dev/null | gzip > ../initrd
```


The `/init` process and hand-off.  Process zero.


### THe boot process


start_kernel()
=> arch_call_rest_init
  => arch_call_rest_init
    => kernel_init (as thread)



Kernel booting, unpacking initramfs, and initializing devices, kernel modules, and networking.

```
start_kernel(void)
{
	char *command_line;
	char *after_dashes;

    set_task_stack_end_magic(&init_task);
    smp_setup_processor_id();

[    0.000000] Booting Linux on physical CPU 0x0000000000 [0x00000000]
[    0.000000] Linux version 5.4.0-97-generic (buildd@bos02-arm64-018) (gcc version 9.3.0 (Ubuntu 9.3.0-17ubuntu1~20.04)) #110-Ubuntu S
MP Thu Jan 13 18:28:08 UTC 2022 (Ubuntu 5.4.0-97.110-generic 5.4.162)
```

```
...	boot_cpu_init();
	page_address_init();
	pr_notice("%s", linux_banner);
	early_security_init();
	setup_arch(&command_line);
	setup_boot_config();
	setup_command_line(command_line);
	setup_nr_cpu_ids();
	setup_per_cpu_areas();
	smp_prepare_boot_cpu();	/* arch-specific boot-cpu hooks */
	boot_cpu_hotplug_init();

	pr_notice("Kernel command line: %s\n", saved_command_line);
	/* parameters may set static keys */
	jump_label_init();
	parse_early_param();
	after_dashes = parse_args("Booting kernel",
				  static_command_line, __start___param,
				  __stop___param - __start___param,
				  -1, -1, NULL, &unknown_bootoption);
	print_unknown_bootoptions();
```


```
[    0.000000] Booting Linux on physical CPU 0x0000000000 [0x00000000]
[    0.000000] Linux version 5.4.0-97-generic (buildd@bos02-arm64-018) (gcc version 9.3.0 (Ubuntu 9.3.0-17ubuntu1~20.04)) #110-Ubuntu S
MP Thu Jan 13 18:28:08 UTC 2022 (Ubuntu 5.4.0-97.110-generic 5.4.162)
[    0.000000] efi: Getting EFI parameters from FDT:
[    0.000000] efi: UEFI not found.
```

```
dev_symlink("/proc/self/fd", "fd");
[    0.059653] devtmpfs: initialized
```

```
[    0.222929] cacheinfo: Unable to detect cache hierarchy for CPU 0
[    0.319762] loop: module loaded
[    0.320170] libphy: Fixed MDIO Bus: probed
[    0.320241] tun: Universal TUN/TAP device driver, 1.6
[    0.320408] PPP generic driver version 2.4.2
[    0.320526] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
[    0.320676] ehci-pci: EHCI PCI platform driver
[    0.320822] ehci-orion: EHCI orion driver
[    0.320898] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
[    0.320987] ohci-pci: OHCI PCI platform driver
[    0.321069] uhci_hcd: USB Universal Host Controller Interface driver
[    0.321213] mousedev: PS/2 mouse device common for all mice
[    0.321356] i2c /dev entries driver
[    0.321586] device-mapper: uevent: version 1.0.3
[    0.321717] device-mapper: ioctl: 4.41.0-ioctl (2019-09-16) initialised: dm-devel@redhat.com
[    0.321902] ledtrig-cpu: registered to indicate activity on CPUs
[    0.322181] drop_monitor: Initializing network drop monitor service
[    0.322439] NET: Registered protocol family 10
[    0.328465] Segment Routing with IPv6
[    0.328556] NET: Registered protocol family 17
[    0.328677] Key type dns_resolver registered
[    0.328852] registered taskstats version 1
....
```

Moun

```
[    0.350045] hctosys: unable to open rtc device (rtc0)
[    0.351563] Freeing unused kernel memory: 6912K
[    0.361641] Checked W+X mappings: passed, no W+X pages found
[    0.361728] Run /init as init process
Loading, please wait...
Starting version 245.4-4ubuntu3.15
```



### Making rootfs disk

See notebooks...

```
dd if=/dev/zero of=disk.img bs=1M count=50
mkfs.ext4 disk.img
mkdir -p /mnt/disk
mount -o loop disk.img /mnt/disk
wget https://dl-cdn.alpinelinux.org/alpine/v3.15/releases/x86_64/alpine-minirootfs-3.15.0-x86_64.tar.gz

tar -zxvf alpine-minirootfs-3.15.0-x86_64.tar.gz -C /mnt/disk/


chroot /mnt/disk ash -c 'echo "nameserver 8.8.4.4" | tee /etc/resolv.conf'
chroot /mnt/disk apk update
chroot /mnt/disk mkdir -p /lib/apk/db /run
chroot /mnt/disk apk add --initdb dhcpcd openssh
```

### Other types of disk formats...


### Packaging as iso




### References

http://www.aclevername.com/articles/linux-xilinx-tutorial/minimalist-initramfs.html

https://cloud-images.ubuntu.com/focal/current/

https://tldp.org/LDP/lfs/LFS-BOOK-6.1.1-HTML/chapter06/devices.html

https://kicherer.org/joomla/index.php/en/blog/47-the-essential-steps-in-the-linux-kernel-to-mount-and-boot-an-initramfs-and-root-filesystem


http://henryomd.blogspot.com/2014/11/linux-kernel-startup.html