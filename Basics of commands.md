<h1>$${\color{red}Basics}\space {\color{red}of} \space {\color{red}commands}$$</h1>

 #### We all know that a large selling point of using OSs such as Ubuntu is how lightweight they can be. This, of course, doesn't come without its disadvantages, where for example, often there is no GUI (Graphical User Interface) or what is also known as a desktop environment that we can use to interact with the machine (unless it has been installed). A large part of interacting with these systems is using the "Terminal".

> The "Terminal" is purely text-based and is intimidating at first. However, if we break down some of the commands, after some time, you quickly become familiar with using the terminal!

<br>

| Command | Description | 
| --- | --- |
| ***echo*** | Output any text that we provide | 
| ***whoami*** | Find out what user we're currently logged in as! |
| ***ls*** | listing |
| ***cd*** | change directory | 
| ***cat*** | concatenate | 
| ***pwd*** | print working directory |
| ***find*** |  to find out where is files |
| ***grep*** | to search the contents of files for specific values that we are looking for |
| ***wc*** | command line utility for printing newline, word and byte counts for files |
| ***man*** | for inforamion of command |
| ***--help*** | for inforamion of command |


> Pro tip: You can list the contents of a directory without having to navigate to it by using ls and the name of the directory. I.e. ```ls /root/Desktop```

> Pro tip: You can use cat to output the contents of a file within directories without having to navigate to it by using cat and the name of the directory. I.e. ```cat /home/ubuntu/Documents/todo.txt```

<br>
<br>

Although it doesn't seem like it so far, one of the redeeming features of Linux is truly how efficient you can be with it. With that said, you can only be as efficient as you are familiar with it of course. As you interact with OSs such as Ubuntu over time, essential commands like those we've already covered will start to become muscle-memory.

One fantastic way to show just how efficient you can be with systems like this is using a set of commands to quickly search for files across the entire system that our user has access to. No need to consistently use ```cd``` and ```ls``` to find out what is where. Instead, we can use commands such as ```find``` to automate things like this for us!

This is where Linux starts to become a bit more intimidating to approach -- but we'll break this down and ease you into it.

## Using Find

The find command is fantastic in the sense that it can be used both very simply or rather complex depending upon what it is you want to do exactly. However, let's stick to the fundamentals first.

Now, of course, directories can contain even more directories within themselves. It becomes a headache when we're having to look through every single one just to try and look for specific files. We can use ```find``` to do just this for us!

Let's start simple and assume that we already know the name of the file we're looking for — but can't remember where it is exactly! In this case, we're looking for "passwords.txt"

If we remember the filename, we can simply use ```find -name passwords.txt``` where the command will look through every folder in our current directory for that specific file.

we want to search for every file that has an extension such as ".txt". Find let's us do that too!
 In our case, we want to find every .txt file that's in our current directory. We will construct a command such as ```find -name *.txt``` . Where "Find" has been able to find every .txt file and has then given us the location of each one


 *****************

 ## Using Grep

Another great utility that is a great one to learn about is the use of ```grep```. The ```grep``` command allows us to search the contents of files for specific values that we are looking for.

Take for example, the access log of a web server. In this case, the access.log of a web server has 244 entries.
Using a command like ```cat``` isn't going to cut it too well here. Let's say for example if we wanted to search this log file to see the things that a certain user/IP address visited? Looking through 244 entries isn't all that efficient considering we want to find a specific value.

We can use ```grep``` to search the entire contents of this file for any entries of the value that we are searching for. Going with the example of a web server's access log, we want to see everything that the IP address "81.143.211.90" has visited (note that this is fictional)

```grep "81.143.211.90" access.log```
"Grep" has searched through this file and has shown us any entries of what we've provided and that is contained within this log file for the IP.

****************
## Introduction to Flags and Switches 

* Commands that accept these will also have a ```--help``` option. This option will list the possible options that the command accepts, provide a brief description and example of how to use it.

```ls --help```

> This option is, in fact, a formatted output of what is called the man page (short for manual), which contains documentation for Linux commands and applications.

* The Man(ual) Page

The manual pages are a great source of information for both system commands and applications available on both a Linux machine, which is accessible on the machine itself and online.

To access this documentation, we can use the ```man``` command and then provide the command we want to read the documentation for. Using our ls example, we would use ```man ls``` to view the manual pages for ```ls``` .

************

##### Now, we're going to learn some more commands for interacting with the filesystem to allow us to:

  * create files and folders
  * move files and folders
  * delete files and folders

More specifically, the following commands:

| Command | Full Name | Purpose | 
| --- | --- | --- |
| ***touch*** | touch | Create file |
| ***mkdir*** | make directory | Create a folder |
| ***cp*** | copy | Copy a file or folder |
| ***mv*** | move | Move a file or folder |
| ***rm*** | remove | Remove a file or folder |
| ***file*** | file | Determine the type of a file |
| ***vim*** | vim | To create or edit a file |
| ***nano*** | nano | To create or edit a file |
| ***su*** | super user | change between users |



> Protip: Similarly to using cat, we can provide full file paths, i.e. directory1/directory2/note for all of these commands


************

## Common Directories 

#### /etc

This root directory is one of the most important root directories on your system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system. 

For example, the sudoers file highlighted in the screenshot below contains a list of the users & groups that have permission to run sudo or a set of commands as the root user.

Also highlighted below are the "passwd" and "shadow" files. These two files are special for Linux as they show how your system stores the passwords for each user in encrypted formatting called sha512.

#### /var

The "/var" directory, with "var" being short for variable data,  is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (/var/log), or other data that is not necessarily associated with a specific user (i.e., databases and the like).


#### /root

Unlike the /home directory, the /root folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as "/home/root" by default.  



#### /tmp

This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.

What's useful for us in pentesting is that any user can write to this folder by default. Meaning once we have access to a machine, it serves as a good place to store things like our enumeration scripts.

**********




<br>

******
if this content liked you, follow me [Here](https://github.com/4bo4yman) ;) :tada:
*****








