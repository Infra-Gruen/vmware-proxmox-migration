# Debian Migration 

   1. From the above steps:
       1. Remove open-vm-tools from ESXi VM
       2. Install qemu-guest-agent on ESXi VM
   2. Detach the disks and attach them as SATA disks
   3. Set the SCSI controller to "VirtIO SCSI Single"
   4. Boot the Debian VM and run "update-initramfs -u -k all"
       1. For me the "update-initramfs" command was missing even in "/sbin" for whatever reason, to install do "apt install initramfs-tools" and then run the command again
   5. Shut the VM down, detach the hard disk and reattach it again as "SCSI"

Source: https://forum.proxmox.com/threads/debian-11-not-booting-with-virtio-scsi-single-but-works-with-vmware-pvscsi.144806/
