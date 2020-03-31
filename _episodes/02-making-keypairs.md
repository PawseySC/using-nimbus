---
title: "Authentication"
teaching: 5
exercises: 5
questions:
- "What are keypairs and why do we need them?"
- "How do we setup keypairs for Nimbus?"
objectives:
- "Logon to the Nimbus dashboard and make a keypair."
keypoints:
- "Functional keypairs are required for starting an instance."
- "Your keypair file is private, and should be treated like a password.  Do not share it with anyone, or lose it."

---

To maintain a secure system, we require all Nimbus users to have a keypair. Keypairs take the form of public (think: 'lock') and private (think: 'key') key files.  These files are presented together to securely authenticate (login) to a Nimbus instance. Without a keypair you cannot access your instance, as the username/password login option is disabled by default.

> ## Secure access
> The username/password login is not set up for new instances, as it is a less secure method of authentication than keypairs.
{: .keypoints}

> ## Activity: Generating a Key Pair
>  1. Login to the Nimbus dashboard and naivgate to the Key Pairs item under the Compute menu.  
>  2. Click the button **Create Key Pair**, and a popup window will appear.
>  3. Enter a name - this can be anything, but try to make it meaningful - then click the **Create Keypair**  button.  The popup will close and your browser will download the private key file with the name you gave it and a .pem extension, for eg `my_first_key.pem`. Make sure to save your private key file somewhere safe so you can access it later.
>
> <kbd><img src="{{ page.root }}/fig/Nimbus_Create_Key_Pairs.png" /></kbd>
>
{: .challenge}
