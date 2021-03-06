---
title: "Best practices"
teaching: 10
exercises: 0
questions:
- "What's the best way to use cloud?"
- "What can I use my instance for?"
- "How do I apply for a Nimbus allocation?"
objectives:
- "Learn best practices for the cloud"
- "Know the process to get an allocation"
keypoints:
- "Snapshot your instance"
- "Google is your friend"
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
Once you have your shiny new VM, you are now the master of your own destiny.  You have flexibility to download software to start doing science.  Listed below are some tips on installing some common software packages that you might like to use however "Googling" your linux flavour / version along with the software will often give you success.  Also listed as details on moving data to your instance



**Machine learning**

If you are interested in machine learning the following site has many good resources (from beginner to advanced) [https://towardsdatascience.com/](https://towardsdatascience.com/)



**Copying files**

Courtsey of NeCTAR training materials - [Copying files](http://training.nectar.org.au/package07/sections/copyFiles.html)


---

## Applying for a VM
Compared to applying for time on one of our supercomputers, the process for applying for an allocation on Nimbus is less demanding.  You can apply at any time of the year by visiting the link below

### To get access visit: [https://apply.pawsey.org.au](https://apply.pawsey.org.au) ###
