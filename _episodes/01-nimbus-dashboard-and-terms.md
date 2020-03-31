---
title: "Dashboard"
teaching: 10
exercises: 10
questions:
- "How do you interact with Nimbus?"
objectives:
- "Learn some key language of cloud computing."
- "Get an overview of the mechanics of using the Nimbus dashboard."
keypoints:
- "We use the Nimbus dashboard to create and manage instances."
- "You log on to the dashboard at https://nimbus.pawsey.org.au using your project username and password."
---


You will use two independent tools when working on Nimbus.  You will use a Secure Shell (SSH) connection to run jobs and do work on your instance.  Meanwhile, you will use the Nimbus dashboard, its web interface, to manage your instances. This episode focuses on getting you familiar with the dashboard.

<kbd><img src="{{ page.root }}/fig/diagram-nimbus.png" /></kbd>

> ## Terminology
>
> There are some key terms we need to discuss before we get started:
>
> * **Allocation** or **Quota**:
>     The infrastructure limits you have been allocated for a specific project (# of instances, RAM, storage space, etc). You select an allocation when you request Nimbus access through the application portal.  
> * **Instance**:
>    A virtual machine located on Nimbus servers, that you use in place of your laptop or desktop computer.
> * **Instance Flavor**:
>    On your application, you request the instance “flavor” or configuration that you want your instance to have (memory, storage, processing power).
> * **Key Pair**:
>    Key pairs allow access to your instance, think of them as a more secure username and password.
> * **Security Groups**:
>    These are the incoming and outgoing connection permissions you allow for your instance (IP addresses, ports, etc.).
>    You must allow at least allow SSH connections to access your instance – so YOU can access it.
> * **IP Address**:
>    The virtual address of your instance.
> * **Volume Storage**:
>    Similar to an external hard drive you attach to one or multiple instances. Includes both the root volume (where the OS and programs are installed) and any data volumes that you’ll create where you store your data.  
> *  **Snapshot & Image**:
>    A snapshot is a copy of a volume. You can take a snapshot of your root volume before deleting your instance. You can then launch this copied image later as a new instance, which is useful for recreating a previously fully configured instance that contains all required applications pre-installed.
{: .keypoints}


> ## Activity: Login to Nimbus
>
> 1.	Go to https://nimbus.pawsey.org.au. This is the URL for the Nimbus login.
> 2.	Log in, by either:
> * Using your project username and password, if you are a current Nimbus user
> * Using the username and password sent to you, if you are a new Nimbus user
>
>     As shown below, for "domain", enter 'pawsey' and your user name and password.
>
> <kbd><img src="{{ page.root }}/fig/nimbus_login_screen.png" /></kbd>
{: .challenge}




> ## Activity: Explore the Nimbus Dashboard
>
> Become familiar with navigating the Nimbus dashboard. You'll see there is a menu on the left side with a number of different tabs. You can use these tabs to monitor and manage different aspects of your project.
>
> ### Compute
>    1. Start by exploring the 'Compute' tab. Note that when you log in, you start in the 'Overview' panel of the 'Compute' tab.
>    2. Review the current quota and usage of your instance (right plots).
>    3. Locate and click on 'Instances' and 'Key Pairs' within the 'Compute' tab. We will be using these in later episodes. Both of these panels are empty at the moment however.
>
> <kbd><img src="{{ page.root }}/fig/Overview_dashboard.png" /></kbd>
>
> ### Network
> 1. Click the 'Network' tab, then select the 'Security Groups' panel.
> 2. You can implement new, or modify existing, network access rules from within this panel.  
> 3. By default there is at least one security group for your project. There is an action button on the right which allows you to manage the rules for each of your security groups.
>
> <kbd><img src="{{ page.root }}/fig/Security_dashboard.png" /></kbd>
{: .challenge}
