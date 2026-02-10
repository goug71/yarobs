# yarobs
Yet another read-only/overlay boot script for ust any linux distro using initramfs-tools

This is yet another overlay boot script, initially targetted at initramfs-tools
This script allows to boot from a read-only medium, and adds overlay from either 
- any supported block device or
- a tarball on local medium or remote fetched by busyvox/curl
- a simple tmpfs overlay which then could be initialized with just any other script (including cloudInit)

It is suitable for baremetal, VMs or container, triggered and configured at run-time by kernel command line
