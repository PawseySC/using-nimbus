---
title: "Launching an Instance"
teaching: 0
exercises: 0
questions:
- "Let's launch an instance"
objectives:
- "Review all launch options"
- "Launch a VM and connect with ssh"
keypoints:
- "First key point."
---

![Launch Details]({{ page.root }}/fig/Launch_details.png)

![Launch Source]({{ page.root }}/fig/Lauch_source.png)

![Launch Flavor]({{ page.root }}/fig/Launch_flavor.png)

![Launch Networks]({{ page.root }}/fig/Launch_networks.png)

![Launch Security Groups]({{ page.root }}/fig/Launch_security_groups.png)

![Launch Security Groups]({{ page.root }}/fig/Launch_security_groups.png)

![Launch Instance Post Click]({{ page.root }}/fig/Launch_instance_click.png)

![Launch Instance Done]({{ page.root }}/fig/Launch_instance_click2.png)

## Now let's give the VM an IP number

![Launch Manage IP]({{ page.root }}/fig/Manage_Floating_IP.png)

![Launch Post IP]({{ page.root }}/fig/Associate_floating_IP_successful.png)

## Managing a VM
![Instance Actions]({{ page.root }}/fig/Instance_actions.png)

## Let's log in
Now, back to your terminal window to login to your instance:
* We will access our instances using a secure shell connection

What you need:
1. Your instance’s IP address -> get this from the instance overview in your dashboard
    xxx.xxx.xxx.xxx

2. Your login name -> this depends on the name of the Linux OS image you selected
    Login names:

    | Fedora/Centos/Scientific Linux | **ec2-user** |
    | Debian  | **debian** |
    | Ubuntu  | **ubuntu** |

3. The location and name of your private key pair
    My_Key_Pair.pem or .key

**Now you can log in**

    $ ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.##.###  

## if it all worked...

![Successful login]({{ page.root }}/fig/nimbus_logged_in.png)
