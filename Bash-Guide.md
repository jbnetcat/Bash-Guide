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
<pre>$ man commandName</pre>Man displays the manual page entry for a given command.<br>

**2. info, -h, and --help** <br>
The info command shows helpful information about most Bash commmands. For a shorter version of the available help pages, try the command name followed by either *-h or --help.*
<pre>$ info commandName</pre>

<pre>$ bash --help </pre> 
Both *info and --help* show useful command options and syntax.

**3. sudo** <br>
Some commands need to be executed with SuperUser or root authority. If you are not logged in as root user on a Unix/Linux/Apple OSX/etc. machine, use *sudo* followed by the command you want to be executed as root user.
<pre>$ sudo ifconfig</pre> 

SuperUser do this commandName
<pre>$ sudo su</pre> Sudo, escalate my privledges to SuperUser 
### Local Discovery
**A. whoami**<br>
One of the first things to do is to find out who you are, what permissions you have and what is your current working directory.  Am I logged in as root or just another user?</pre>
<pre>$ whoami</pre>
 
**B. pwd**<br>
Print Working Directory is a simple command that prints your current working directory.
<pre>$ pwd 
$ /home/user/Desktop/Apps</pre>

**C. ls**<br>
The LS command is widely used and lists information about files and directories. Defaults to the current directory.
<pre>$ ls -lia /home/user</pre> 
List -a: all, including hidden files/dirs in -l: long list format, -i: include inode index

**D. locate**<br>
If you are trying to locate a particular file this command works well. It is sometimes necessary to run the *updatedb* command first before using *locate* because updatedb refreshes your machine's file database index.
<pre>$ updatedb</pre>

<pre>$ locate foo.bar
$ /home/user/Documents/foo.bar</pre>

**E. file**<br>
In **.nix** environments, file extensions don't tell us much about what kind of file we're dealing with. For instance you could name a file: myfile.mine and make it executable by setting the file's executable bit: *Chmod u+x fileName.* However, you can use *file* followed by the file name to discover the file's type.
<pre>$ file foo.bar
$ ASCII text</pre>

### Files and Directories
**1. cd**<br>
Change directories, from the current working directory to a /new/location.
<pre>$ cd ../home/user</pre>Changes directory to the (..) parent directory of /home/user

**2. mkdir**<br>
Make a new directory.
<pre>$ mkdir /var/www/html/NewWebsite</pre>

**3. rmdir**<br>
Remove a directory. Note: a directory must be empty before deleting it, unless you use additional parameters with *rmdir* to delete a dir and its subdirectories forcefully.
<pre>$ rmdir /var/www/html/OldWebsite</pre>

**4. rm**<br>
Remove or delete files and directories. Options include: -f: force, don't prompt me. -r: recursive, delete directories and their contents recursively. 
<pre>$ rm -rf Deleteme/</pre>

**5. shred**<br>
Note that if you use rm to remove a file, it might be possible to recover some of its contents, given sufficient expertise and/or time. For greater assurance that the contents are truly unrecoverable, consider using shred. Options include: -u: truncate and remove file after overwriting. -v: verbose, show progress. -z: add a final overwrite with zeros to hide shredding
<pre>$ shred -vzu /home/myTop/Secret/File.txt</pre>

**6. mv**<br>
Move a file from location A to location B and/or rename it.
<pre>$ mv /home/user/mydoc.php /home/user/Anotherdoc.php</pre>

**7. cp**<br>
Copy a file to a new location, but the old file remains by default.
<pre>$ cp myfile_Name.docx /home/usr/path/NewName.docx</pre>

**8. touch**<br>
Create an empty file, or change/modify the file's timestamp/Date accessed/Date modified.
<pre>$ touch file_1.sh</pre>

**9. nano**<br>
Edit an existing file or create a new one with nano, one of the many command line text editors. Nano also performs syntax highlighting when you name a file with a relevant extension. For example: *nano file.php* will create/edit this fileName, and display highlighing for the PHP syntax.
<pre>$ nano /path/to/file/Index.html</pre>
### Common commands and Utilities
**a. echo**<br>
fasdfasdfasdf
<pre></pre>
**b. md5sum**<br>
fasdfasdfasdf
<pre></pre>
**c. sha1sum**<br>
fasdfasdfasdf
<pre></pre>
**d. cat**<br>
fasdfasdfasdf
<pre></pre>
**e. grep**<br>
fasdfasdfasdf
<pre> </pre>
