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

Transfer protocols are the different sets of rules governing the exchange or transmission of data between devices. The functionality of each protocol can give advantages depending on the situation in which they are used.

HTTP is the protocol used to fetch data from web servers. It is a very simple protocol that is built upon TCP/IP and transfers via unencrypted text. 

SCP is a network protocol which ensures the authenticity, encryption, and confidentiality of data by making use of SSH for transferring files. In SCP you do not need to start an FTP session or log into the remote host explicitly for transfer.

SFTP is another protocol packaged with SSH. Like SCP it uses a secure connection to transfer files, however unlike SCP it allows you to traverse the filesystem on both the local and remote systems.

There are many graphical file management tools which have transfer protocols like SFTP integrated into them (for eg cyberduck or filezilla), but in this lesson we will only be introducing command line tools.


> ## Activity: Copying files with HTTP
> We'll start by using the HTTP protocol in the form of the `wget` tool. To download a file to your instance using `wget` you need the URL for the file. The command is then simply:
>~~~
>  $ wget `file_URL`
>~~~
> 
>  For example, in the figure below you can see the setup page for the Software Carpentry lesson on the Unix Shell. By right-clicking on the data-shell.zip link you can copy the URL to the clipboard.
> <br>
> 
><kbd><img src="{{ page.root }}/fig/Data_copy_link.png" /></kbd><br><br>
> Then, from the terminal logged into your instance, type the wget command, paste the link and then hit enter. You should see output like that below:
> <br>
><kbd><img src="{{ page.root }}/fig/Data_wget_file.png" /></kbd><br><br>
{: .challenge}

> ## Activity: Transferring files with SCP
> HTTP tools like `wget` are good for online files, but what about data you have on your machine, or another machine at your institute? This is where tools that use SSH are useful. So, for example, to copy a file from your local machine to your instance using `scp`:
>~~~
>  $ scp -i `name_of_your_key`.pem `local_file_path` `login_name`@###.###.###.###:`instance_file_path`
>~~~
><br>
> This command might be starting to look a little complicated, but you just need to remember that most CLI copying tools, just like ordinary `cp`, require you to provide where something is that needs to be copied (origin), and where it needs to be copied to (destination) in that order.
> 
> Lets try that now, either by creating a text file, or copying a file you already have. For example, from your local terminal:
><br>
><kbd><img src="{{ page.root }}/fig/Data_scp_copy.png" /></kbd><br><br>
> Note: If you leave the instance file path empty, it will copy your file into your ubuntu users home directory.
>
>  So now if we log in to our instance we can check that the transfer worked:
><br>
><kbd><img src="{{ page.root }}/fig/Data_scp_check.png" /></kbd><br><br>
>
> If you want to copy multiple files you simply add them to the command:
>~~~ 
>  $ scp -i `name_of_your_key`.pem `file1_path` `file2_path` `login_name`@###.###.###.###:`instance_file_path`
>~~~
>
> Or if you need to copy an entire directory, you can do so by using the recursive flag (-r):
> ~~~
>  $ scp -r -i `name_of_your_key`.pem `local_directory_path` `login_name`@###.###.###.###:`instance_folder_path` 
> ~~~ 
><br>
> To copy a file from your instance to your local computer, you have to swap the order of the origin and the destination.
> For example, if you want a copy of the data directory you created in the Storage episode, you would use:
><br>
><kbd><img src="{{ page.root }}/fig/Data_scp_recursive.png" /></kbd><br><br>
> **Why is there the permission denied message, and what is the difference between the two scp commands?**
> > ## Solution
> > The permission error occurs because lost+found file is still owned by root, not the ubuntu user. 
> > The -C in the second command stands for enable compression. By using this option transfer speeds can be increased while copying. It automatically enables compression at the origin and decompression at the destination.
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
> We can navigate through our instance's file hierarchy using a number of commands that function similarly to their shell counterparts. 
> <br>
><kbd><img src="{{ page.root }}/fig/Data_sftp_remote.png" /></kbd><br><br>
>
> We can direct commands towards the local file system by preceding them with an “l” for local.
> 
> If we would like to download files from our instance, we can do so by issuing the following command:
>~~~
>  get `instance_file_path` `local_file_path`
>~~~
> <br>
> If you omit the local file name, the command downloads the file to a file with the same name on the local file system.
>  <br>
> 
><kbd><img src="{{ page.root }}/fig/Data_sftp_get.png" /></kbd><br><br>
>
><br>
> When you need to transfer from your local machine to your instance, you use:
>~~~
>  put `local_file_path` `instance_file_path` 
>~~~
> <br>
> <kbd><img src="{{ page.root }}/fig/Data_sftp_put.png" /></kbd><br><br>
> 
>  Just as with `scp` you can copy entire directories using the recursive flag -r. 
> 
{: .challenge}



