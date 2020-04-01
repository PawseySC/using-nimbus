---
title: "Access"
teaching: 5
exercises: 15
questions:
- "How do we access an instance?"
objectives:
- "Connect to an instance with ssh"

keypoints:
- "You learned how to connect with an SSH client to a Linux instance."

---

Access to an instance is achieved using using a Secure SHell (SSH) connection. For this you need a terminal, a Command Line Interface (CLI), either the native terminal app on Linux/Mac OS systems, clients like Putty or MobaXTerm on Windows systems, or even web-based terminals.

<br>


> ## Activity: Access an instance
>
> Head to your terminal window to login to your instance.<br>
> ### 1. You will need
> * __Your instance’s IP address__: get this from the instance overview in your dashboard
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
>    Your private key file permissions will need to be changed to work with your SSH client. As a security precaution, SSH will not work unless the key file is only readable by you. To make sure this is the case, run this command in your terminal, making sure you are in the directory which contains your key file:
>~~~
>     chmod 600 name_of_your_key.pem
>~~~
> ### 2. Login
> Type the following into your terminal, using your login name and the instance's IP address:
>~~~
>  $ ssh -i name_of_your_key.pem login_name@###.###.###.###
>~~~
><br>
> For example, if I used an Ubuntu image for my instance, and the instance IP is 146.118.66.157, and my key pair is `my_first_key.pem`, I would enter:
>~~~
>  $ ssh -i my_first_key.pem ubuntu@146.118.66.157
>~~~
><br>
> You should then see something like that shown in the figure below:<br><br>
><kbd><img src="{{ page.root }}/fig/nimbus_logged_in.png" /></kbd><br><br>
> Congratulations, you have now successfully logged in to your instance.
{: .challenge}

> ## If you get an error...
>
> 1) ssh: Could not resolve hostname \342\200\223i name or service unknown error - [link](http://tumblr.gudge.com/post/18186353550/ssh-could-not-resolve-hostname-342200223i)
>
>When using MobaXTerm if you cut and paste the *ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###* example you will get the wrong hyphen in the "-i" part and throw a confusing error
>
>**Solution:** Don't cut and paste example - manually type in ssh syntax
{: .keypoints}
