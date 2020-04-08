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

## Two roles with Nimbus
There are two distinct roles that need to be performed when using Pawsey's cloud computing. The first is the typical role you have with your local laptop or desktop computer, ie using the processing and storage resources available to you to perform your research. This might include: moving, cleaning and visualising data; writing and or installing programs to analyse data. The difference with cloud computing is of course you are working remotely, rather than on a local machine. The primary means by which this is done is via a Secure Shell (SSH) over a Command Line Interface (CLI). You will begin using SSH in episode 4.

The second role is an administrative and management role, wherein you monitor, allocate, and manage the resources allocated to your project. This is achieved via a web-based interface, the Nimbus dashboard. From your dashboard you are able to create, configure, start, stop, modify, and delete instances within your project. This episode begins your exploration of the dashboard.

<kbd><img src="{{ page.root }}/fig/diagram-nimbus.png" /></kbd>


> ## Activity: Log in to Nimbus
>
> 1.	Go to [https://nimbus.pawsey.org.au](https://nimbus.pawsey.org.au). This is the URL for the Nimbus login.
> 2.	Log in, by either:
> * Using your project username and password, if you are a current Nimbus user
> * Using the username and password sent to you, if you are a new Nimbus user
>
>     As shown below, for **Domain**, type **pawsey**. Then type your user name and password.
>
> <kbd><img src="{{ page.root }}/fig/nimbus_login_screen.png" /></kbd>
{: .challenge}


> ## Activity: Explore the Nimbus Dashboard
>
> Become familiar with navigating the Nimbus dashboard. You'll see there is a menu on the left side with a number of different tabs. You can use these tabs to monitor and manage different aspects of your project.
>
>    1. Start by exploring **Compute**. Note that when you log in, you start in the **Overview** page of the **Compute** tab is displayed.
>    2. Review the current quota and usage of your instance (right plots).
>    3. Locate and click **Instances** and **Key Pairs** - both under the **Compute** tab. We will be using these in later episodes. Both of these panels are empty at the moment however.
>    4. Return to **Overview**. Why do some plots already show usage when you haven't yet set up any instances?
>
> <kbd><img src="{{ page.root }}/fig/Overview_dashboard.png" /></kbd>
>
{: .challenge}
