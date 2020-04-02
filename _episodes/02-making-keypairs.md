---
title: "Authentication"
teaching: 5
exercises: 5
questions:
- "What are key pairs and why do we need them?"
- "How do we set up key pairs for Nimbus?"
objectives:
- "Describe how key pairs are used to protect your Nimbus instance."
- "Generate a key pair for your instance using the Nimbus dashboard."
keypoints:
- "Key pairs establish a public-private (lock-key) combination so you can securely access your Nimbus instance."
- "Your keypair file is private, and should be treated like a password.  Do not share it with anyone, or lose it."
- "You can easily use the Nimbus dashboard to create your key pair (or import an existing key pair)."

---

To maintain a secure system, we require all Nimbus users to have a keypair. Keypairs take the form of public (think: 'lock') and private (think: 'key') key files.  These files are presented together to securely authenticate (login) to a Nimbus instance. Without a keypair you cannot access your instance, as the username/password login option is disabled by default.

> ## Secure access
> The username/password login is not set up for new instances, as it is a less secure method of authentication than keypairs.
{: .keypoints}

> ## Activity: Generating a Key Pair
>  1. Login to the Nimbus dashboard and navigate to the **Key Pairs** panel under the Compute menu.  
>  2. Click the **Create Key Pair** button. The **Create Key Pair** dialog box will appear.
>  3. Enter a name - this can be anything, but try to make it meaningful - then click the **Create Keypair** button.  The dialog box will close and your browser will download the private key file with the name you gave it and a .pem extension, for eg `my_first_key.pem`. Make sure to save your private key file somewhere safe so you can access it later.
>
> <kbd><img src="{{ page.root }}/fig/Nimbus_Create_Key_Pairs.png" /></kbd>
>
{: .challenge}
