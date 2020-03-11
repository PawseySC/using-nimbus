---
title: "Launching an Instance"
teaching: 45
exercises: 0
questions:
- "Let's launch an instance"
objectives:
- "Review all launch options"
- "Launch an instance"
keypoints:
- "You learned how to start an instance using Openstack and the Nimbus Cloud."
---

## The steps to launch an instance

This lesson will step you through the process of launching an instance on Nimbus.  You will be making decisions on the specifications of your instance.  When you are doing this for the first time it can seem like a lot of information to take in before you can start an instance. As you become more familiar with this process it will become less intimidating.

It is easy to forget a step or misconfigure required elements.  The result may be errors on starting the instance, or you may be unable to connect once the instance is up and running.  If this happens, don't worry (we've all made the same mistakes when we were getting started).  If you're working through this lesson with an instructor, they can come and advise you on where you might have gone wrong.  Whether you are working through this in a class, or by yourself, we find that (usually) the easiest fix is to delete the instance and make a new one, paying close attention to each step.

### OK, let's get started...

From the left hand menu select **Compute** then **Instances**.  Click on the **Launch Instance** button.

![Launch Details]({{ page.root }}/fig/Create_instance_button.png)


## 1. Set a name

The first step is to give your instance a name.  It doesn't matter what you call it; usually we recommend giving your instance a name related to the task it will be performing.

![Launch Details]({{ page.root }}/fig/Launch_details.png)


## 2. Choose a source image

The selection of the Source Image defines the operating system that will be used to launch your instance.  We include some images directly from upstream providers, as well as curating some of our own (marked with Pawsey in the name).

Make sure that Boot Source is set to **Image**, and **Delete Volume on Instance Delete** should set to No.

> ## Delete Volume on Instance Delete?
>
> We suggest that you set this to No.  This does mean that if you delete your instance, its root volume will stay behind and will continue to use up your quota until you delete it.  On the other hand, it means you can recreate your instance without losing its configuration.
>
{: .callout}

For training purposes you will launch an instance using the latest Pawsey curated Ubuntu image, named something like **Ubuntu 18.04 - 2019-09 - Pawsey**.  Click the up-arrow to the right of the image name so that it is listed under **allocated**.

Note that there are other images you can select, and you can create your own custom images for certain purposes.

If you need a specific flavour of Linux and you find that it is not listed you do have another option; it is possible to import external images, but our support for you in this instance will be very limited.  It is also possible to take one of the existing images or an external image and modify it before creating an instance from that custom iamge.

![Launch Source]({{ page.root }}/fig/Instance_source.png)


## 3. Select a flavour

A 'flavour' (or 'flavor' because our software prefers US spelling) defines the characteristics of an instance.  We provide a range of flavours that vary based on the number of cores available to your instance.

If you're at a training event, then select __m2.small__.  If you're self-learning, choose any flavour that you wish.



![Launch Flavor]({{ page.root }}/fig/Instance_flavour.png)


## 4. Select a network

The **Networks** tab is where you will define the networking available to your instance.

Nimbus projects have networking prepared for you.  Using a training account you will see a network named something like __cou010-network__.  If you are using your own project you will see a network name similar to this.

You will also see a __Public external__ network.  We will use this now since you get a public IP address automatically.

![Launch Networks]({{ page.root }}/fig/Instance_network.png)


## 5. Check security groups
#### Include an SSH security group
The security group called __default__ is selected already, and you should leave it like that.  It allows outgoing connections from your instance, and communication between your instances if you need more than one.  

Nimbus projects are preconfigured with a security group to permit incoming SSH access.  This is required by most users.  The security group to add is named something like __cou010-SSH__.

![Launch Security Groups]({{ page.root }}/fig/Instance_security.png)


## 6. Click on **Launch Instance**

## Let's go!

When you click __Launch Instance__ you should see a new instance show up in your list (probably the only item you see listed).  You will see it change state as it starts up.

![Launch Instance Post Click]({{ page.root }}/fig/Launch_instance_click.png)


When complete, your entry should look like this:

![Launch Instance Done]({{ page.root }}/fig/Launch_instance_click2.png)


## What if something went wrong?

> ## What did we do?
>
> - Selected an image and flavour
> - Selected a network
> - Selected a SSH security group
>
{: .checklist}

What can go wrong?
- If your instance does not start and gives an error message:  You might have selected the wrong network.


## Managing your instance

Let's have another look at that instance menu, because there's a lot there.  This is where you will perform management activities for your instance.

![Instance Actions]({{ page.root }}/fig/Instance_actions.png)

## Manage attachements

Select **Manage Attachments** from the drop-down menu of the data volume you created

![Nimbus Manage Attachments]({{ page.root }}/fig/nimbus_vol_manage_attachments.png)
