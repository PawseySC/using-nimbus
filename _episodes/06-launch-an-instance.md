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
- "You learned how to start an instance using Openstack and the Nimbus Cloud."
- "You learned how to connect with an SSH client to a Linux instance."
---

## The steps to launch an instance

This lesson will step you through the process of launching an instance (virtual machine or VM) on Nimbus.  You will be making decisions on the specifications of your instance and finally using a terminal to log on to your instance.  When you are doing this for the first time it can seem like a lot of information to take in before you can start an instance. As you become more familiar with this process it will become less intimidating.

It is easy to forget a step or misconfigure required elements.  The result may be errors on starting the instance, or you may be unable to connect once the instance is up and running.  If this happens, don't worry (we've all made the same mistakes when we were getting started).  If you're working through this lesson with an instructor, they can come and advise you on where you might have gone wrong.  Whether you are working through this in a class, or by yourself, we find that (usually) the easiest fix is to delete the instance and make a new one, paying close attention to each step.

### OK, let's get started...

From the left hand menu select **Compute** then **Instances**.  Click on the **Launch Instance** button.

![Launch Details]({{ page.root }}/fig/Create_instance_button.png)


## 1. Set a name

The first step is to give your instance a name.  It doesn't matter what you call it; usually we recommend giving your instance a name related to the task it will be performing.

![Launch Details]({{ page.root }}/fig/Launch_details.png)


## 2. Choose a source image

The selection of the Source Image defines the operating system that will be used to launch your instance.  We include some images directly from upstream providers, as well as curating some of our own (marked with Pawsey in the name).

Make sure that Boot Source is set to **Image**, and **Delete Volume on Instance Delete** should set to No.

> ## Delete Volume on Instance Delete?
>
> We suggest that you set this to No.  This does mean that if you delete your instance, its root volume will stay behind and will continue to use up your quota until you delete it.  On the other hand, it means you can recreate your instance without losing its configuration.
>
{: .callout}

For training purposes you will launch an instance using the latest Pawsey curated Ubuntu image, named something like **Ubuntu 18.04 - 2019-09 - Pawsey**.  Click the up-arrow to the right of the image name so that it is listed under **allocated**.

Note that there are other images you can select, and you can create your own custom images for certain purposes.

If you need a specific flavour of Linux and you find that it is not listed you do have another option; it is possible to import external images, but our support for you in this instance will be very limited.  It is also possible to take one of the existing images or an external image and modify it before creating an instance from that custom iamge.

![Launch Source]({{ page.root }}/fig/Launch_source.png)


## 3. Select a flavour

A 'flavour' (or 'flavor' because our software prefers US spelling) defines the characteristics of an instance.  We provide a range of flavours that vary based on the number of cores available to your instance.

If you're at a training event, then select __m2.small__.  If you're self-learning, choose any flavour that you wish.



![Launch Flavor]({{ page.root }}/fig/Launch_flavor.png)


## 4. Select a network

The **Networks** tab is where you will define the networking available to your instance.

Nimbus projects have networking prepared for you.  Using a training project you will select the network named something like __cou050-network__.  If you are using your own project you will see a network name similar to this.

You will also see a __Public external__ network.  Cloud admins have recently changed it so you can use this and get a public IP address automatically.  As a user, you can use either method to get a public IP to SSH into.

![Launch Networks]({{ page.root }}/fig/Launch_networks.png)


## 5. Check security groups (include previously created SSH access)
#### Include the __default__ security group
The security group called __default__ is selected already, and you should leave it like that.  It allows outgoing connections from your instance, and communication between your instances if you need more than one.  

Nimbus projects are preconfigured with a security group to permit incoming SSH access.  This is required by most users.  The security group to add is named something like __cou050-SSH __.

![Launch Security Groups]({{ page.root }}/fig/Launch_security_groups.png)


## 6. Click on **Launch Instance**

## Let's go!

When you click __Launch Instance__ you should see a new instance show up in your list (probably the only item you see listed).  You will see it change state as it starts up.

![Launch Instance Post Click]({{ page.root }}/fig/Launch_instance_click.png)


When complete, your entry should look like this:

![Launch Instance Done]({{ page.root }}/fig/Launch_instance_click2.png)


## What if something went wrong?

> ## What did we do?
>
> - Selected an image and flavour
> - Selected a network
> - Selected a SSH security group
>
{: .checklist}

What can go wrong?
- If your instance does not start and gives an error message:  You might have selected the wrong network.


## Now let's give the instance an IP address
An IP address is a unique number that identify your instance and allows you to connect to it from anywhere on the internet.  We need to select one to use in the instance, only once this is done can we actually login to an instance.

Go your instance listed in the Instances view.  If you open the menu on the right side of the instance entry you will see

![Instance Actions]({{ page.root }}/fig/Instance_actions.png)


If you click __Associate Floating IP__ you will see this:

![Launch Manage IP]({{ page.root }}/fig/Manage_Floating_IP.png)


Click the __+__ button and you will see the __Allocate Floating IP__ view, here you should click __Allocate IP__ and you will now have an IP address you can use.

![Launch Post IP]({{ page.root }}/fig/Associate_floating_IP_successful.png)


## Managing your instance

Let's have another look at that instance menu, because there's a lot there.  This is where you will perform management activities for your instance.

![Instance Actions]({{ page.root }}/fig/Instance_actions.png)


## Let's log in
Now, back to your terminal window to login to your instance:
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

2) Asks for passphrase when no passphrase was created.

When creating a private keypair from Nimbus interface, it copies it to a clipboard, which you then have to save to your computer.  You need to ensure no extra characters are added and -----BEGIN RSA PRIVATE KEY----- and -----END RSA PRIVATE KEY----- present

**Solution:** Use nano, vi directly or other non-Windows text editor, should be something like below

![example private key]({{ page.root }}/fig/example private key.png)
