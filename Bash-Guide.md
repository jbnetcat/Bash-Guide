### Introduction
The acronym **BASH** stands for: *Bourne Again Shell,* which is a *command interpreter* based on its predecessor, the *Bourne* shell.  This environment allows you to interact with your OS via commands, and normally runs inside your terminal, but you can also run a Bash/Shell script as a standalone executable. This guide covers some very useful Bash commands for WhiteHatters. 

Many Bash commands are intuitive, for example you could fire up a terminal and ask:
	<pre>$ whatis bash <br>bash (1)    - GNU Bourne-Again SHell</pre>
To locate source files, man pages and executables:

<pre>$ whereis bash
bash: /bin/bash /etc/bash.bashrc /usr/share/man/man1/bash.1.gz</pre>



### Helpful Commands
**1. man** <br>
It is very important to learn how to find help when using terminal commands. Most **.nix**  systems include built-in manual pages to get information about almost any command such as: proper syntax, options, attributes, and even examples of correctly formatted commands.
<pre>$ man commandName</pre>Shows the manual page entry for a given command

**2. info, -h, and --help** <br>
The info command shows helpful information about most Bash commmands. For a shorter version of the available help pages, try the command name followed by either *-h or --help.*
<pre>$ info commandName</pre>  Provides helpful information about the command

<pre> $ bash --help </pre> Show useful options and syntax

**3. sudo** <br>
Some commands need to be executed with SuperUser or root authority. If you are not logged in as root user on a Unix/Linux/Apple OSX/etc. machine, use *sudo* followed by the command you want to be executed as root user.
<pre>$ sudo ifconfig</pre> 

SuperUser do this commandName
<pre>$ sudo su</pre> Sudo, escalate my privledges to SuperUser 

### Local Discovery
**A. whoami**<br>
One of the first things to do is to find out who you are, what permissions you have and what is your current working directory.
<pre>$ whoami</pre>	 Am I logged in as root or just another user?</pre>
 
**B. pwd**<br>
Print Working Directory is a simple command that prints your current working directory.
<pre>$ pwd 
$ /home/user/Desktop/Apps</pre>

**C. ls**<br>
The LS command is widely used and lists information about files and directories. Defaults to the current directory
<pre>$ ls -lia /home/user</pre>                       Display -a: all, including hidden files/dirs in -l: long list format, -i: include inode index</pre>

**D. locate**
If you are trying to locate a particular file this command works well. It is sometimes necessary to run the *updatedb* command first before using *locate* because updatedb refreshes your machine's file database index.
<pre>$ updatedb</pre>Refresh the built-in file database
 
<pre>$ locate foo.bar</pre> $ /home/user/Documents/foo.bar

**E. file**
In computer security it is necessary to know what kind of file you're dealing with. Use *file* followed by the file name to find out its file type.
<pre>$ file foo.bar</pre> 

$ ASCII text

### Files and Directories
**1. cd**
Change from the current working directory to a /new/location.
<pre>$ cd ../home/user</pre>Change directory to the (..) parent directory of /home/user

**2. mkdir**

**3. rmdir**

**4. rm**

**5. mv**

**6. cp**

**7. touch**

### Common commands and Utilities