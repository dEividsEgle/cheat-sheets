# Linux Manual

#### Overview
The `man` command can be helpful to find documentation online about a specific command and it's use.

- Get help about a specific command
```
man <command>
```

- Search for a manual page by a keyword.
```
man -k <keyword>
```

#### Online manual sections

Manual pages are referenced by numbered sections.

| Section | Description                                                |
|:-------:| ---------------------------------------------------------- |
|    1    | User commands.                                             |
|    2    | Kernel system calls.                                       |
|    3    | Higher-level Unix programming library documentation.       |
|    4    | Device interface and driver information.                   |
|    5    | File description (system configuration files).             |
|    6    | Games                                                      |
|    7    | File formats, conventions, and encodings (ASCII, suffixes). |
|    8    | System commands and server.                                |

# Help Command

#### Overview
The `--help`  or `-h` can be appended at the end of the command to find help on a specific command.

- Learn more about a command
```
ls --help
```

# Info Manual

#### Overview
There is another documentation in a different format called *info* or *infotext*. This often goes further than typical manual page does, but can also be more complex.

- Access the info manual
```
info <command>
```

# Other Documentations

#### Overview
Some packages do not provide online help, therefore, they can somtimes dump their documnetation into `/usr/share/doc` directory. Browse to the directory to see if any additional documentation has been provided.

