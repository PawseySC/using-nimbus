---
title: "Storage"
teaching: 30
exercises: 0
questions:
- "What’s the difference between root and data volumes?"
- "How do I set up a volume to store my working data?"
- "What do I do with my data volume if I want to delete my instance?"
- "How many data volumes can I create?"
objectives:
- "Create and configure a data volume for an instance."
- "Attach and use a data volume with an instance."
- "Remove a data volume before deleting an instance."
keypoints:
- "You learned how to create a new volume for your instance."
- "You learned how to create a new filesystem and mount it in your instance."
- "You learned how to unmount and detach your volume."

---


Nimbus gives access to two types of storage by default, both of which can be considered like the Hard-disk drive of your desktop or laptop:
  1. Root Volume - includes your home directory, and storage for the operating system of your instance, and has the device name `/dev/vda`
  2. Data Volume - a second, independent volume you can attach to your instance for working storage, and has the device name `/dev/vdc`

> ## Best practice
> We recommend you use the Root Volume strictly as the home for your operating software, and that all data and documents are kept on a Data Volume. This allows you to take full advantage of the flexible nature of cloud computing, so for example if your instance develops a problem, you can quickly destroy and recreate the instance (destroying the original Root Volume in the process) and attach your Data Volume to the new instance.
{: .keypoints}

This episode goes through setting-up and using Data Volumes with your instance.


> ## Activity: Create and attach a volume
> From the Nimbus dashboard, go to **Volumes** then **Volumes**. Click on the **Create Volume** button.
>
> <kbd><img src="{{ page.root }}/fig/Volumes_dashboard.png" /></kbd><br><br>
>
>   The **Create Volume** dialog box will appear. Enter a **Volume Name** and > **Size (GiB)** for the volume, then click the **Create Volume** button at the bottom of the dialog box.
>
> <kbd><img src="{{ page.root }}/fig/Volumes_create.png" /></kbd><br><br>
>
> Once this is done, you will return to the **Volumes** panel, where you will now see the created data volume listed. In order to attach this volume to your instance, use its drop down menu on the right to select **Manage Attachments**.
>
> <kbd><img src="{{ page.root }}/fig/Volumes_manage.png" /></kbd><br><br>
>
> The **Manage Volume Attachments** dialog box will open. Use the **Attach To Instance** menu to select your instance, then click the **Attach Volume** button.
>
><kbd><img src="{{ page.root }}/fig/nimbus_vol_manage_attachments.png" /></kbd><br><br>
> When the dialog box closes you should see your data volume attached to your instance in the volumes panel.
><br>
>
> <kbd><img src="{{ page.root }}/fig/Volumes_attached.png" /></kbd><br><br>
{: .challenge}

You have created and attached a new data volume to your instance, which means at this point it is not formatted, and is therefore not useable. In order to be able to use it, you need to create a filesystem on the volume and mount it.<br><br>


> ## Activity: Create a filesystem
>
> Log in to your instance from the terminal using SSH. Once logged in, test the unformatted volume is properly attached by entering the following command:
>
>~~~
>ubuntu@test-instance:~$ sudo fdisk -l /dev/vdc
>~~~
><br>
You should see output like below:
>
>~~~
>Disk /dev/vdc: 20 GiB, 21474836480 bytes, 41943040 sectors
>Units: sectors of 1 * 512 = 512 bytes
>Sector size (logical/physical): 512 bytes / 512 bytes
>I/O size (minimum/optimal): 512 bytes / 512 bytes
>~~~
><br>
> You next need to format and create a filesystem on the volume.  You do this using the *mkfs* command.   
>> ## Warning
>> Use mkfs only once on a volume.  The command erases all data already there. If you are not sure if the volume has a filesystem, you can run the following command:
>>
>>~~~
>>ubuntu@test:~$ sudo file -sL /dev/vdc
>>~~~
>><br>
>> If there is a filesystem installed, you will see output like that below, and should therefore not run the *mkfs* command unless you are sure you want to format the volume.
>>
>>~~~
>>/dev/vdc: Linux rev 1.0 ext4 filesystem data, UUID=19916909-e2e2-4c44-8c34-fc7ded13918d (extents) (64bit) (large files) (huge files)
>>~~~
>><br>
>{: .keypoints}
>
> To format a volume and create a filesystem, run the following command:
>
> ~~~
>ubuntu@test-instance:~$ sudo mkfs.ext4 /dev/vdc
>~~~
><br>
> You will see the following output:
>
>~~~
>mke2fs 1.42.13 (17-May-2015)
>Creating filesystem with 5242880 4k blocks and 1310720 inodes
>Filesystem UUID: 4523e176-043a-4d3f-b4a9-0c74ac9a4562
>Superblock backups stored on blocks:
>        32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208,
>        4096000
> 
>Allocating group tables: done
>Writing inode tables: done
>Creating journal (32768 blocks): done
>Writing superblocks and filesystem accounting information: done
>~~~
><br>
>Now that the creation of the filesystem is complete, you can mount the volume. Using this example will mount the volume to the new directory '/data':
>
>~~~
>ubuntu@test-instance:~$ sudo mkdir /data
>ubuntu@test-instance:~$ sudo mount /dev/vdc /data
>ubuntu@test-instance:~$ df -h | grep vdc
>/dev/vdc         20G   44M   19G   1% /data
>~~~
><br>
> The output of the *df* command shows that the volume attached to '/dev/vdc' is now mounted to the '/data' directory. However, since you had to use root permissions to create the '/data' directory, you do not own it, and cannot use it to copy and access data. To do so, you need to change it's ownership:
>
>~~~
>ubuntu@test-instance:~$ sudo chown ubuntu /data
>~~~
><br>
>
>You can now store files and create subdirectories in the /data directory. Try it by creating a file, typing some made up data into it, then save and quit (^X):
>
>~~~
>ubuntu@test-instance:~$ nano /data/my-data-file
>ubuntu@test-instance:~$ ls /data
>ubuntu@test-instance:~$ cat /data/my-data-file
>~~~
><br>
>
>If you need to __unmount__ your data volume and __detach__ it from your instance, run the following command:
>
>~~~
>ubuntu@test-instance:~$ sudo umount /data
>~~~
><br>
>Next, from the Nimbus dashboard select **Volumes** from the **Volumes** tab, use it's drop down menu on the right to select **Manage Attachments**, then click the __Detach Volume__ button, and then again to confirm. **Note: If you detach a volume before you unmount it, you may lose data.**
{: .challenge}

> ## Moving Data
>
{: .challenge}
