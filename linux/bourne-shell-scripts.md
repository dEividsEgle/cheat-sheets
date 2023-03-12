# Basics

Bourne shell scripts generally start with the `#!/bin/sh`, which indicated that the `/bin/sh` program should execute the commands included in the script. The `#!` is referd to as *shebang*. 

----
# Literals

Quotes can be userd to create *literals*; a string that the shell should not analyze before passing it to the command line.

#### Single quotes

The easiest way to create a literal is to enclose the entrire string in single quotes 
`( '<string' )`.  Now the shell will view this as a single parameter.

#### Double quotes

Double quotes work similar to single quotes, except that the shell expand any variables that appear within double quotes. 

----
# Shell Script Utilities

#### basename

The `basename` command can strip the extension from filename or get rid of the directories in a full pathname.

- The following will only return *example*.
```bash
basename example.html .html
basename /usr/dev/bin/example
```

#### awk

Awk can pick a single field out of input stream.

- List the owner of the file from the `ls -l` output.
```bash
ls -l | awk '{print $4}'
```

#### sed (stream editor)

The `sed` program is an automatic text editor that takes an input stream, alerts it according to some expression, and prints the results to standard output.