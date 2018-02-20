---
title: "Simplified security and networking"
teaching: 0
exercises: 0
questions:
- "Let's have a look at security and networking"
objectives:
- "Understand that security groups can be created to expose services"
- "Understand that limiting access improves security"
keypoints:
- "Security groups and networks can be modified to meet specific needs"
---
## What are security groups?

Security groups are the tool you use protect access to your virtual machine.  Remember that to access your cloud instance you will use SSH (Secure-Shell).

SSH is a password encrypted network protocol which allows you to login to your instance securely.

The password is a Key Pair (the private key is located on your local terminal and public key located on your instance) SSH connects over port 22, so your Security Groups must allow for at least these connections.

The "port" mentioned here is a number used by the system to define a network communication protocol. HTTP, which you may be familiar with, is port 80.

## Less is better

Each port you open on a VM a potential vulnerability, so we strongly recommend you limit open ports to those strictly necessary for your work,.

## How do you make new groups/rules?

To make a security group, you will go to the Network / Security Groups section and hit "Create Security Group";

![Manage Security Groups]({{ page.root }}/fig/Nimbus_Security_Groups.png)


First you give your group a name:

![Create Security Groups]({{ page.root }}/fig/Nimbus_create_Security_Groups.png)

Then you can go back to the security group management pane and click "Manage Rules".  Here we can add rules.  "Ingress" means things can come in to your VM, and "Egress" means things that can go out from your VM.

![Manage Security Groups Rules]({{ page.root }}/fig/Nimbus_manage_security_group_rules.png)

You can create a custom rule:

![ Security Group Add Rule]({{ page.root }}/fig/Nimbus_Security_add_rule.png)

Or you can select a rule from the predefined list

![ Security Group Add Rule List]({{ page.root }}/fig/Nimbus_Security_add_rule_options.png)
