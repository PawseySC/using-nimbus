---
title: "How does Nimbus work for users?"
teaching: 20
exercises: 0
questions:
- "A quick overview of the Nimbus Interface"
objectives:
- "Get an overview of the mechanics of using Nimbus"
- "Learn some key language of cloud computing with Nimbus"
keypoints:
- "We use ssh to connect to a virtual machine and the nimbus web interface to manage."
---

## How does it work?

You will use two independant tools to manage and use Nimbus.  You will (usually) use a Secure Shell (SSH) connection to run jobs and do work on your virtual machine.  Meanwhile, you will use the Nimbus dashboard, its web interface, to manage your virtual machine(s) (instances).

![The Nimbus workflow]({{ page.root }}/fig/diagram-nimbus.png)

### The Nimbus Dashboard
Let's take a closer look at the dashboard:

![The Nimbus Dashboard]({{ page.root }}/fig/Overview_dasboard.png)

You'll see there is a menu on the left side of the view, where you can manage different aspects of your Nimbus project.  On the right you can see the various plots that show current quota and usage.  We will explore the other sections of the interface as we make our way through the material.

## Key Terminology

There are some key terms we need to discuss before we get started:

* **Allocation** or **Quota**:
    The infrastructure specifications you have been allocated for a specific project (# of instances, RAM, steorage space, etc)
* **Instance**:
    A virtual machine (located on Nimbus servers, you access via the SSH)
* **Instance Flavor**:
    The size of your instance (RAM, VCPUs, root disk, ephemeral disk)
* **Key Pair**:
    This is a key you generate which allows you to login to your instance
* **Security Groups**:
    These are the incoming and outgoing connection permissions you allow for your instance (IP addresses, ports, etc.).
    You must allow at least allow SSH connections to access your instance!
* **IP Address**:
    The virtual address of your instance
* **Snapshot & Image**:
    A snapshot is a copy of a volume you can create before deleting your instance. You can launch this image later as a new instance (useful for booting a fully configured virtual machine with all required applications pre-installed)
* **Volume & Object Storage**:
    Similar to an external hard drive you attach and detach to one or multiple instances (useful for big and important data).
