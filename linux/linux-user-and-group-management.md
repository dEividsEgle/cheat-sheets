# User Management

#### Overview
All user accounts are store in the `/etc/passwd` location. The default account in the `etc/passwd` folder is the **root** account. The *passwd* file contains different fields of information each seperated by a colon. All user password are stored in the `/etc/shadow` file. Similar to the `/etc/passwd` file, the `/etc/shadow` file also contains series of fields that are seperated by colon.

Reading the files or creating new user accounts require the root access or using the `sudo` command.

#### /etc/passwd
The `/etc/passwd` file fields.
**username:password:UID:GID:comments:home_dir:shell**
- Username.
	- A string used to identify an account and must be supplied during login.
- Password
	- Password are stored in the `/etc/shadow` file which can only be read by a superuser.
- User ID (UID)
	- Each account has a unique User ID. System account UID's are < 1000 and the root account UID is always 0.
- Group ID (GID)
	- User accounts default group. Any new files that are created by the user will belong to the user's default group. You must change the group prior to creating a new file if you wish that file to belong to the desired group.
- Comments (GECOS)
	- Comments field typicaly containes information regarding the use of the account. Alternatively, this can containes user full name.
- User home directory.
	- When users signs-in, by default, they are placed in their home directory. If the home directory is does not exist, they will be placed in the root directory. 
- Shell
	- Shell is executed whenever the user successfully manages to sign-in. The list of available shells are in the `/etc/shells/` file. You can specify `/usr/sbin/nologin` or `/bin/false` as the shell to prevent interactive use for an account. This can often be set to system accounts designed to run specific processes.

#### /etc/shadow
The `/etc/shadow/` file fields.
**`[username]:[password]:[date of last password change]:[minimum password age]:[maximum password age]:[warning period]:[inactivity period]:[expiration date]:[unused]`**
- Username
	- String identifying the account that exisits on the system.
- Password
	- Password encrypted by a cryptographic hash algorithm.
- Last password change.
	- Date since the password has last been changed. Days are counted since 1st of January 1970.
- Minimum password age.
	- Number of days after the user password must be changed. By default, the user password does not have to be changed and is indicated by 99999.
- Warning period.
	- Warning prior to password expiery day.
- Inactivity period
	- Number of days after the user password expires.
- Expiration date
	- Date of when the account had been disabled.
- Unused
	- The last field is reserved for future use. 

#### User Management Commands

- Create a new user
```bash
useradd -c "Soren Kierkegaard" -m -s /bin/bash soren
```
- Add user password
```bash
passwd deivids
```
- View the last user account created
```bash
tail -1 /etc/passwd
```
* Add service account with no login
```bash
useradd -c "Nginx Service Account" -d /opt/nginx -r -s /usr/sbin/nologin nginx
```
- Delete user including it's home directory.
```bash
userdel -r soren
```

#### Update user account with `usermod` command.
| Command                                 | Description                     |
| --------------------------------------- | ------------------------------- |
| `usermod -c <"comment"> <username>`     | Add a comment to user account.  |
| `usermod -g <group> <username> `        | Specify user default group.     |
| `usermod -G <group1,group2> <username>` | Add user to groups.             |
| `usermod -s <path> <username>`          | Specify the default user shell. |
|                                         |                                 |

----
# Group Management

Groups are stored in the `/etc/group` file. The first entry in the group file is the root group. Similar to the user and password file, the group file also containes series of fields seperated by a colon.

#### /etc/group
The `/etc/group` fields.
**group_name:password:GID:account1,account2**
- Group name
	- The display name of the group.
- Password
	- Sometimes used for priviledged groups. When there is an `X` in this field, it means that shadow group password are being used, which information is stored in the `/etc/gshadow` file.
- Group ID
	- Unique ID number to represent the group.
- Account names field.
	- Members of the group separated by a comma. 

#### Group management commands
| Command                    | Description                                                |
| -------------------------- | ---------------------------------------------------------- |
| `groups`                   | Display list of groups that the current user is part of.   |
| `groups <username>`        | Display list of groups that the specified user is part of. |
| `grouadd [] <group_name>`  | Create a new group.                                        |
| `groupdel <group_name>`    | Delete an existing group.                                  |
| `groupmod [] <group_name>` | Change the properties of existing group.                                                           |

----
# Elevating permissions and switching Users

| Command                      | Description                                                                                                                                                |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `su <username>`              | Change user ID or become a super user. Current user environment will be maintained.                                                                        |
| `su - <username>`            | Provide the user environemnt similar as if you would sign in with the user.                                                                                |
| `su -c <command>`            | Specify a command to be executed.                                                                                                                          |
| `whoami`                     | Return the current user account name.                                                                                                                      |
| `sudo`</br>`sudo <username>` | Execute commands with the security priviledges of another users. By default, the root users will be used, otherwise, a different user has to be specified. |
| `sudo su`                    | Switch to superuser account.                                                                                                                               |
| `sudo su -`                  | Switch to superuser account with the root's environment.                                                                                                   |
| `sudo su - <username>`       | Switch to username account.                                                                                                                                |
| `visudo`                     | Change and edit the sudo configuration file stored in `/etc/sudoers`. The command must be executed as the root user.                                                                                                                                                            |

## Running commands as the superuser

#### /etc/sudoers
The priviledge users must be configured in the `/etc/sudoers` file to enable the to run priviledged commands. You must use the `visudo` command to edit the sudoers file. This will also check for file syntax errors after the file is saved.

#### sudo logs

- Find and view the `sudo` logs.
```bash
journalctl SYSLOG_IDENTIFIER=sudo
```

