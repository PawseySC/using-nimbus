---
title: "Access"
teaching: 45
exercises: 0
questions:
- "How do we access an instance?"
objectives:
- "Connect to an instance with ssh"

keypoints:
- "You learned how to connect with an SSH client to a Linux instance."

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

    Once saved (or saved and uploaded) your private key file permission will need to be changed to work with your SSH client in the next lessons. Run this command in your terminal:
~~~
     chmod 600 name_of_your_key.pem
~~~

----

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
