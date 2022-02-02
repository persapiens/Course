# Building Virtual Machine Images

```bash
npm i
npm link
p init
p build
```

0. Docker... in VM (Windows) or 'local' Mac/Linux.

1. Build Dockerfile image.

- mkiofs
- mkfs.ext4

2. Download and build rootfs. Run packaging script.

chroot rootfs build

3. Pack cpio. Format disk.

4. Package kernel, initrd, rootfs + bootloader as iso

5. Demonstrate building and booting iso in screencast.
