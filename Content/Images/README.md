# Building images


WOrksop..

http://www.aclevername.com/articles/linux-xilinx-tutorial/minimalist-initramfs.html

https://cloud-images.ubuntu.com/focal/current/

https://tldp.org/LDP/lfs/LFS-BOOK-6.1.1-HTML/chapter06/devices.html

# mount the disk on the loopback device (e.g. put the CDROM into the DRIVE)

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


```
find . | cpio -o -H newc 2>/dev/null | gzip > ../initrd
```