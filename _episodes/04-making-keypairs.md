---
title: "First steps: making keypairs"
teaching: 0
exercises: 0
questions:
- "What are keypairs and why do we need them?"
- "How do we setup keypairs for Nimbus?"
objectives:
- "Logon to Nimbus and make a keypair"
keypoints:
- "Create keypairs using the Nimbus dashboard."
- "Keypairs can be imported using the dashboard"
- "Functional keypairs are required for starting a virtual machine"
---
## Login to Nimbus

If you are at a Pawsey training event, then your instructor will provide a username and password you can use for the day.  Alternatively if you have a Nimbus project you can use your project username and password.

The Nimbus dashboard is at https://nimbus.pawsey.org.au
Open this URL now in a browser window, you will see the login window (below).  As shown, for "domain", enter 'pawsey' and your user name and password.

![Login Screen]({{ page.root }}/fig/nimbus_login_screen.png)

Now that you are logged in you can have a look around the various panes of the user interface.

## Generating keypairs

Our first action is to generae keypairs.  Keypairs take the form of public (think: 'lock') and private (think: 'key') key files.  These files are presented together to securely authenticate (login) to a Nimbus virtual machine.  **Why do this?**  We do this because the username/password login is not set up for new VMs (by design).

There are two methods of creating keypairs.

1. **From the Nimbus Dashboard**
    This will automatically create a lock in your Dashboard and download the key to your local computer (.pem file)

2. **From within your Terminal Window**
    This will create two separate files, your key and lock (.key and .key.pub)
    You need to import your lock (public key file) to the dashboard for Nimbus to recognize it


## Keypairs from the Nimbus dashboard

Go to the Key Pairs item under the Compute menu.  Click the button "Create Key Pair", and give your key pair a name.
![Create Keypairs]({{ page.root }}/fig/Nimbus_Create_Key_Pairs.png)

When done, your browser will download the .pem file.

![Download Keypairs]({{ page.root }}/fig/Nimbus_Download_Key_Pair.png)


## Keypairs from your terminal

This method will be very useful to you, if you wish to make a keypair that you can use with multiple systems (in addition to your Nimbus VMs).

Run the command as shown below (with a useful name for "My_Key_Pair_Name");

```
popocatepetl:~ markg$ ssh-keygen  -t  rsa  -f  My_Key_Pair_Name.key
Generating public/private rsa key pair.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in My_Key_Pair_Name.key.
Your public key has been saved in My_Key_Pair_Name.key.pub.
The key fingerprint is:
SHA256:OKdIxLawp/A6X36umLm1gT5EcE60ClzHR2ttz8z30h4 markg@popocatepetl.local
The key's randomart image is:
+---[RSA 2048]----+
| .......         |
|o +o.. .o        |
|.*o + .o o       |
|..o= .... =      |
|o.. + o S  = .   |
| o.= . +    . o  |
| .+ = .      . E |
|.o.B o.       o .|
|.oBo++.        . |
+----[SHA256]-----+
```



## Installing keypairs

> ## If you're using JupyterHub
>
> We need to move your .pem file to JupyterHub.  Your instructor will discuss at this point.
{: .callout}

If you used Nimbus to make the keypair, you should move the downloaded .pem file somewhere where you can find it later.

1. If using Mac, store in your .ssh/ directory
```
$ cp ~/Downloads/file_name.pem  ~/.ssh
```
2. If using PC it will depend on the Linux emulator you are using, but creating a specific local directory is a universally acceptable procedures
```
$ cp ~/Downloads/file_name.pem  ~/Desktop/My_Directory
```

If you created your keypair on the commandline, then you will need to get the public key data and import this into Nimbus using the "Import Key Pair" button.

First get the public key data

```
popocatepetl:~ markg$ more  My_Key_Pair_Name.key.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDVZTn98qxxovMDnui8L+WynWptAGS8sR2GIJ4HE+9v8lHlcSiKDze07o/SIb+RQR7FFvLchAD2xLxiF8mB+4SUhaoxWXZGhc8RBLXpSMD6tJNT9VNxd99mI7g6rq3HMpSZDE5YTxSweDy13qRmc6gBXWNGjUHV3eUv6pHKthbs1v/MjsA7nkYdINiCwpgawJ7fdyJJ61vkrO7+tjkdRFBBTn2O8ELTMYEssM/hwHZt00RWOVjXylaQK766yF6Qhog2pQc2gsUXQLown9Hzga8QVxvMxCY9cVh2lxtBVjDuv1HWwC1PZhYa9QlLf+jsITyOzEfPuNidZvyWnjxei6+P markg@popocatepetl.local
```

Then copy/paste this into the keypair import interface, as shown:

![Import Keypairs]({{ page.root }}/fig/Nimbus_import_key_pair.png)

## Final (Important) step

By default, Key Pairs do not have the appropriate permissions required to be used to connect (ssh) to your instances.

**Permissions = who (users, group, world) can read, write, execute a file**

To allow the correct permissions we want to allow only the user (you) to have at least read and write privileges:

```
$  chmod 600 My_Key_Pair.key   or   $ chmod 600 My_Key_Pair.pem
```

If you skip step, you will encounter errors when you try and use the key.