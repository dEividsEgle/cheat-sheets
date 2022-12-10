# Linux Cheat Sheet #

Some quick reference for most common tools used at for work on daily basis.

* Extensions
  * Each .cpl extension is a representation of a tool within control panel. 
  * Each .msc extension is a representation of MS Windwos management console (snap-in).

## Linux Basics ##

### Filesystem ###
![image](https://user-images.githubusercontent.com/107066953/206867053-6967e18b-ddbd-4fd9-9d67-86bbc4a18c88.png)

### Basic Linux commands ###
| Command | Description |
| --- | --- |
| `pwd` | Show the current working directory |
| `whoami` | Show the current user |
| `ls` | List the contents of directory |
| `ls -l` | Long list the contents of directory |
| `ls -la` | Long list the contents of directory including hidden files |
| `<command> --help (-h)` | Get help for a specific command |
| `man <command>` | View manual for a specific command |
| `locate <keyword>` | Go through the file system to locate the specific keywoard |
| `whereis` | Find binaries (binary files) |
| `which` | Return location of the binary in the PATH variable |
| `find <dir> -type <type(dir or file)> -name <name-to-be-found>` | Specify the directory and start a search to find the matching query |
| `ps aux` | List all running processes |
| `ps` | List currently running processes (user) |
| `cat` | Display contents of the file or use redirect to create a file |
| `touch` | Create a file |
| `mkdir` | Create a directory |
| `cp <source file> </dir/new-file>` | Copy a file |
| `mv` | Move a file (also used to rename a file) |
| `rm` | Remove a file |
| `rmdir` | Remove a directory |

## Text Manipulation ##

| Command | Description |
| --- | --- |
| `head` | Display the first 10 (default) lines in the text |
| `tail` | Display the last 10 line in the text |
