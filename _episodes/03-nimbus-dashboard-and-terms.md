---
title: "How does Nimbus work for users?"
teaching: 0
exercises: 0
questions:
- "A quick overview of the Nimbus Interface"
objectives:
- "Get an overview of the mechanics of using Nimbus"
- "Learn some key language of cloud computing with Nimbus"
keypoints:
- "We use ssh to connect to a virtual machine and the nimbus website to manage."
---

## How does it work?

You will use two independant tools to manage and use Nimbus.  You will (usually) use a Secure Shell (SSH) connection to run jobs and do work on your virtual machine.  Meanwhile, you will use the Nimbus dashboard, a website we maintain, to manage your virtual machine/s.  This is shown below;

![The Nimbus workflow]({{ page.root }}/fig/diagram-nimbus.png)

Let's take a closer look at the dashboard;

![The Nimbus Dashboard]({{ page.root }}/fig/Overview_dasboard.png)

You'll see here there is a menu on the left side of the view, here you will be able to explore the core functionality across Nimbus.  At first glance on the right you see the various plots that show current quota and usage.  We'll be exploring the other sections of the website as we make our way through the 

## Key Terminology

There are some key terms we need to discuss before we get started

* **Allocation**
    the infrastructure specifications you have been allocated for a specific project (# of instances, RAM, memory, etc.)
* **Instance**
    a virtual machine (located on Nimbus servers, you access via the SSH)
* **Instance Flavor**
    the size of your instance (RAM, VCPUs, root disk, ephemeral disk)
* **Key Pair**
    this is a key you generate which allows you to login to your instance
* **Security Groups**
    these are the incoming/outgoing permissions you allow for your instance (IP addresses, ports, etc.).
    You must allow at least allow ssh connections to access your instance!

* **IP Address**
    the virtual address of your instance
* **Snapshot & Image**
    a snapshot is a copy of your Root Disk storage you create before terminating your instance. You can launch this image later as a new instance (useful for booting a fully configured virtual machine with all required applications pre-installed)
* **Volume & Object Storage**
    similar to an external hard drive you attach and detach to one or multiple instances (useful for big and important data or fully configured virtual machines).
