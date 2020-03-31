---
title: "Creation"
teaching: 5
exercises: 30
questions:
- "How do we create an instance?"
objectives:
- "Review all instance options"
- "Launch an instance"
keypoints:
- "You use the Nimbus dashboard to configure an instance how you wish before creating it."
---

This episode will step you through the process of launching an instance on Nimbus.  You will be making decisions on the specifications of your instance.  When you are doing this for the first time it can seem like a lot of information to take in before you can start an instance. As you become more familiar with this process it will become less intimidating.
<br><br>


> ## Activity: Create an Instance
> ### 1. Start the process
>
> Login to the Nimbus dashboard. From the left hand menu select **Compute** then **Instances**. Click on the **Launch Instance** button.
>
> <kbd><img src="{{ page.root }}/fig/Create_instance_button.png" /></kbd><br><br>
>
> ### 2. Choose a Name
>
> Clicking on **Lauch Instance** brings up the __Launch Instance__ window. Configuration options are listed by topic in the menu on the left. These can be progressed through sequentially via the navigation buttons on the bottom right, or can be selected by clicking directly on the desired topic. The initial step is to give your instance a name.  It doesn't matter what you call it; usually we recommend giving your instance a name related to the task it will be performing.
> Then click __next__.
>
><kbd><img src="{{ page.root }}/fig/Launch_details2.png" /></kbd><br><br>
>
> ### 3. Choose a source image
>
> The selection of the Source Image defines the operating system that will be used to launch your instance.  We include some images directly from upstream providers, as well as curating some of our own (marked with Pawsey in the name).
>
> **NB:** Selecting a GPU image will not allocate you a GPU :)
>
> Make sure that Boot Source is set to **Image**, set **Volume Size** to 10GB, and **Delete Volume on Instance Delete** should be set to Yes.
>
> <kbd><img src="{{ page.root }}/fig/Instance_source_selection.png" /></kbd><br>
>
> For training purposes we will be using the Pawsey Ubuntu 18.04 image. Click the up-arrow to the right of the image name so that it is listed under **allocated** as shown below. Then click __Next__.  
>
><kbd><img src="{{ page.root }}/fig/Instance_source_selection2.png" /></kbd><br><br>
>
> ### 4. Select a flavor
>
> A 'flavour' (or 'flavor' because our software prefers US spelling) defines the characteristics of an instance.  We provide a range of flavors that vary based on the number of virtual CPUs, memory, and storage available to your instance.
>
> If you're at a training event, then select __m2.small__.  If you're self-learning, choose any flavour that you wish.
>
><kbd><img src="{{ page.root }}/fig/Instance_flavour2.png" /></kbd><br><br>
>
> ### 5. Select a network
>
> The **Networks** tab is where you will define the networking available to your instance.
>
> Nimbus projects have networking prepared for you.  Using a training account you will see a network named something like  __cou010-network__.  If you are using your own project you will see a network name similar to this.
>
> You will also see a __Public external__ network.  We will use this now since you get a public IP address automatically.
>
><kbd><img src="{{ page.root }}/fig/Instance_network.png" /></kbd><br><br>
>
>
> ### 6. Check security groups
>
> We skip over __Network Ports__ at this stage, as they are only for more advanced use of an instance. Instead go straight to __Security Groups__.
>
> The security group called __default__ is selected already, and you should leave it like that.  It allows outgoing connections from your instance, and communication between your instances if you need more than one.  
>
>Nimbus projects are preconfigured with a security group to permit incoming SSH access.  This is required by most users.  The security group to add is named something like __cou010-SSH__.
>
><kbd><img src="{{ page.root }}/fig/Instance_security.png" /></kbd><br><br>
>
> ### 7. Select a key pair
>
> The key pair provides secure access to your instance. When selected for an instance, the public key is installed during creation of the instance, thereby ensuring access is only given when you have the corresponding private key.
>
> **NB:** If you select a key pair for which you do not have, or have lost, the private key, it is not possible to gain access to the instance.
>
><kbd><img src="{{ page.root }}/fig/Instance_keypairs.png" /></kbd><br><br>
>
>
> ### 8. Launch instance
> Selecting the key pair is the last step necessary for creation of your instance. So you should now click __Launch Instance__. The launch window will close, and you should see a new instance show up in your instances panel (probably the only item you see listed). You will see it change state as it starts up.
>
><kbd><img src="{{ page.root }}/fig/Launch_instance_click.png" /></kbd><br>
>
> When the launch process is complete, your instance details should look something like this:
>
><kbd><img src="{{ page.root }}/fig/Launch_instance_click2.png" /></kbd><br>
>
{: .challenge}
<br>
> ## Problems
> It is easy to forget a step or misconfigure required elements.  The result may be errors on starting the instance, or you may be unable to connect once the instance is up and running. Whether you are working through this in a class, or by yourself, we find that (usually) the easiest fix is to delete the instance and make a new one, paying close attention to each step.
{: .keypoints}

> ## What did we do?
>
> - Gave our instance a name
> - Selected an operating system source image
> - Provisioned our instance by selecting a flavor of memory, CPUs, and storage
> - Gave our instance access to the outside world by selecting the public external network
> - Selected a security group to allow SSH access
> - Selected a key pair so we can login to our instance
> - Created our instance
>
{: .checklist}
