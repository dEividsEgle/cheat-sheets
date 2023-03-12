# Working with files and directories

#### Most commonly used directories

| Dir            | Description                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `/`            | 'Root', the top of the file system                                                                                                    |
| `/bin`         | Contains binary files and executable files (sometimes refered to as *ready-to-run* programs).                                         |
| `/etc`         | Contains configuration files, such as, boot, device, networking, and other setup files that control how applications and OS behaves.  |
| `/home`        | 'Home', is where user directories live.                                                                                               |
| `/opt`         | Optional or thirdparty software. Similar to how 'Program Files' work on windows where all the app installed are placed in this folder |
| `/tmp`         | Temporary space. This folder is cleared on reboots                                                                                    |
| `/usr`         | Containes user related programs. Usr will contain it's own directory structure of executables and binary files                        |
| `/var`         | Contains variable data such as log files that change often.                                                                           |
| `/boot`        | Kernel bootloader files. Files required to boot the operating system.                                                                 |
| `/cdrom`       | Monut points for CD-ROM's                                                                                                             |
| `/dev`         | Devices files                                                                                                                         |
| `. (dot)`      | Represents current directory                                                                                                          |
| `.. (dot dot)` | Represents the parent directory. Use `cd` to navigate between directories.                                                            |
| `/etc/passwd`  | Contains the list of all the account on linux system.                                                                                 |
| `/lib`         | Holds library files containing the code that the executables can use.                                                                 |
| `/proc`        | Contains information about currently running processes as well as some kernel parameters.                                             |
| `/run`         | Runtime data specific to the system, including process IDs, socket files, status records, and system logging.                         |
| `/sys`         | Provides device and system interface.                                                                                                 |
| `/sbin`        | System executables.                                                                                                                   |
| `/media`       | Base attachment point for removable media such as flash drives.                                                                                                                                      |

#### Commands used to navigate and manipulate directory

| Command                                                  | Description                                                                                                                                        |
| -------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `pwd`                                                    | Show the current directory.                                                                                                                        |
| `cd`                                                     | Change between directories.                                                                                                                        |
| `$OLDPWD`                                                | Represents the previous directory the user was located in.                                                                                         |
| `mkdir [-p]`                                             | Create a directory `[and specify the parent directory]`.                                                                                           |
| `rmdir [-p]`                                             | Remove a directory (empty directories only).                                                                                                       |
| `rm -rf`                                                 | Recursively remove directory.                                                                                                                      |
| `ls`</br>`ls -a`</br>`ls -l`</br>`ls -al`</br>`ls -latr` | List files within directory.</br>List all files..</br>Long list files.</br>Long list all files.</br>Long list all files sorted by time in reverse. |
| `ls -F`</br>`/`</br>`@`</br>`*`                          | Reveal file types.</br>Directory.</br>Link.</br>Executable.                                                                                        |
| `tree`</br>`tree -d`</br>`tree -c`                       | List the tree view of the directory.</br>List directories only.</br>Colorize output.                                                               |
| `find`                                                   | Supply the path and expression to find a file. `Find` command evaluates files and directories in real time.                                        |
| `file`                                                   | File command tells what kind of file it is that you are looking at.                                                                                |
| `locate`                                                 | Similar to `find` command but queries the index instead.                                                                                                                                                   |

----
# Permission Modes

#### Octal Mode

| r (read) | w (write) |  x (execute)  | Description                     |
|:--------:|:---------:|:---:| ------------------------------- |
|    0     |     0     |  0  | Binary value for off            |
|    1     |     1     |  1  | Binary value for on             |
|    0     |     0     |  0  | Base 10 (decimal) value for off |
|    4     |     2     |  1  | Base 10 (decimal) value for on  |

To get a number to be used with `chmod`, convert the binary into base 10 (decimal). The permission number is determined by adding up the value for each permission type.


#### Numeric Based Permissions

| Binary | Octal | String | Description             |
|:------:|:-----:|:------:| ----------------------- |
|  000   |   0   |  ---   | No Permission           |
|  001   |   1   |  --x   | Execute Only            |
|  010   |   2   |  -w-   | Write Only              |
|  011   |   3   |  -wx   | Write and Execute (2+1) |
|  100   |   4   |  r--   | Read Only               |
|  101   |   5   |  r-x   | Read and Execute (4+1)  |
|  110   |   6   |  rw-   | Read and Write (4+2)    |
|  111   |   7   |  rwx   | Read, Write, and Execute (4+2+1)                        |

#### Permission Categories

| Symbol | Category |
| :------: | :--------: |
| u      | User     |
| g      | Group    |
| o      | Other    |
| a      | All         |

#### Changing permissions

| Command | Description                            |
| ------- | -------------------------------------- |
| `chmod` | Change mode command. (Add permissions) |
| `umask` | Take away permissions.                                       |
| ugoa    | User category user, group, other, all. |
| `+-=`   | Add, subtract, set permissions.        |
| `rwx`   | Read, Write, Execute.                  |
| `chgrp` | Change the group.                      |

#### Most commonly used permissions

| Symbol     | Octal | Description                                    |
| ---------- | ----- | ---------------------------------------------- |
| -rwx------ | 700   | Owner can read and execute.                    |
| -rwxr-xr-x | 755   | Everyone can execute, but only owner can edit. |
| -rw-rw-r-- | 664   | Group can edit and others can read.            |
| -rw-rw---- | 660   | Group can edit and read, not others.           |
| -rw-r--r-- | 644   | Everyone can read, but only the owner can edit.                                               |

#### Permission meaning

| Permission | File Meaning                    | Directory Meaning                                                    |
| ---------- | ------------------------------- | -------------------------------------------------------------------- |
| Read       | Allows a file to be read.       | Allows file names in the directory to be read.                       |
| Write      | Allows a file to be modified.   | Allows entries to be modified within the directory.                  |
| Execute    | Allows the execution of a file. | Allows access to contents and metadata for entries in the directory. |
|            |                                 |                                                                      |

----
# Finding Files

#### Overview
The `find` command can be used to find files by name, size, permissions, owner, modification time, and more. If no arguments are supplied to the find command, it will find all files in the current directory.

#### How to use find command

| Command                          | Description                                                   |
| -------------------------------- | ------------------------------------------------------------- |
| `find <dir> -name <pattern>`     | Display files whos name matches the pattern (case sensitive). |
| `find <dir> -iname <pattern>`    | Display files whos name matches the pattern (ignore case).    |
| `find <dir> -ls`                 | Performs and `ls` on each of the found files or directories.  |
| `find <dir> -mtime <num_days>`   | Finds files that are `num_days` old.                          |
| `find <dir> -size <num>`         | Finds files that are of size 'num'.                           |
| `find <dir> -newer <file>`       | Finds files that are newer than file.                         |
| `find <dir> -exec command {} \;` | Run command against all the files that are found.                                                              |

----
# Handling Files

#### Basic file I/O commands and comparison commands  
| Command                                          | Description                                                                                                                   |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| `* (wildcard)`                                   | Matches zero or more characters.                                                                                              |
| `? (question mark)`                              | Matches exactly one character.                                                                                                |
| `[]`</br>`[a-g]`                                 | Matches a specified character class.</br>User a *hyphen* to match all files with the specified letters from the range.        |
| `>`                                              | Redirect standard output to a file. File must be empty, else it will be overwriten.                                           |
| `> <file> 2< <standard_error>`                   | Send standard output to the file and redirect standard error to a different file.                                                                                                                              |
| `>>`                                             | Redirect satandard output to a file, but append any existing content in a file.                                               |
| `<`                                              | Redirect input from a file to a command.                                                                                      |
| `diff <filename-1> <filename-2>`                 | View differences between two files.                                                                                           |
| `sdiff <filename-1> <filename2`                  | View differences between two files by placing them side-by-side.                                                              |
| `vimdiff`                                        | View differences between two files using vim.                                                                                 |
| `grep`</br>`grep -i`</br>`grep -c`</br>`grep -n` | Display lines matching a pattern.</br>Ignore case.</br>Count the number of occurrences.</br>Precede output with line numbers. |
| `tr`                                             | Translate a character to a new character.                                                                                     |

# Searching in Files

Use the `grep` command to search for text in files.

#### How to use the `grep` command

| Command                    | Use                                                                 |
| -------------------------- | ------------------------------------------------------------------- |
| `grep <pattern> <file>`    | Search for pattern in file.                                         |
| `grep -v <pattern> <file>` | Invert match. Return lines from file that do not match the pattern. |
| `grep -i`                  | Perform a search ignoring the case.                                 |
| `grep -c`                  | Count the number of occurences in the file.                         |
| `grep -n`                  | Precede output with the line number from the file.                                                                    |

#### How to use the `strings` command to search within binary file.

The `grep` command cannot be used to search a binery file. To search the binary you must use the `strings` command followed by the *file* that you want to searche.

- Display printable strings in the file.
```
strings <file>
```

----
# Copying Files

#### Copy files across the network with tfpt

- SFTP is a secure SSH file transfer protocol that provides file access, transfer, and management. SFTP uses port 22 and if you have a SSH key authentication configured it will also work with SFTP.

| Command                                             | Description                                |
| --------------------------------------------------- | ------------------------------------------ |
| `sftp <servername>`</br>`sftp <username@ipaddress>` | Use sftp to connect to the remote server.  |
| `pwd`                                               | Show remote working directory.             |
| `lpwd`                                              | Show local working directory.              |
| `lls`                                               | Show files on the local machine.           |
| `put`                                               | Copy from local machine to remote machine. |
|                                                     |                                            |

#### Copy files across the network with scp

- SCP is a secure copy protocol that works similar to SFTP.

| Command                                            | Description                                                             |
| -------------------------------------------------- | ----------------------------------------------------------------------- |
| `scp <filename> <username@ipaddress:<destination>` | Copy file using SCP on to the specified server into the specified path. |
