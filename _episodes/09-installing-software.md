---
title: "Software"
teaching: 30
exercises: 0
questions:
- "Why is it important to maintain your instances’ software?"
- "What is the process for maintaining an instances’ software?"
- "How do I install software on my instance?"
objectives:
- "Learn the commands to keep your instance up-to-date"
- "Install software using package managers"

keypoints:
- "Perform maintenance updates on your instances at least weekly to ensure the security and effectiveness of your software."
- "Install software when needed as administrator of your instance, but remind yourself that root commands have the potential to damage the system."
---

## Managing software

In earlier episodes you learned that on Nimbus you are responsible for managing all aspects of your instances, including the installation and maintaining of all software. In this episode we cover what you'll need to manage software on your instances via the command line interface.

## Keeping your instance up-to-date

Regularly updating your instance means you are installing the latest security patches, bug fixes and application upgrades. Updates on Ubuntu are managed via the `apt` application (there are a number of different Linux distributions, and not all of them are updated in the same fashion), which is actually a package manager. Package managers are a collection of software tools that automate the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner.

> ## Performing administrative tasks on Linux
> Before going any further it's important to note what happens if you try to perform an administrative task on different operating systems. On Windows or a Mac a dialog box asks you if you wish to continue and you may be required to type in your password and click OK. Things are a little more complicated in Linux. In order to be able to run system commands you need to have permission at the root (most powerful) level of the system. You can achieve this via `sudo` (pronounced like “sue dough”), which stands for “super user do!”. You may remember we used this command in the Storage episode in order to format and mount the Data Volume to our instance.
>
><kbd><img src="{{ page.root }}/fig/sandwich-1.png" /></kbd>
{: .callout}


The first command you need is `sudo  apt  update`:

<kbd><img src="{{ page.root }}/fig/apt_update.gif" /></kbd>

This command updates the local database of available software packages for Ubuntu. At the end of the command, it tells you how many packages can be upgraded.
To see them run the following command: `apt list --upgradable`.

The second command you need is `sudo apt upgrade`:

<kbd><img src="{{ page.root }}/fig/apt_upgrade.png" /></kbd>

The upgrade command actually installs newer versions of the packages you have. After updating the lists, the package manager knows about available updates for the software you have installed. This is why you first want to update.

> ## Use these commands as often as possible!
> Run them at least once a week, or every time you login, and this will keep your instance up to date.
>
{: .keypoints}



## Installing software

To install new software you use `sudo  apt  install <package_name>`


> ## Activity: Update and install software using apt
> We'll start by making sure our package database is up to date:
>~~~
>    $ sudo apt update && sudo apt upgrade -y
>~~~
> <br>
> The above command is a shortcut, a combination of the two commands we learnt previously. The `&&` is a way to combine two commands such that the second command runs only when the previous command ran successfully. The `-y` flag automatically enters “yes” when the upgrade asks for your confirmation before installing updates.
>
><kbd><img src="{{ page.root }}/fig/apt_update_upgrade.gif" /></kbd>
>
> Now we'll install a command line calendar application called `calcurse`:
>~~~
>    $ sudo apt install calcurse
>    $ source .bashrc
>    $ which calcurse
>    $ calcurse
>~~~
>
><kbd><img src="{{ page.root }}/fig/apt_calcurse.gif" /></kbd>
>
{: .challenge}

Apt is not the only useful package manager, another is conda, a package manager for Python. Conda quickly installs, runs, and updates packages and their dependencies. As well, conda is an environment management system. It easily creates, saves, loads, and switches between environments. For eg, if you had some legacy code that required Python 2, but all the rest of your workflows used Python 3, you could create a separate environment for Python 2 and run the workflow completely separately from all your others.

> ## Activity: Install conda and use it to install Pandas
> Download and run the miniconda install shell script, test that the installation has worked, and then use it to install the Python package pandas:
>~~~
>    $ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
>    $ bash Miniconda3-latest-Linux-x86_64.sh
>    $ source .bashrc
>    $ conda -V
>    $ conda list
>    $ conda install pandas
>    $ conda list pandas
>~~~
> <br>
>
{: .challenge}

> ## Challenge
> Practice everything you've learned:
> 1. Download the data from the following URL - http://swcarpentry.github.io/python-novice-gapminder/files/python-novice-gapminder-data.zip
> 2. Use apt to install the unzip program.
> 3. Unzip the data files.
>
> > ## Solution
> >
> >~~~
> >    $  wget http://swcarpentry.github.io/python-novice-gapminder/files/python-novice-gapminder-data.zip
> >    $  sudo apt install unzip
> >    $  unzip python-novice-gapminder-data.zip
> >~~~
> >
> {: .solution}
{: .challenge}

> ## Activity: Use Pandas to examine the data
>
>~~~
> ipython
> import pandas as pd
>
>data = pd.read_csv('data/gapminder_gdp_americas.csv')
>print(data.describe())
>~~~
> <br>
>
{: .challenge}
