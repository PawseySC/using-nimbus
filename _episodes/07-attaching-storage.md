---
title: "Attaching volume storage"
teaching: 30
exercises: 0
questions:
- "How do you set up volumes and store data?"
objectives:
- "Attach and use a data volume with your instance."
keypoints:
- "You learned how to create a new volume and attach it to your instance."
- "You learned how to create a new filesystem and mount it in your instance."
---

**There are two types of built-in storage**
1. Root Volume - your home directory, and storage for the operating system of your virtual machine
2. Data Volume - a second hard drive you can add to your VM for working storage

Volumes are created and attached using the Nimbus web interface, then formatted and mounted.

## Create a volume
Go to **Compute** then **Volumes**.  Click on **Create Volume**.  A pop-up will appear (see screenshot below).

![Nimbus Volumes]({{ page.root }}/fig/Nimbus_volumes.png)

Enter a **Volume Name** and **Size (GiB)** for the volume, then click **Create Volume** at the bottom of the pop-up.

![Nimbus Create Volumes]({{ page.root }}/fig/nimbus_create_volume.png)


## Manage attachements
![Nimbus Configure Volumes]({{ page.root }}/fig/Nimbus_configure_volumes.png)

Select the **Manage Attachments** from the drop-down menu of the volume you just created

![Nimbus Manage Attachments]({{ page.root }}/fig/nimbus_vol_manage_attachments.png)

We can check that the volume is attached, but we can’t use it just yet.  If the unformatted volume is properly attached you should see:

~~~
root@test-instance:~# sudo fdisk -l /dev/vdc
Disk /dev/vdc: 20 GiB, 21474836480 bytes, 41943040 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
~~~
{: .output}

We need to format and create a filesystem on the volume.  We will do this using the mkfs command. __Warning: Use mkfs only once for each volume.  It wipes any data already on it._

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

Then we can mount the volume, and create a subdirectory to store files in:

~~~
root@test-instance:~# sudo mkdir /data
root@test-instance:~# sudo mount /dev/vdc /data
root@test-instance:~# df -h | grep vdc
/dev/vdc         20G   44M   19G   1% /data
root@test-instance:~# sudo mkdir /data/my_files
root@test-instance:~# sudo chown ubuntu /data/my_files
~~~
{: .output}

You can now store files and subdirectories in the /data/my_files/ directory.
