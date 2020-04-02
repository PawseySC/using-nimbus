---
title: "Instance Access"
teaching: 10
exercises: 10
questions:
- "How do I securely log into a Nimbus instance?"
objectives:
- "Discuss what is needed to log in to a Nimbus instance."
- "Successfully log in to a Nimbus instance."

keypoints:
- "You can securely log in to your Nimbus instance from Linux, Mac, Unix, or Windows, using Secured Shell (SSH)."

---

Access to an instance is achieved using a Secure SHell (SSH) connection. For this you need a terminal, a Command Line Interface (CLI), either the native terminal app on Linux/Mac OS systems, clients like Putty or MobaXTerm on Windows systems, or even a web-based terminal.

<br>


> ## Activity: Access an instance
> ### Before you start
> There are three items to make sure you have on hand to sign into your instance:
> * __Your instance’s IP address__: get this from the instance overview in the Nimbus dashboard (__Compute>Instance__)
>
>    ###.###.###.###
><br><br>
> * __Your login name__: this depends on the name of the Linux OS image you selected
>
>    Login names:
>
>    | Ubuntu  | **ubuntu** |
>    | Centos | **centos** |
>    | Fedora | **fedora** |
>    | Scientific Linux | **root** |
>    | Debian  | **debian** |
>
> * __The location and name of your private key pair__:<br>
>    If you haven't done so previously, your private key file permissions will need to be changed to work with your SSH client. As a security precaution, SSH will not work unless the key file is only readable by you. To do so, run this command in your terminal, making sure you are in the directory which contains your key file:
>~~~
>     chmod 600 `name_of_your_key`.pem
>~~~
>
> ### Login
> Type the following into your terminal, using your login name and the instance's IP address:
>~~~
>  $ ssh -i `name_of_your_key`.pem `login_name`@###.###.###.###
>~~~
><br>
> For example, if I used an Ubuntu image for my instance, and the instance IP is 146.118.66.157, and my key pair is `my_first_key.pem`, I would enter:
>~~~
>  $ ssh -i my_first_key.pem ubuntu@146.118.66.157
>~~~
><br>
> Your terminal should then display something like that shown in the figure below:<br><br>
><kbd><img src="{{ page.root }}/fig/nimbus_logged_in.png" /></kbd><br><br>
> **Congratulations, you have now successfully logged in to your instance!**
{: .challenge}

<br>
> ## Troubleshooting
> It is easy to forget a step or misconfigure required elements. Whether you are working through this in a class, or by yourself, we find that (usually) the easiest fix is to delete the instance and make a new one, paying close attention to each step.<br><br>
> There are some common errors which we detail below:
> 1. *ssh: Could not resolve hostname \342\200\223i name or service unknown error - [link](http://tumblr.gudge.com/post/18186353550/ssh-could-not-resolve-hostname-342200223i)*
>
>     When using MobaXTerm if you cut and paste the *ssh –i my_first_key.pem ubuntu@###.###.###.###* example, the pasted command will include an incorrect character for the hypen, which the system will not understand and will result in an error.
>
>    **Solution:** Do not cut and paste the example - manually type in the ssh command.
> 2. *ssh: Timeout*
>
>    Most often the result of not including a security group which allows ssh access on port 22.
>
>    **Solution:** Go to the Nimbus dashboard and allocate an ssh access security group to your instance.
{: .keypoints}
