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
- "Functional keypairs are required for starting an instance"
---


## Generating keypairs

Our first action is to generate keypairs.  Keypairs take the form of public (think: 'lock') and private (think: 'key') key files.  These files are presented together to securely authenticate (login) to a Nimbus instance.

**Why do this?**  We do this because the username and password login is not set up for new instances (by design).


## Keypairs from the Nimbus dashboard
Go to the Key Pairs item under the Compute menu.  Click the button **Create Key Pair**, and give your key pair a name.
![Create Keypairs]({{ page.root }}/fig/Nimbus_Create_Key_Pairs.png)

Enter a name for your keypair and click **Create Keypair**.  The popup will close and your browser will download the private key file, named something like `my_key.pem`.  Save it somewhere safe so you can access it later.  This file is private, and should be treated like a password.  Do not share it with anyone, or lose it.


> ### Keypairs with JupyterHub (Pawsey Training sessions)
> From JupyterHub, click on the upload file button, select the key you just generated in the Nimbus web interface, and upload it.  We will need this file later to connect to our instance.
>
>![Upload Key]({{ page.root }}/fig/Jupyter_upload_arrow.png)
>



# Keypairs: getting more complicated

The process described above works well in training or when you are getting started with the use of Pawsey systems.  What if your situation is more complicated?  We will now cover specific cases around keypair usage.



> ## (optional) If you are using Windows with PuTTY
> 1. Open PuTTYgen (All Apps -> Putty -> Puttygen)
> 2. Click on the LOAD button.
> 3. Select the .pem file you just downloaded from the Nimbus Dashboard. If you cannot see your .pem file , select __All Files__ instead of __Putty Private Key Files__ from the dropdown bottom menu.
> 4. Set a new passphrase and confirm it for your private key.
> 5. Click on the __Save private key__ button and give it the name you prefer.
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
> > ## If you created your keypair on the command line
> >
> > If you created your keypair on the command line, then you will need to get the public key data and import this into Nimbus using the **Import Key Pair** button.
> >
> > First get the public key data
> > ~~~
> > popocatepetl:~ markg$ cat My_Key_Pair_Name.key.pub
> > ssh-rsa > AAAAB3NzaC1yc2EAAAADAQABAAABAQDVZTn98qxxovMDnui8L+WynWptAGS8sR2GIJ4HE+9v8lHlcSiKDze07o/SIb+RQR7FFvLchAD2xLxiF8mB+4SUhaoxWXZGhc8RBLXpSMD6tJNT9VNxd99mI7g6rq3HMpSZDE5YTxSweDy13qRmc6gBXWNGjUHV3eUv6pHKthbs1v/MjsA7nkYdINiCwpgawJ7fdyJJ61vkrO7+tjkdRFBBTn2O8ELTMYEssM/hwHZt00RWOVjXylaQK766yF6Qhog2pQc2gsUXQLown9Hzga8QVxvMxCY9cVh2lxtBVjDuv1HWwC1PZhYa9QlLf+jsITyOzEfPuNidZvyWnjxei6+P markg@popocatepetl.local
> > ~~~
> > {: .output}
> > Then copy and paste this into the keypair import interface, as shown:
> >
> > ![Import Keypairs]({{ page.root }}/fig/Nimbus_import_key_pair.png)
> {: .callout}
{: .solution}
