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

2. Your login name -> this depends on the name of the Linux OS image you selected
    Login names:

    | Fedora/Centos/Scientific Linux | **fedora/centos/root** |
    | Debian  | **debian** |
    | Ubuntu  | **ubuntu** |

3. The location and name of your private key pair
    My_Key_Pair.pem or .key

**Now you can log in**

    $ ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###  

## If it all worked...

![Successful login]({{ page.root }}/fig/nimbus_logged_in.png)
