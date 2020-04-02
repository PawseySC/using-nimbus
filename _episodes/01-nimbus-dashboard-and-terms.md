---
title: "Dashboard"
teaching: 10
exercises: 10
questions:
- "What is a Nimbus instance?"
- "Where can I manage my Nimbus instance?"
objectives:
- "Describe at a high level how Nimbus works using Cloud terminology."
- "Identify plots and graphs on the Nimbus dashboard."
- "Discuss how to use plots and graphs to manage your Nimbus instance/s."
keypoints:
- "Use the Nimbus dashboard, available from a web browser, to manage your instance, including to help you determine whether you need more/less resources."
- "Log on to the [Nimbus dashboard](https://nimbus.pawsey.org.au) using your project username and password."
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
> * **Key Pair**:
>    Key pairs allow access to your instance, think of them as a more secure username and password.
> * **IP Address**:
>    The virtual address of your instance.
> * **Volume Storage**:
>    Similar to an external hard drive you attach to one or multiple instances. Includes both the root volume (where the OS and programs are installed) and any data volumes that you’ll create where you store your data.  
><br><br>
> <kbd><img src="{{ page.root }}/fig/Terminology.png" /></kbd>
{: .keypoints}

<br>
> ## Activity: Login to Nimbus
>
> 1.	Go to [https://nimbus.pawsey.org.au](https://nimbus.pawsey.org.au). This is the URL for the Nimbus login.
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
>    1. Start by exploring the 'Compute' tab. Note that when you log in, you start in the 'Overview' panel of the 'Compute' tab.
>    2. Review the current quota and usage of your instance (right plots).
>    3. Locate and click on 'Instances' and 'Key Pairs' within the 'Compute' tab. We will be using these in later episodes. Both of these panels are empty at the moment however.
>
> <kbd><img src="{{ page.root }}/fig/Overview_dashboard.png" /></kbd>
>
{: .challenge}
