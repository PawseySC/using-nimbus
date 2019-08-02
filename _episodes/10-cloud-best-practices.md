---
title: "Cloud best practices"
teaching: 10
exercises: 0
questions:
- "What's the best way to use cloud?"
- "What can I use my VM for?"
- "How do I apply for a Nimbus allocation?"
objectives:
- "Learn best practices for the cloud"
- "Understand how to install software on my VM"
- "Know the process to get an allocation"
---

## Best practices 
1. **Snapshot your instance!**

    This saves your Root Disk and allows you to launch a fully configured instance with all packages already installed

2. **Document your steps so you know what you did**

    Create a configuration script, save a copy out of the cloud and keep it up to date
    history -> prints all previous commands
    history  |  keyword -> searches a specific command

3. **Update! Every time you login!**

    ```sudo apt-get update && sudo apt-get update```-> updates packages and security
    Older versions of packages and operating systems eventually lose support from their creators

4.  **Be Green and keep it elastic**

    The cloud still uses electricity and is shared, when you’re no longer using it -> turn it off!
    
---

## Ideas for using your VM
Once you have your shiny new VM, you are now the master of your own destiny.  You can start downloading software to start doing science.  Listed below are some tips on installing some common software packages that you might like to use.

**Conda**

Conda is an open source package management system and environment management system.   that runs on Windows, macOS, and Linux. Conda quickly installs, runs and updates packages and their dependencies. Conda easily creates, saves, loads, and switches between environments on your local computer. It was created for Python programs but it can package and distribute software for any language.

You can get started by downloading the installer suitable for your instance.  Miniconda installer page is given below [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html)

Further info on [Linux installation](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)


**Machine learning**

If you are interested in machine learning the following site has many good resources (from beginner to advanced) [https://towardsdatascience.com/](https://towardsdatascience.com/)

---

## Applying for a VM
Compared to applying for time on one of our supercomputers, the process for applying for an allocation on Nimbus is less demanding.  You can apply at any time of the year by visiting the link below

### To get access visit: [https://apply.pawsey.org.au](https://apply.pawsey.org.au) ### 
