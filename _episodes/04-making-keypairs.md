---
title: "First steps: making keypairs"
teaching: 30
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

You need to have a Nimbus login account to proceed in this training.  If you are at a Pawsey training event, then your instructor will provide a username and password you can use for the day.  Alternatively if you have a Nimbus project you can use your project username and password.

The Nimbus dashboard is at [https://nimbus.pawsey.org.au](https://nimbus.pawsey.org.au)
Open this URL now in a browser window, you will see the login window (below).  As shown, for "domain", enter 'pawsey' and your user name and password.

![Login Screen]({{ page.root }}/fig/nimbus_login_screen.png)

Now that you are logged in you can have a look around the various panes of the user interface.

## Generating keypairs

Our first action is to generate keypairs.  Keypairs take the form of public (think: 'lock') and private (think: 'key') key files.  These files are presented together to securely authenticate (login) to a Nimbus virtual machine.  **Why do this?**  We do this because the username and password login is not set up for new VMs (by design).

There are two methods of creating keypairs.

1. **From the Nimbus Dashboard**
    This will automatically create a lock when selected for your instance through the Dashboard, and download the private key to your local computer (.pem file)

2. **(optional) From within your Terminal Window**
    This will create two separate files, your key and lock (.key and .key.pub)
    You need to import your lock (public key file) to the dashboard for Nimbus to recognize it


## Keypairs from the Nimbus dashboard

Go to the Key Pairs item under the Compute menu.  Click the button "Create Key Pair", and give your key pair a name.
![Create Keypairs]({{ page.root }}/fig/Nimbus_Create_Key_Pairs.png)

Enter a name for your keypair and click "Create Keypair".  The window will expand to show you something called your "private key".

![Download Keypairs]({{ page.root }}/fig/Nimbus_Download_Key_Pair.png)

Click the "Copy Private Key to Clipboard" button and make a new text file with the clipboard contents.  Traditionally we give this text file a ".pem" extention, so you might name it "mynewkey.pem" (for instance). We're going to use this pem file later, so keep it handy.

**Note** - If you are using JupyterHub in a Pawsey Training session, just run nano to create a new file e.g. "nano mynewkey.pem" and paste the private key into the new file - see [here](https://pawseysc.github.io/shell-hpc/03-create/index.html) for further info on nano from the Pawsey "Intro to Unix" course.

### Keypairs with JupyterHub (in person training)
From JupyterHub, click on the upload file button, select the key you just generated in the Nimbus web interface, and upload it (or if created in nano, it should already be there). We will need this file later to connect to our instance (virtual machine).

By default, once uploaded you private key permission will not be correct to be used in the next lessons with you SSH client. To fix that run:
~~~
chmod 600 name_of_your_key.pem
~~~

You can go to the next section now.

# Keypairs: getting more complicated

The process described above works well in training or when you are getting started with the use of Pawsey systems.  What if your situation is more complicated?  We will now cover specific cases around keypair usage.

## Keypairs from your terminal

 This method will be very useful to you, if you wish to make a keypair that you can use with multiple systems (in addition to your Nimbus instances).

 Run the command as shown below (with a useful name for "My_Key_Pair_Name");

 ~~~
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
 ~~~
 {: .output}


## Storing your keypairs
Store your private key in a safe place! Losing your private key means losing all access to your instances. Not even the Nimbus support can give you access to your instances if you have lost your private key.

{: .output}

> ## (optional) If you are using Windows with PuTTY
>
> 1. Open PuTTYgen (All Apps -> Putty -> Puttygen)
> 2. Click on the LOAD button.
> 3. Select the .pem file you just downloaded from the Nimbus Dashboard. If you cannot see your .pem file , select "All Files" instead of "Putty Private Key Files" from the dropdown bottom menu.
> 4. Set a new passphrase and confirm it for your private key.
> 5. Click on the "Save private key" button and give it the name you prefer.
{: .solution}

> ## (optional) If you are using a native terminal (Linux / Mac / Unix)
>
> > ## If you used Nimbus to make the keypair
> >
> > If you used Nimbus to make the keypair, you should move the downloaded .pem file somewhere where you can find it later.
> >
> > Ensure the .ssh/ directory exists with the right permissions.
> > ~~~
> > $ mkdir -p ~/.ssh
> > $ chmod 700 ~/.ssh
> > ~~~
> > {: .output}
> > Store in your .ssh/ directory and rename it id_rsa (or give it another name if you have more than a private key)
> > ~~~
> > $ cp -i ~/Downloads/file_name.pem  ~/.ssh/id_rsa
> > ~~~
> > {: .output}
> > Ensure that only you (the user) have read and write permissions:
> > ~~~
> > $  chmod 600 ~/.ssh/id_rsa
> > ~~~
> > {: .output}
> {: .callout}
> > ## If you created your keypair on the commandline
> >
> > If you created your keypair on the commandline, then you will need to get the public key data and import this into Nimbus using the "Import Key Pair" button.
> >
> > First get the public key data
> > ~~~
> > popocatepetl:~ markg$ cat My_Key_Pair_Name.key.pub
> > ssh-rsa > AAAAB3NzaC1yc2EAAAADAQABAAABAQDVZTn98qxxovMDnui8L+WynWptAGS8sR2GIJ4HE+9v8lHlcSiKDze07o/SIb+RQR7FFvLchAD2xLxiF8mB+4SUhaoxWXZGhc8RBLXpSMD6tJNT9VNxd99mI7g6rq3HMpSZDE5YTxSweDy13qRmc6gBXWNGjUHV3eUv6pHKthbs1v/MjsA7nkYdINiCwpgawJ7fdyJJ61vkrO7+tjkdRFBBTn2O8ELTMYEssM/hwHZt00RWOVjXylaQK766yF6Qhog2pQc2gsUXQLown9Hzga8QVxvMxCY9cVh2lxtBVjDuv1HWwC1PZhYa9QlLf+jsITyOzEfPuNidZvyWnjxei6+P markg@popocatepetl.local
> > ~~~
> > {: .output}
> > Then copy/paste this into the keypair import interface, as shown:
> >
> > ![Import Keypairs]({{ page.root }}/fig/Nimbus_import_key_pair.png)
> {: .callout}
{: .solution}
