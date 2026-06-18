# yarobs
Yet another read-only/overlay boot script for use with any linux distro using initramfs-tools

This is yet another overlay boot script, initially targetted at initramfs-tools
This script allows to boot from a read-only medium, and adds overlay from either 
- any supported block device or
- a tarball on local medium or remote fetched by busyvox/curl
- a simple tmpfs overlay which then could be initialized with just any other script (including cloudInit)

It is suitable for baremetal or VMs and triggered and configured at run-time by kernel command line.

It came out of frustration about the complexity of debian-live where only tiny bits of it were needed to achieve one simple goal : run a bunch of machinew, VMs (or containers) using the same read-only rootfs, and differing only by a few KBs of config file and which service are activated or not.

Overlay is covering /root, /etc and /var. It can be a simple FS block device (including LVM), or live (which basically means tmpfs), possibly populated by a tarball fetched from a given URL (customizable with mac address)
