---
title: "Security Groups"
teaching: 15
exercises: 0
questions:
- "Let's have a look at network security"
objectives:
- "Understand that security groups can be created to expose services"
- "Understand that limiting access improves security"
keypoints:
- "Security groups can be created to meet specific needs"
---

> ## During training with an instructor
>
> During the training with instructor, the security groups will be pre-populated and all these steps are purely informative.
{: .callout}

## What are Security Groups?

**Security Groups** are the tool you use to protect access to your instance.  Remember that in order to gain access you will use SSH (Secure-Shell).

SSH is an encrypted network protocol which connects over port 22, so your **Security Groups** must allow for at least these connections.

The "port" mentioned here is a number used by the system to define a network communication protocol.  HTTP, which you may be familiar with, normally uses port 80.

## Less is better

Each port you open on an instance is a potential vulnerability, so we strongly recommend you limit open ports to those strictly necessary for your work.

## How do you make new groups and rules?

To make a security group, you will go to the Network / Security Groups section and click **Create Security Group**:

![Manage Security Groups]({{ page.root }}/fig/Nimbus_Security_Groups.png)


First you give your security group a name:

![Create Security Groups]({{ page.root }}/fig/Nimbus_create_Security_Groups.png)

Then you can go back to the security group management pane and click **Manage Rules**.  Here we can add rules.  **Ingress** means connections can come in to your instance, and **Egress** means connections that can go out from your instance.

![Manage Security Groups Rules]({{ page.root }}/fig/Nimbus_manage_security_group_rules.png)

You can create a custom rule:

![ Security Group Add Rule]({{ page.root }}/fig/Nimbus_Security_add_rule.png)

Or you can select a rule from the predefined list

![ Security Group Add Rule List]({{ page.root }}/fig/Nimbus_Security_add_rule_options.png)
