---
title: "Launching an Instance"
teaching: 45
exercises: 0
questions:
- "Let's launch an instance"
objectives:
- "Review all launch options"
- "Launch a VM and connect with ssh"
keypoints:
- "You learnt how to start an instance using Openstack and the Nimbus Cloud;"
- "You learnt how to connect with an SSH client to a Linux instance."
---

## The steps to launch a virtual machine

**1. Set a name**

![Launch Details]({{ page.root }}/fig/Launch_details.png)

**2. Define a source image (Ubuntu LTS 16.04)**

![Launch Source]({{ page.root }}/fig/Lauch_source.png)

**3. Select a flavor (select m2.small)**

![Launch Flavor]({{ page.root }}/fig/Launch_flavor.png)

**4. Select a network (select "Private Network")**

![Launch Networks]({{ page.root }}/fig/Launch_networks.png)

**5. Check security groups (include previously created SSH access)**

![Launch Security Groups]({{ page.root }}/fig/Launch_security_groups.png)

**6. Click on "Launch Instance"

## Let's go!
![Launch Instance Post Click]({{ page.root }}/fig/Launch_instance_click.png)

![Launch Instance Done]({{ page.root }}/fig/Launch_instance_click2.png)

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
