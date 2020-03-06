---
title: "Cloud best practices"
teaching: 10
exercises: 0
questions:
- "How do you keep your instance up to date and safe?"
- "What's the best way to use cloud?"
- "What can I use my instance for?"
- "How do I apply for a Nimbus allocation?"
objectives:
- "Learn the commands to keep your instance up-to-date"
- "Learn best practices for the cloud"
- "Understand how to install software on my VM"
- "Know the process to get an allocation"
keypoints:
- "You learnt how to keep your instance up to date"
- "Snapshot and update your VM"
- "Google is your friend"
---

## Best practices
1. **Keep your instance up-to-date**
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




2. **Snapshot your instance!**

    This saves your Root Disk and allows you to launch a fully configured instance with all packages already installed

3. **Document your steps so you know what you did**

    Create a configuration script, save a copy out of the cloud and keep it up to date
    history -> prints all previous commands
    history  |  keyword -> searches a specific command

4. **Update! Every time you login!**

    ```sudo apt-get update && sudo apt-get update```-> updates packages and security
    Older versions of packages and operating systems eventually lose support from their creators

5.  **Be Green and keep it elastic**

    The cloud still uses electricity and is shared, when you’re no longer using it -> turn it off!

---

## Ideas for using your VM
Once you have your shiny new VM, you are now the master of your own destiny.  You have flexibility to download software to start doing science.  Listed below are some tips on installing some common software packages that you might like to use however "Googling" your linux flavour / version along with the software will often give you success.  Also listed as details on moving data to your instance


**Conda**

Conda is an open source package management system and environment management system.   that runs on Windows, macOS, and Linux. Conda quickly installs, runs and updates packages and their dependencies. Conda easily creates, saves, loads, and switches between environments on your local computer. It was created for Python programs but it can package and distribute software for any language.

You can get started by downloading the installer suitable for your instance.  Miniconda installer page is given here [Miniconda](https://docs.conda.io/en/latest/miniconda.html)

Further information on installation here [Linux installation](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)


**R**

You can install R or Rstudio easily for most Linux flavours

for Debian/Ubuntu run *sudo apt-get install r-base* and or Fedora run *sudo yum install R* then type *R* to run

RStudio is an IDE (Integrated Development Environment) that makes R easier to use.  Go to RStudio download page - [https://www.rstudio.com/products/rstudio/download-server/](https://www.rstudio.com/products/rstudio/download-server/) and enter the following for Ubuntu

- *sudo apt-get install gdebi-core*
- *wget https://download2.rstudio.org/server/trusty/amd64/rstudio-server-1.2.1335-amd64.deb*
- *sudo gdebi rstudio-server-1.2.1335-amd64.deb*


**Machine learning**

If you are interested in machine learning the following site has many good resources (from beginner to advanced) [https://towardsdatascience.com/](https://towardsdatascience.com/)



**Copying files**

Courtsey of NeCTAR training materials - [Copying files](http://training.nectar.org.au/package07/sections/copyFiles.html)


---

## Applying for a VM
Compared to applying for time on one of our supercomputers, the process for applying for an allocation on Nimbus is less demanding.  You can apply at any time of the year by visiting the link below

### To get access visit: [https://apply.pawsey.org.au](https://apply.pawsey.org.au) ###
