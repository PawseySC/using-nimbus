---
title: "Access and Use an Instance"
teaching: 45
exercises: 0
questions:
- "How do we access an instance?"
- "What are the first things we do on an instance?"
objectives:
- "Connect to an instance with ssh"
- "Attach and use a data volume with your instance"
keypoints:
- "You learned how to connect with an SSH client to a Linux instance."
- "You learned how to create a new filesystem and mount it in your instance."
- "You learned how to unmount and detach your volume, and reuse it."
---

## Let's log in
Head to your terminal window to login to your instance:
* We will access our instances using a Secure SHell (SSH) connection.

What you need:
1. __Your instance’s IP address__: get this from the instance overview in your dashboard

    ###.###.###.###

2. __Your login name__: this depends on the name of the Linux OS image you selected

    Login names:

    | Ubuntu  | **ubuntu** |
    | Centos | **centos** |
    | Fedora | **fedora** |
    | Scientific Linux | **root** |
    | Debian  | **debian** |

3. The location and name of your private key pair (if you are using Windows and Putty)
    My_Key_Pair.ppk

    Once saved (or saved and uploaded) your private key file permission will need to be changed to work with your SSH client in the next lessons. Run this command in your terminal:
~~~
     chmod 600 name_of_your_key.pem
~~~

----

> ## If you're using Linux / Mac / Unix
>
>  $ ssh login_name@###.###.###.###
>
> or (if you have more than one private key)
>
>  $ ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###
{: .callout}

> ## If you're using Windows
>
> 1) Open Putty
>
> 2) Under "Host name (or IP address)" put: login_name@###.###.###.###
>
> 3) In the menu on the left, expand "SSH" and click on "Auth".
>
> 4) Under the section "Authentication parameters" click on "Browse...".
>
> 5) Select your previously create .ppk private key.
>
> 6) Click on "Open" to start the connection to your instance.
{: .callout}


## If it all worked...

![Successful login]({{ page.root }}/fig/nimbus_logged_in.png)


## If you get an error...

1) ssh: Could not resolve hostname \342\200\223i name or service unknown error - [link](http://tumblr.gudge.com/post/18186353550/ssh-could-not-resolve-hostname-342200223i)

When using MobaXTerm if you cut and paste the *ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###* example you will get the wrong hyphen in the "-i" part and throw a confusing error

**Solution:** Don't cut and paste example - manually type in ssh syntax

----


## Volume Storage

We can check that our data volume is attached, but we can’t use it just yet.  If the unformatted volume is properly attached you should see:

~~~
root@test-instance:~# sudo fdisk -l /dev/vdc
Disk /dev/vdc: 20 GiB, 21474836480 bytes, 41943040 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
~~~
{: .output}

## Format and mount a filesystem

We need to format and create a filesystem on the volume.  We will do this using the mkfs command.  __Warning: Use mkfs only once for each volume.  It wipes any data already on it.__

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
test-instance:~$ sudo mkdir /data
test-instance:~$ sudo mount /dev/vdc /data
test-instance:~$ df -h | grep vdc
/dev/vdc         20G   44M   19G   1% /data
test-instance:~$ sudo mkdir /data/my_files
test-instance:~$ sudo chown ubuntu /data/my_files
~~~
{: .output}

You can now store files and subdirectories in the /data/my_files/ directory.

~~~
test-instance:~$ nano /data/my_files/my-data-file
# type some made up data into the file, save and quit (^X)
test-instance:~$ ls /data/my_files/
my-data-file
~~~
{: .output}

## Unmount and reuse the volume

Once you have stored some data in your volume, you may wish to __unmount__ it __detach__ it from your instance.

~~~
test-instance:~$ sudo umount /data/my_files
~~~
{: .output}

Next, select __Manage Attachments__ from the drop-down menu of the volume, then __Detach Volume__, and again to confirm.  Warning: If you detach a volume before you unmount it, you may lose data.

Now you could delete your instance and recreate it, then attach this data volume to the new one. For now, we will just reattach it to the same instance.  Click __Manage Attachments__ again, select your instance, and __Attach Volume__.

This time, let's mount the volume somewhere different. Remember, you do __not__ need to create a filesystem again, because that would wipe your data.
~~~
test-instance:~$ sudo mkdir /data2
test-instance:~$ sudo mount /dev/vdc /data2
test-instance:~$ df -h | grep vdc
/dev/vdc         20G   44M   19G   1% /data2
test-instance:~$ ls /data2/
my_files
test-instance:~$ ls /data2/my_files/
my-data-file
~~~
{: .output}
