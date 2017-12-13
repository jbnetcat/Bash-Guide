## Introduction
The acronym **BASH** stands for: *Bourne Again Shell,* which is a *command interpreter* based on its predecessor, the *Bourne* shell.  This environment allows you to interact with your OS via commands, and normally runs inside your terminal, but you can also run a Bash/Shell script as a standalone executable. This guide covers some very useful Bash commands for WhiteHatters. 

Many Bash commands are intuitive, for example you could fire up a terminal and ask:
	<pre>$ whatis bash <br>bash (1)    - GNU Bourne-Again SHell</pre>
To locate source files, man pages and executables:

<pre>$ whereis bash
bash: /bin/bash /etc/bash.bashrc /usr/share/man/man1/bash.1.gz</pre>



### Helpful Commands
**1. man** 
It is very important to learn how to find help when using terminal commands. Most **.nix**  systems include built-in manual pages to get information about almost any command such as: proper syntax, options, attributes, and even examples of correctly formatted commands.
<pre>$ man commandName			        # shows the manual page entry for a given command</pre>

**2. info, -h, and --help** 
The info command shows helpful information about most Bash commmands. For a shorter version of the available help pages, try the command name followed by either *-h or --help.*
<pre>$ info commandName			        # Provides helpful information about the command
$ bash --help				        # GNU bash, version 4.3.48(1)-release-(x86_64-pc-linux-gnu)</pre>
**3. sudo** 
Some commands need to be executed with SuperUser or root authority. If you are not logged in as root user on a Unix/Linux/Apple OSX/etc. machine, use *sudo* followed by the command you want to be executed as root user.
<pre>$ sudo ifconfig                     # SuperUser do this commandName
$ sudo su				            # Sudo, escalate my privledges to SuperUser </pre>

### Local Discovery
**A. whoami**
One of the first things to do is to find out who you are, what permissions you have and what is your current working directory.
<pre>$ whoami				   		    # Am I logged in as root or just another user?</pre>
 
**B. pwd**
Print Working Directory is a simple command that prints your current working directory.
<pre>$ pwd				                # /home/user/Desktop/Apps</pre>

**C. ls**
The LS command is widely used and lists information about files and directories. Defaults to the current directory
<pre>$ ls -lia /home/user	 	        # Display -a: all, including hidden files/dirs in -l: long list format, -i: include inode index</pre>

**C. locate**
If you are trying to locate a particular file this command works well. It is sometimes necessary to run the *updatedb* command first before using *locate* because updatedb refreshes your machine's file database index.
<pre>$ updatedb					          # Refresh the built-in file database 
$ locate foo.bar					 # /home/user/Documents/foo.bar</pre>
