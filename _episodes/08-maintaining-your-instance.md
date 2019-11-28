---
title: "Maintaining your instance"
teaching: 10
exercises: 0
questions:
- "How do you keep your instance up to date and safe?"
objectives:
- "Learn the commands to keep your VM up-to-date"
keypoints:
- "You learnt how to keep your instance up to date"
---

To create a new instance (Nimbus virtual machine), click on "Instances" (on the left menu under the "Compute" section) and after that click on the "Launch instance" button, located on the right.

There are many types and flavours of Linux distribution. The most widely used are often the Debian based linux distributions such as Ubuntu, and the Red Hat/Fedora based distribution such as CentOS. Other distributions have different methods to do updates that will not be covered for the purpose of this training.

All modern Linux distribution do not allow the superuser (root) to connect directly to perform administrative task. What is used is a "service" user that does not have administrative permissions, but that can access those privileges by executing the command "sudo" before administrative like commands.

| ```sudo``` | Prefix command used to allow ‘super’ privileges to make administrative changes |

## Maintaining an Ubuntu linux distribution

To maintain the already installed packages, meaning installing newer versions and security patches:

| ```sudo  apt-get  update``` | Update the list of repositories (sources with available new software)|
| ```sudo  apt-get  upgrade``` | Upgrade all installed packages |
| ```sudo  apt-get  dist-upgrade``` | Upgrade all installed packages (to new releases versions and updates the kernel as well. To be used with care. |

To install new software:

| ```sudo  apt-get  install <package_name>``` | Install packages available within your selected Linux distribution's software package repository |

## Maintaining an CentOS linux distribution

To maintain the already installed packages, meaning installing newer versions and security patches:

| ```sudo  yum check-update``` | UUpdate the list of repositories and display available updates|
| ```sudo  yum update --exclude=kernel*``` | Upgrade all installed packages minus the kernel |
| ```sudo  yum update``` | Upgrade all installed packages including kernel |

To install new software:

| ```sudo  yum install <package_name>``` | Install packages available within your selected Linux distribution's software package repository |

## Use these commands as often as possible!

Ideally, combine these commands, depending on your Linux distribution, and run them at least once a week, or every time you login.

This will keep your instance up to date.

> ## Install a package on your instance
>
> Try to install the advanced text editor. This package is called 'vim' and it is not installed by default on most Linux distributions.
>
>> ## Solution
>> on Ubuntu:
>> ~~~
>> sudo apt-get install vim
>> ~~~
>> or on CentOS:
>> ~~~
>> sudo yum install vim
>> ~~~
> {: .solution}
{: .challenge}
