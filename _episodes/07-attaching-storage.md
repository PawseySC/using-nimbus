---
title: "Attaching volume storage"
teaching: 30
exercises: 0
questions:
- "How do you setup disks and store data?"
objectives:
- "Attach and use an external data volume to your instance."
keypoints:
- "You learnt how to create a new volume and attach it to your instance."
- "You learnt how to create a new filesystem and mount it to your instance"
---

**There are two types of built-in storage**
1. Root Disk- your home directory, and storage for the operating system of your virtual machine
2. Volume Storage - a 2nd hard disk you can add to your VM for working storage

Volumes are created, attached using the Nimbus interface, and then formatted and mounted
## First create a volume
![Nimbus Volumes]({{ page.root }}/fig/Nimbus_volumes.png)

![Nimbus Create Volumes]({{ page.root }}/fig/nimbus_create_volume.png)

## Now, manage attachements.
![Nimbus Configure Volumes]({{ page.root }}/fig/Nimbus_configure_volumes.png)

![Nimbus Manage Attachments]({{ page.root }}/fig/nimbus_vol_manage_attachments.png)

We can check that the volume is attached, but we can’t use it just yet.  If the unformatted disk is properly attached you should see (from the fdisk command):

~~~
root@test-instance:~# sudo fdisk -l /dev/vdc
Disk /dev/vdc: 20 GiB, 21474836480 bytes, 41943040 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
~~~
{: .output}

First we need to format the disk.  We will do this using the mkfs command.

~~~
root@test-instance:~# sudo mkfs.ext4 /dev/vdc
mke2fs 1.42.13 (17-May-2015)
Creating filesystem with 5242880 4k blocks and 1310720 inodes
Filesystem UUID: 4523e176-043a-4d3f-b4a9-0c74ac9a4562
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208,
        4096000
 
Allocating group tables: done
Writing inode tables: done
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done
~~~
{: .output}

Finally we can mount the disk:

~~~
root@test-instance:~# sudo mkdir /data
root@test-instance:~# sudo mount /dev/vdc /data
root@test-instance:~# df -h | grep vdc
/dev/vdc         20G   44M   19G   1% /data
~~~
{: .output}
