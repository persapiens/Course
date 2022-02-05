FROM alpine:3.15
RUN mkdir -p /lib/apk/db /run
RUN apk add --initdb openrc
RUN apk add linux-virt dbus-libs kbd-bkeymaps

# busybox-initscripts busybox-suid
#RUN apk add --update alpine-baselayout alpine-keys apk-tools busybox busybox-initscripts alpine-conf ca-certificates rng-tools  util-linux
RUN apk add --update alpine-baselayout alpine-conf alpine-keys busybox busybox-initscripts rng-tools util-linux

# Copy kernel for later use
RUN cp /boot/vmlinuz-virt /vmlinuz
# Nuke boot
RUN rm -rf /boot

# Deleted cached packages
RUN rm -rf /var/cache/apk/*

#RUN echo "tty0::respawn:/sbin/agetty -a root -L tty0 38400 vt100" > /etc/inittab
RUN echo "hvc0::respawn:/sbin/agetty -a root -L hvc0 38400 linux" >> /etc/inittab

RUN echo "Welcome to initramfs" > /etc/motd

# Our init
COPY simple_init /init