---
title: "Access and Use an Instance"
teaching: 45
exercises: 0
questions:
- "How do we access an instance?"
- "What are the first things we do on an instance?"
objectives:
- "Connect to an instance with ssh"
- "Attach and use a data volume with your instance"
keypoints:
- "You learned how to connect with an SSH client to a Linux instance."
- "You learned how to create a new filesystem and mount it in your instance."
- "You learned how to unmount and detach your volume, and reuse it."
---

## Let's log in
Head to your terminal window to login to your instance:
* We will access our instances using a Secure SHell (SSH) connection.

What you need:
1. __Your instance’s IP address__: get this from the instance overview in your dashboard
    ###.###.###.###

2. __Your login name__: this depends on the name of the Linux OS image you selected
    Login names:

    | Ubuntu  | **ubuntu** |
    | Centos | **centos** |
    | Fedora | **fedora** |
    | Scientific Linux | **root** |
    | Debian  | **debian** |

3. The location and name of your private key pair (if you are using Windows and Putty)
    My_Key_Pair.ppk


> ## If you're using Linux / Mac / Unix
>
>  $ ssh login_name@###.###.###.###
>
> or (if you have more than one private key)
>
>  $ ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###
{: .callout}

> ## If you're using Windows
>
> 1) Open Putty
>
> 2) Under "Host name (or IP address)" put: login_name@###.###.###.###
>
> 3) In the menu on the left, expand "SSH" and click on "Auth".
>
> 4) Under the section "Authentication parameters" click on "Browse...".
>
> 5) Select your previously create .ppk private key.
>
> 6) Click on "Open" to start the connection to your instance.
{: .callout}


## If it all worked...

![Successful login]({{ page.root }}/fig/nimbus_logged_in.png)


## If you get an error...

1) ssh: Could not resolve hostname \342\200\223i name or service unknown error - [link](http://tumblr.gudge.com/post/18186353550/ssh-could-not-resolve-hostname-342200223i)

When using MobaXTerm if you cut and paste the *ssh –i ~/.ssh/My_Key_Pair.pem login_name@###.###.###.###* example you will get the wrong hyphen in the "-i" part and throw a confusing error

**Solution:** Don't cut and paste example - manually type in ssh syntax

----

2) Asks for passphrase when no passphrase was created.

When creating a private keypair from Nimbus interface, it copies it to a clipboard, which you then have to save to your computer.  You need to ensure no extra characters are added and -----BEGIN RSA PRIVATE KEY----- and -----END RSA PRIVATE KEY----- present

**Solution:** Use nano, vi directly or other non-Windows text editor, should be something like below

![example private key]({{ page.root }}/fig/example private key.png)
