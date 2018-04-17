---
title: "Launching an Instance"
teaching: 45
exercises: 0
questions:
- "Let's launch an instance"
objectives:
- "Review all launch options"
- "Launch a virtual machine and connect to it with ssh"
keypoints:
- "You learnt how to start an instance using Openstack and the Nimbus Cloud;"
- "You learnt how to connect with an SSH client to a Linux instance."
---

## The steps to launch a virtual machine

This lesson will step you through the process of launching a virtual machine (VM) on Nimbus.  You will be making decisions on the specifications of your VM and finally using a terminal to logon to your VM.  When you are doing this for the first time it can seem like a lot of information to take in before you can start a VM. As you become more familiar with this process it will become less intimidating.

It is easy to forget a step or misconfigure required elements.  The result maybe errors on starting the VM, or you may be unable to connect once the VM is up and running.  If this happens, don't worry (we've all made the same mistakes when we were getting started).  If you're working through this lesson with an instructor, she or he can come and advise you on where you might have gone wrong.  Whether you are working through this in a class, or by yourself, we find that (usually) the easiest fix is to delete the VM and make a new one, paying close attention to each step.

### OK, let's get started...


## 1. Set a name

The first step is to give your VM a name.  It doesn't matter what you call it, usually we recommend giving your VM a name related to the task it will be performing.

![Launch Details]({{ page.root }}/fig/Launch_details.png)

## 2. Choose a source image

The selection of the Source Image defines the operating system that will be used to launch your VM.

First make sure that Boot Source is set to "Image", and Volume Size is set to 5GB (You can modify the boot size later, before you first launch the VM). "Delete Volume on Instance Delete" should set to Yes.

> ## Delete Volume on Instance Delete?
>
> We usually suggest that you set this to YES.  It will result in the volume used for your VM to be deleted if you delete your VM, but this is a good thing.
>
{: .callout}

For training purposes you will launch a VM using the "Ubuntu LTS 16.04" image.  Click the up-arrow to the right of the image name so that it is listed under "allocated".

You will note that there are other images you can select.  Some of these are visible, but not intended for individual user deployment (the Hadoop or Spark images).  We do support the Ubuntu LTS 16.04 and Centos 7 image for you to run VMs.

If you need a specific flavour of Linux that we do not offer you should know that it is possible to import external images.
![Launch Source]({{ page.root }}/fig/Lauch_source.png)

## 3. Select a flavour

A 'flavour' (or 'flavor' because our software prefers US spelling) defines the characteristics of a VM.  We provide a range of flavours that vary based on the number of cores available to your VM.  

If you're at a training event, then select __m2.small__.  If you're self-learning, choose any flavour that you wish.

![Launch Flavor]({{ page.root }}/fig/Launch_flavor.png)

## 4. Select a network (select "Private Network")

![Launch Networks]({{ page.root }}/fig/Launch_networks.png)

## 5. Check security groups (include previously created SSH access)

![Launch Security Groups]({{ page.root }}/fig/Launch_security_groups.png)

## 6. Click on "Launch Instance"

## Let's go!
![Launch Instance Post Click]({{ page.root }}/fig/Launch_instance_click.png)

![Launch Instance Done]({{ page.root }}/fig/Launch_instance_click2.png)

## What if something went wrong?

> ## What did we do?
>
> - one thing
> - two thing
>
{: .checklist}

## Now let's give the VM an IP address
An IP address is a unique number that identify your instance and allows you to connect to it from anywhere on the internet.

![Launch Manage IP]({{ page.root }}/fig/Manage_Floating_IP.png)

![Launch Post IP]({{ page.root }}/fig/Associate_floating_IP_successful.png)

## Managing a VM
![Instance Actions]({{ page.root }}/fig/Instance_actions.png)

## Let's log in
Now, back to your terminal window to login to your instance:
* We will access our instances using a Secure SHell (SSH) connection.

What you need:
1. Your instance’s IP address -> get this from the instance overview in your dashboard
    ###.###.###.###

2. Your login_name -> this depends on the name of the Linux OS image you selected
    Login names:

    | Fedora/Centos/Scientific Linux | **fedora/centos/root** |
    | Debian  | **debian** |
    | Ubuntu  | **ubuntu** |

3. The location and name of your private key pair (if you are using Windows and Putty)
    My_Key_Pair.ppk

> ## If you're using Linux / Mac / Unix
>  
>  $ ssh login_name@###.###.###.###
> or (if you have more than one private key)
>  $ ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###  
{: .callout}

> ## If you're using Windows
>  
> 1) Open Putty
> 2) Under "Host name (or IP address)" put: login_name@###.###.###.###
> 3) In the menu on the left, expand "SSH" and click on "Auth".
> 4) Under the section "Authentication parameters" click on "Browse...".
> 5) Select your previously create .ppk private key.
> 6) Click on "Open" to start the connection to your instance.
{: .callout}


## If it all worked...

![Successful login]({{ page.root }}/fig/nimbus_logged_in.png)
