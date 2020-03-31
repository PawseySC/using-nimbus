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
- "Keypairs can be imported using the dashboard"
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

### Keypairs: getting more complicated

The process described in Episode 2 works well in training or when you are getting started with Nimbus.  What if your situation is more complicated?  We will now cover more specific cases around keypair usage.


> ## (optional) If you are using Windows with PuTTY
> 1. Open PuTTYgen (All Apps -> Putty -> Puttygen)
> 2. Click on the LOAD button.
> 3. Select the .pem file you just downloaded from the Nimbus Dashboard. If you cannot see your .pem file , select __All Files__ instead of __Putty Private Key Files__ from the dropdown bottom menu.
> 4. Set a new passphrase and confirm it for your private key.
> 5. Click on the __Save private key__ button and give it the name you prefer.
{: .solution}

> ## (optional) If you are using a native terminal (Linux / Mac / Unix)
>
> > ## If you used Nimbus to make the keypair
> >
> > If you used Nimbus to make the keypair, you should move the downloaded .pem file somewhere where you can find it later.
> >
> > Ensure the .ssh/ directory exists with the right permissions.
> > ~~~
> > $ mkdir -p ~/.ssh
> > $ chmod 700 ~/.ssh
> > ~~~
> > {: .output}
> > Store in your .ssh/ directory and rename it id_rsa (or give it another name if you have more than a private key)
> > ~~~
> > $ cp -i ~/Downloads/file_name.pem  ~/.ssh/id_rsa
> > ~~~
> > {: .output}
> > Ensure that only you (the user) have read and write permissions:
> > ~~~
> > $  chmod 600 ~/.ssh/id_rsa
> > ~~~
> > {: .output}
> {: .callout}
> > ## If you created your keypair on the command line
> >
> > If you created your keypair on the command line, then you will need to get the public key data and import this into Nimbus using the **Import Key Pair** button.
> >
> > First get the public key data
> > ~~~
> > popocatepetl:~ markg$ cat My_Key_Pair_Name.key.pub
> > ssh-rsa > AAAAB3NzaC1yc2EAAAADAQABAAABAQDVZTn98qxxovMDnui8L+WynWptAGS8sR2GIJ4HE+9v8lHlcSiKDze07o/SIb+RQR7FFvLchAD2xLxiF8mB+4SUhaoxWXZGhc8RBLXpSMD6tJNT9VNxd99mI7g6rq3HMpSZDE5YTxSweDy13qRmc6gBXWNGjUHV3eUv6pHKthbs1v/MjsA7nkYdINiCwpgawJ7fdyJJ61vkrO7+tjkdRFBBTn2O8ELTMYEssM/hwHZt00RWOVjXylaQK766yF6Qhog2pQc2gsUXQLown9Hzga8QVxvMxCY9cVh2lxtBVjDuv1HWwC1PZhYa9QlLf+jsITyOzEfPuNidZvyWnjxei6+P markg@popocatepetl.local
> > ~~~
> > {: .output}
> > Then copy and paste this into the keypair import interface, as shown:
> >
> > ![Import Keypairs]({{ page.root }}/fig/Nimbus_import_key_pair.png)
> {: .callout}
{: .solution}

---
**_NOTE:_**  There are other images you can select, and you can create your own custom images for certain purposes. At this stage you should only consider the default OS images, seek advice from Cloud team for more advanced usage.


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
