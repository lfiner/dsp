# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

Show working directory: `pwd`

Create a directory: `mkdir`

Delete a directory: `rmdir`

Create a file: `touch newfile`

Delete a file: `rm`

Rename a file: `mv oldfilename newfilename`

List hidden files: `ls -a`

Copy a file from one directory to another: `cp path/file newpath/`

Move up one directory level: `cd ..`

Show a manual page: `man command`


---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

`ls`: list files in the current directory

`ls -a`: include hidden files

`ls -l`: show files in long format

`ls -lh`: show files in long format and with unit suffixes

`ls -lah`: all of the above

`ls -t`: sort in reverse chronological order

`ls -Glp`: enable color, show in long format, and show a slash after directory names


---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -d`: list only directories

`ls -m`: show the names as a comma-separated list

`ls -r`: list files in reverse order

`ls -x`: list files as rows

`ls -1`: list each entry on a line

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` takes standard input, such as a string or series of words or numbers, and feeds it to a command as arguments to that command.

Example:

`pwd  | xargs echo "Working directory is"`

yields

`Working directory is /Users/Myname`

 

