---
title: "Maintaining your instance"
teaching: 10
exercises: 0
questions:
- "How do you keep your instance up to date and safe?"
objectives:
- ""
keypoints:
- ""
---
​
14
**There are two types of built-in storage**
15
1. Root Disk- your home directory, and storage for the operating system of your virtual machine
16
2. Volume Storage - a 2nd hard disk you can add to your VM for working storage
17
​
18
Volumes are created, attached using the Nimbus interface, and then formatted and mounted
19
## First create a volume
20
![Nimbus Volumes]({{ page.root }}/fig/Nimbus_volumes.png)
21
​
22
![Nimbus Create Volumes]({{ page.root }}/fig/nimbus_create_volume.png)
23
​
24
## Now, manage attachements.
25
![Nimbus Configure Volumes]({{ page.root }}/fig/Nimbus_configure_volumes.png)
26
​
27
![Nimbus Manage Attachments]({{ page.root }}/fig/nimbus_vol_manage_attachments.png)
28
​
29
We can check that the volume is attached, but we can’t use it just yet.  If the unformatted disk is properly attached you should see (from the fdisk command):
30



| ```sudo``` | Prefix command used to allow ‘super’ privileges to make administrative changes |
| ```sudo  apt-get  install <package_name>``` | Install packages available within your selected Linux distribution's software package repository
| ```sudo  apt-get  update``` | Update all installed packages info (from the repository)|
| ```sudo  apt-get  upgrade``` | Upgrade all installed packages |
| ```sudo  apt-get  dist-upgrade``` | Upgrade all installed packages (to new releases versions and updates the kernel as well. To be used with care. |


Ideally you can combine all this ```sudo apt-get update && sudo apt-get update``` and once every few month run ```sudo apt-get update && sudo apt-get dist-upgrade``` and reboot your instance, this to get the newer kernel releases.

This will keep your instance up to date.
