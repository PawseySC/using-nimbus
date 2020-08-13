---
title: "Data"
teaching: 10
exercises: 0
questions:
- "How do we move data to and from an instance?"
- "How do we backup data?"
objectives:

keypoints:

---

## Transfer Protocols

HTTP is the protocol used to fetch data from web servers. It is a very simple protocol that is built upon TCP/IP. 

SCP is a network protocol which uses SSH for data transfer and uses the same mechanisms for authentication. 

SFTP is another protocol packaged with SSH. Like SCP it uses a secure connection to transfer files, and has the added advantage of being able to traverse the filesystem on both the local and remote systems.

There are many graphical file management tools which have transfer protocols like SFTP integrated into them (for eg cyberduck or filezilla), but in this lesson we will only be introducing command line tools.


> ## Activity: Moving data
> We'll start by using the HTTP protocol in the form of the `wget` tool. To download a file to your instance using `wget` you need the URL for the file. The command is then simply:
>~~~
>  $ wget `file_URL`
>~~~
> 
>  For example, in the figure below you can see the setup page for the Software Carpentry lesson on the Unix Shell. By right-clicking on the data-shell.zip link you can copy the URL to the clipboard.
> <br>
><kbd><img src="{{ page.root }}/fig/Data_copy_link.png" /></kbd><br><br>
> Then, from the terminal logged into your instance, type the wget command, paste the link and then hit enter. You should see output like that below:
> <br>
><kbd><img src="{{ page.root }}/fig/Data_wget_file.png" /></kbd><br><br>
>
> You can then check that the file is there:
>~~~
>  ubuntu@test:~$ ls -l
>~~~
><br>
> HTTP tools like `wget` are good for online data, but what about data you have on your machine, or another machine at your institute? This is where tools that use SSH are useful. So, for example, to copy a file from your local machine to your instance using `scp`:
>~~~
>  $ scp -i `name_of_your_key`.pem `local_file_path` `login_name`@###.###.###.###:`instance_file_path`
>~~~
><br>
> This command might be starting to look a little complicated, but you just need to remember that most CLI copying tools, just like `cp`, require you to provide where something is that needs to be copied (origin), and where it needs to be copied to (destination) in that order.
> 
> Lets try that now, either by creating a text file, or copying a file you already have. For example, from your local terminal:
>~~~
>  $ nano random.txt
>  $ scp -i ~/.ssh/test.pem random.txt ubuntu@146.118.67.254:
>~~~
><br>
> Note: If you leave the instance file path empty, it will copy your file into your ubuntu users home directory.
>
>  So now if we log in to our instance we can check that the transfer worked:
>~~~
>  $ ssh -i ~/.ssh/test.pem ubuntu@146.118.67.254
>  ubuntu@test:~$ ls -l
>~~~
><br>
{: .challenge}

>## Exercise
> To copy a file from your instance to your local computer, you have to swap the order of the origin and the destination. As an exercise, copy the  data-shell.zip file we downloaded to the instance, from the instance to your local machine.
> 
> > ## Solution
> >
> >~~~
> >    $  scp -i ~/.ssh/test.pem ubuntu@146.118.67.254:data-shell.zip .
> >    $  ls -l data-shell.zip
> >~~~
> >
> {: .solution}
{: .challenge}




> ## Activity: Managing data via SFTP
> SCP is a popular solution that can prove helpful if you simply need to transfer files. However, if you need to list remote directories, create new directories, remove files, or do other administrative tasks, SFTP can do the job.
> 
> We can open up an SFTP session, just like when logging in via ssh, by issuing the following command:
>~~~
>  $ sftp -i `name_of_your_key`.pem `login_name`@###.###.###.###
>~~~
><br>
> You will connect to your instance and your prompt will change to an SFTP prompt.
> 
{: .challenge}


## Backing Up

> ## Activity: rsync
> 
{: .challenge}

> ## Activity: OpenStack tools
> 
{: .challenge}
