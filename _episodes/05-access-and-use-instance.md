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

Access to an instance is achieved using a Secure SHell (SSH) connection. For this you need a terminal, either the native terminal app on Linux/Mac OS systems, clients like Windows Terminal or  MobaXTerm on Windows systems, or even a web-based terminal.

<br>



> ## Before you start
> There are three items you need to make sure you have on hand to sign into your instance:
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
> * __The location and name of your private key__:<br>
>    In episode 3 you created your keypair and wrote down the location where you saved the private key. For the following exercises you should either `cd` to that location, or provide the path to that location in your commands. So, for example, if you are in the directory where your key is located, the command would look like:
>~~~
>    $ `command` `name_of_your_key`.pem
>~~~
> <br>
> or alternatively, you could use:
>~~~
>    $ `command` `path/name_of_your_key`.pem
>~~~
>
><br>
> When you have all these things, the last thing you need to do is make sure your private key is secure. To do this you will modify its permissions so that only you have access to it. This is achieved differently depending upon the operating system you are using. Select your system below and follow the instructions:
><br><br>
> > ## Linux, Unix, or Mac OS
> > On Unix based systems SSH will not work unless the key file is only readable by you. To make it so, run this command in your terminal:
> >~~~
> >  $  chmod 600 `name_of_your_key`.pem
> >~~~
> > To check that the permissions are now set correctly, now type
> >~~~
> >  $  ls -l `name_of_your_key`.pem
> >~~~
> > and you should see an output like the following:
> ><br>
> ><kbd><img src="{{ page.root }}/fig/Private_key_lsl2.png" /></kbd>
> {: .solution}
> > ## Windows
> > On Windows, SSH will work regardless of whether the key file is only readable by you. To modify the key's permissions, locate it in Windows Explorer, right-click on it then 
> > select **Properties**. Navigate to the **Security** tab and click **Advanced**.
> ><br><br>
> ><kbd><img src="{{ page.root }}/fig/Private_key_properties2.png" /></kbd>
> ><br><br>
> > Disable inheritance and remove all permissions. Then add a new permissions entry.
> ><br>
> ><kbd><img src="{{ page.root }}/fig/Private_key_no_permissions2.png" /></kbd>
> ><br><br>
> > Click **Select a principal** and enter your user name.
> ><br>
> ><kbd><img src="{{ page.root }}/fig/Private_key_select_principal2.png" /></kbd>
> ><kbd><img src="{{ page.root }}/fig/Private_key_selected_principal2.png" /></kbd>
><br><br>
> > Clear all permissions then grant yourself **Full Control** and apply the changes.
> ><br>
> ><kbd><img src="{{ page.root }}/fig/Private_key_full_control2.png" /></kbd>
> ><br><br>
> > Your key file should now have security settings that look like those shown below.
> ><br>
> ><kbd><img src="{{ page.root }}/fig/Private_key_modified_control.png" /></kbd>
> ><br>
> {: .solution}
> #### Now you are ready to access your instance for the first time.
{: .callout}

> ## Activity: Access an instance
> Type the following into your terminal, using your login name and the instance's IP address:
>~~~
>  $ ssh -i `name_of_your_key`.pem `login_name`@###.###.###.###
>~~~
><br>
> For example, if I used an Ubuntu image for my instance, and the instance IP is 146.118.67.137, and my key pair is `test-instance.pem`, I would enter:
>~~~
>  $ ssh -i test-instance.pem ubuntu@146.118.67.137
>~~~
><br>
>You will receive a message saying:
>~~~
> The authenticity of host '146.118.67.137 (146.118.67.137)' can't be established.
>~~~
><br>
> It will then give a key fingerprint, and ask
>~~~
> Are you sure you want to continue connecting (yes/no)?
>~~~
><br>
>If you are sure (and/or confirm the fingerprint), answer 'yes' to continue. It will then give a warning,
>~~~
> Warning: Permanently added '146.118.67.137' (ECDSA) to the list of known hosts.
>~~~
><br>
> meaning that next time you log in using this key and IP address you won't receive this message.
> Having done that, your terminal should then display something like that shown in the figure below:<br><br>
><kbd><img src="{{ page.root }}/fig/nimbus_logged_in2.png" /></kbd><br><br>
> #### Congratulations, you have now successfully logged on to your instance!
{: .challenge}

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
>
> For more, see the [Nimbus Documentation](https://support.pawsey.org.au/documentation/display/US/Common+Issues).
{: .callout}
