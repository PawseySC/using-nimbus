---
title: "Software"
teaching: 10
exercises: 0
questions:
- "How do you maintain the software on your instance?"
- "How do you install new software?"
objectives:
- "Learn the commands to keep your instance up-to-date"
- "Install software using package managers"

keypoints:
- "You learnt how to keep your instance up to date"
- "You learnt how to install software using package managers"

---

## Managing software

Unlike on your laptop or desktop computer, you interact with your Nimbus instance remotely using the command line, ie. via a terminal. This means managing software is also done via the terminal, which might be an unfamiliar experience for many. In this episode we cover some of the basics you'll need to manage software on your instances via the command line interface.

## Keep your instance up-to-date

There are many types and flavours of Linux distribution. The most widely used are often the Debian based linux distributions such as Ubuntu, and the Red Hat/Fedora based distribution such as CentOS. Other distributions have different methods to do updates that will not be covered for the purpose of this training.

All modern Linux distribution do not allow the superuser (root) to connect directly to perform administrative tasks. What is used is a "service" user that does not have administrative permissions, but that can access those privileges by executing the command "sudo" before administrative like commands.

| ```sudo``` | Prefix command used to allow ‘super’ privileges to make administrative changes |

## Maintaining an Ubuntu linux distribution

To maintain the already installed packages, meaning installing newer versions and security patches:

| ```sudo  apt-get  update``` | Update the list of repositories (sources with available new software)|
| ```sudo  apt-get  upgrade``` | Upgrade all installed packages |
| ```sudo  apt-get  dist-upgrade``` | Upgrade all installed packages (to new releases versions and updates the kernel as well. To be used with care. |


## Maintaining an CentOS linux distribution

To maintain the already installed packages, meaning installing newer versions and security patches:

| ```sudo  yum check-update``` | UUpdate the list of repositories and display available updates|
| ```sudo  yum update --exclude=kernel*``` | Upgrade all installed packages minus the kernel |
| ```sudo  yum update``` | Upgrade all installed packages including kernel |

## Use these commands as often as possible!

Ideally, combine these commands, depending on your Linux distribution, and run them at least once a week, or every time you login.

This will keep your instance up to date.


## Package managers

Package managers are a collection of software tools that automate the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner.

Package managers are designed to eliminate the need for manual installs and updates. There are a range of different package managers available for different operating systems, as well as those for specific languages that work across different systems, such as the conda package manager for Python.

To install new software on Ubuntu you use apt:

| ```sudo  apt-get  install <package_name>``` | Install packages available within your selected Linux distribution's software package repository |

To install new software on CentOS you use yum:

| ```sudo  yum install <package_name>``` | Install packages available within your selected Linux distribution's software package repository |

> ## Exercise
> Update your system using the commands appropriate for your Linux distribution, and then try to install
> the advanced text editor 'vim'.
>
>> ## Solution
>> on Ubuntu:
>> ~~~
>> sudo  apt-get  update
>> sudo  apt-get  upgrade
>> sudo apt-get install vim
>> ~~~
>> or on CentOS:
>> ~~~
>> sudo yum check-update
>> sudo yum update --exclude=kernel*
>> sudo yum install vim
>> ~~~
> {: .solution}
{: .exercise}


## Python

A widely used package manager for the Python programming language is conda. Conda is open source, and as well as a package management system is also an environment management system. It runs on Windows, macOS, and Linux. Conda quickly installs, runs and updates packages and their dependencies. Conda easily creates, saves, loads, and switches between environments. It was created for Python programs but it can package and distribute software for any language.

You can get started by downloading the installer suitable for your instance.  Miniconda installer page is given here [Miniconda](https://docs.conda.io/en/latest/miniconda.html)

Further information on installation here [Linux installation](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)

__install conda and update, then install some small package, then exercise?__

## R

You can install R or Rstudio easily for most Linux flavours

for Debian/Ubuntu run *sudo apt-get install r-base* and or Fedora run *sudo yum install R* then type *R* to run

RStudio is an IDE (Integrated Development Environment) that makes R easier to use.  Go to RStudio download page - [https://www.rstudio.com/products/rstudio/download-server/](https://www.rstudio.com/products/rstudio/download-server/) and enter the following for Ubuntu

- *sudo apt-get install gdebi-core*
- *wget https://download2.rstudio.org/server/trusty/amd64/rstudio-server-1.2.1335-amd64.deb*
- *sudo gdebi rstudio-server-1.2.1335-amd64.deb*
