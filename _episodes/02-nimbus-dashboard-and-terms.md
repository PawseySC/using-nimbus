---
title: "Management"
teaching: 10
exercises: 0
questions:
- "What is a Nimbus instance?"
- "Where can I manage my Nimbus instance?"
objectives:
- "Describe at a high level how Nimbus works using Cloud terminology."
- "Identify plots and graphs on the Nimbus dashboard."
- "Discuss how to use plots and graphs to manage your Nimbus instance/s."
keypoints:
- "Use the Nimbus dashboard, available from a web browser, to manage your instance, including to help you determine whether you need more/less resources."

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
{: .callout}

>## Two roles with Nimbus
>There are two distinct roles that need to be performed when using Pawsey's cloud computing. The first is the typical role you >have with your local laptop or desktop computer, ie using the processing and storage resources available to you to perform >your research. This might include: moving, cleaning and visualising data; writing and or installing programs to analyse data. >The difference with cloud computing is of course you are working remotely, rather than on a local machine. The primary means >by which this is done is via a Secure Shell (SSH) over a Command Line Interface (CLI). You will begin using SSH in episode 5.
>
>The second role is an administrative and management role, wherein you monitor, allocate, and manage the resources allocated to >your project. This is achieved via a web-based interface, the Nimbus dashboard. From your dashboard you are able to create, >configure, start, stop, modify, and delete instances within your project.
>
><kbd><img src="{{ page.root }}/fig/diagram-nimbus.png" /></kbd>
{: .callout}

> ## Managing your project
> An example of a Nimbus dashboard can be seen below, showing the overview page of the **Compute** tab. There are a number of different tabs available from the menu on the left side. You can use these to monitor and manage different aspects of your project.
><br><br>
> *Question: Why do some plots in the overview already show usage when there are no instances?*
><br><br>
><kbd><img src="{{ page.root }}/fig/Overview_dashboard.png" /></kbd>
><br>
> > ## Answer
> >
> {: .solution}
{: .challenge}
