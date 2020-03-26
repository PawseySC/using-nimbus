---
title: "Dashboard"
teaching: 20
exercises: 0
questions:
- "A quick overview of the Nimbus Interface"
objectives:
- "Get an overview of the mechanics of using Nimbus"
- "Learn some key language of cloud computing"
keypoints:
- "We use ssh to connect to instances and the nimbus web interface to create and manage instances."
---

## How does it work?

You will use two independent tools to manage and use Nimbus.  You will (usually) use a Secure Shell (SSH) connection to run jobs and do work on your instance.  Meanwhile, you will use the Nimbus dashboard, its web interface, to manage your instances(virtual machines).

![The Nimbus workflow]({{ page.root }}/fig/diagram-nimbus.png)

## Login to Nimbus

You need to have a Nimbus login account to proceed in this training.  If you are at a Pawsey training event, then your instructor will provide a username and password you can use for the day.  Alternatively if you have a Nimbus project you can use your project username and password.

The Nimbus dashboard is at [https://nimbus.pawsey.org.au](https://nimbus.pawsey.org.au)
Open this URL now in a browser window, you will see the login window (below).  As shown, for "domain", enter 'pawsey' and your user name and password.

![Login Screen]({{ page.root }}/fig/nimbus_login_screen.png)

Now that you are logged in we'll explore the various facets of the user interface.

### The Nimbus Dashboard
Let's take a closer look at the dashboard and the main components we'll be using:

![The Nimbus Dashboard]({{ page.root }}/fig/Overview_dashboard.png)

You'll see there is a menu on the left side of the view, where you can manage different aspects of your Nimbus project. When you login you start in the **Overview** panel of the **Compute** tab. So on the right you can see the various plots that show current quota and usage. The two other panels of the Compute tab we will be using are **Instances** and **Key Pairs**. Both of these panels are empty at the moment, so click on the **Network** tab and select the **Security Groups** panel.

![Security groups]({{ page.root }}/fig/Security_dashboard.png)

 You'll see two groups already exist and each has a 'Manage Rules' button on the far right under the 'Actions' heading. The second of these buttons also has a downward pointing arrow indicating a pull-down menu. This is a common and useful way of selecting actions you want to perform when managing your instance.


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
