# Bash profile setup

## Customizing the shell

**Overview**
To save the customised shell to be persistent across logins, you must save it to the .bash_profile. Otherwise, each time you connect to will have to re-enter the command to create the shell that you want.

The *.bash_profile* config file is stored in the user home directory.

- Create custom shell
```bash
echo 'export PS1="\t [\u@\h \w]\n $ ]"' >> ~/.bash_profile
```

#### Formating strings

| String | Description                                    |
| ------ | ---------------------------------------------- |
| `\d`   | Date in "Weekday Month Date e.g.(Mon June 20)" |
| `\h`   | Hostname up to the first '. (dot)'.            |
| `\H`   | Hostname.                                      |
| `\n`   | Newline.                                       |
| `\t`   | Current time in 24H format (hh:mm:ss).         |
| `\@`   | Current time in 12H AM/PM format.              |
| `\A`   | Curernt time in 24-hour (HH:MM) format.                                               |
| `\u`   | User name of the current host.                 |
| `\w`   | Current working directory.                     |
| `\W`   | Base name of the current working directory.    |
| `\$`   | If UID is 0, a #, otherwise $.                 |
|        |                                                |

## Creating aliases

**Overview**
Aliases can be used to create shortcuts for the most common commands that are being used. Many linux distributions come with predefined aliases, but each of these can be customised to the user preference. Aliases can also be used to correct the most common typing errors.

Similar to how the shell is customised, the aliases have to be added to the dotfile to make them persistent across logins.

View all the defined aliases by using the `alias` command.

- Remove the alias
```bash
unalias <name-of-the-alias>
```
- Remove all aliases
```bash
unalias -a
```
- Create an alias
```bash
alias ll='ls -l'
alias cls='clear'
```

## Set time zone

- Set time zone to # Greenwich mean time
```bash
export TZ='GMT' >> ~/.bash_profile
```

## Configure shell history

**Overview**
Each command entered into the shell is added to the history enabling user to recall and display entered commands. Shell history is stored on both memory and disk. The history file is stored in user home folder. 

- The most common history files:
	- ~/,bash_history
	- ~/.history
	- ~/.histfile

The `HISTSIZE` environmental variable sets the history of how many command will be remembered. By default bash retains 1000 commands in the history file.

- Configure 500 commands to be retained in history.
```bash
export HISTSIZE=500
```

#### History command ####
| Command          | Description                                                                                                    |
| ---------------- | -------------------------------------------------------------------------------------------------------------- |
| `history`        | Display the shell history.                                                                                     |
| `!! (bang bang)` | Repeate the previous command line.                                                                             |
| `!N`             | Repeat the command in line number N.                                                                           |
| `!<character>`   | Repeat the most recent command starting with specified character or name.                                      |
| `!:N`            | Pull out a word from the previous command by referencing the word with number `N`. The word count starts at 0. |
| `!^`             | Represents the first argument of the previous command. This command is equal to `!:1`.                         |
| `!$`             | Represent the last argument of the previous command.                                                           |
| `Ctrl+R`         | Reverse shell history search. Use `Ctrl+G` to cancel the search.                                               |
|                  |                                                                                                                |

## Tab completion

**Overview**
The tab completion should be enabled by default. Tab completion can help to complete command names, environmental variables, file names and directory names. Hitting the `Tab` twice will reveal a list of available command to use. Once there are only one option left, hitting the `Tab` key will complete the command.