## Introduction
The acronym **BASH** stands for: *Bourne Again Shell,* which is a *command interpreter* based on its predecessor, the *Bourne* shell.  This environment allows you to interact with your OS via commands, and normally runs inside your terminal, but you can also run a Bash/Shell script as a standalone executable. This guide covers some very useful Bash commands for WhiteHatters. 

Some commands are intuitive, for example you could fire up a terminal and ask:
	<pre>$ whatis bash <br>bash (1)    - GNU Bourne-Again SHell</pre>
Or, to locate source files, man pages and executables:

<pre>$ whereis bash
bash: /bin/bash /etc/bash.bashrc /usr/share/man/man1/bash.1.gz</pre>



###Helpful Commands
**1. man** 
Always use the built-in manual pages to get information about almost any command such as: proper syntax, options and even examples of correctly formatted commands.
<pre>$ man commandName</pre>