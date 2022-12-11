# Linux Cheat Sheet #

Linux cheat sheet that I have put toget from the time that I was familiarising myself with the os. This has helped me a lot along side the built in help tool and the manual pages.

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
  
### Text Manipulation ###
| Command | Description |
| --- | --- |
| `head` | Display the first 10 (default) lines in the text |
| `tail` | Display the last 10 line in the text |
| `head -nl` | Display numbered lines (nl) in the text |
| `sed` | Find and replace text |
| `sed s/mysql/MySQL/g(or #) snort.conf > snort2.conf` | Substitute mysql with MySQL globally (on specific occurrence) |
| `more` | Scroll through text |
| `less` | Show less text and use / to search for terms in the text |
| `grep` | --- |

### Networkig ###
| Command | Description |
| ------------- | ----------- |
| `ifconfig` | Display physical int ip configuration |
| `iwconfig` | Display wireless int ip configuration |
| `ifconfig eth <IP> netmask <subnet> broadcast <gateway>` | Change the interface ip configuration |
| `dhclient eht0` | Reassigned IP via DHCP protocol on eth0 interface |
| `dig <address> ns/nx` | Find specific domain name servers/mail servers |
| `vm /etc/hosts` | Change local DNS entry |
| `vm /etc/resolv.conf` | Change DNS server |

### Adding and Removing Software ###
| Command |	Description |
| --- | --- |
| `apt-cache search <package>` |	Search for software in the repository (local) |
| `apt-get install <package>`	| Install software stored in the local repository |
| `apt-get remove <package>`	| Remove installed software |
| `apt-get purge <package>`	| Remove installed software and the configuration files |
| `apt autoremove <package>`	| Remove all the dependencies |
| `apt-get update`	| Check and download available updates |
| `apt-get upgrade`	| Install the downloaded updates |
| `vm /etc/apt/sources.list` |	Add repositories to query for software |
| `apt-get synaptic` | Run synaptic from shell (GUI based installer) |

### File and Directory Permissions ###
| Command | Description |
| --- | --- |
| `chown <user><dir/file>` | Change user ownership on a specific file |
| `chgrp <group><dir>` | Change group ownership on a specific file |
| `ls -l </dir/file>` | Check current effective permissions |

<p align="center">
Octal and Binary Representations of Permissions 
</p>

<p align="center"></p>
<table>
    <thead>
        <tr>
            <th align="left">Column1</th>
            <th align="center">Column1</th>
            <th align="right">Column1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="left">Column1</td>
            <td align="center">Column1</td>
            <td align="right">Column1</td>
        </tr>
    </tbody>
</table>
<p></p>
