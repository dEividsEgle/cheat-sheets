# Editing files with `Vim`

#### Overview

`Vim` is comaptible with commands found in `vi`. These tools are always available on the system and provide the abilty to edit files. `Vim` also provides the option to edit the files over the network and it includes syntax highlighting.

Most of the key mappings from `vi` can be carried over to commands like `man,` `more`, `less`, and `view`.

#### How to open `vi` and `vim`

On many distros when you invoke `vi`, it is actually running `vim`.

| Command       | Description                         |
| ------------- | ----------------------------------- |
| `vi <file>`   | Edit specified file.                |
| `vim <file>`  | Same as `vi` but has more features. |
| `view <file>` | Start `vim` in read-only mode.                                    |

# `vi` modes

#### Overview
When `vi` starts, by default, you are placed into the command mode. Letters typed into command mode are not sent to the file but are rather interpreted as commands. 

## Command Mode

Command mode allows to:
- Navigate throught the file
- Perform searches
- Delete text
- Copy text
- Paste text

#### Command mode key bindings

| Command | Use                              |
| :-------: | -------------------------------- |
| `k`     | Up one line.                     |
| `j`     | Down one line.                   |
| `h`     | Left one character.              |
| `l`     | Right one character.             |
| `w`     | Right one word.                  |
| `b`     | Left one word.                   |
| `^`     | Go to the beginning of the line. |
| `$`     | Go to end of the line.                                 |

## Insert Mode

| Command | Use                                  |
|:-------:| ------------------------------------ |
|   `i`   | Insert at the cursor position.       |
|   `I`   | Insert at the beginning of the line. |
|   `a`   | Append after the cursor position.    |
|   `A`   | Append at the end of the line.       |
|  `esc`  | Return to command mode.                                     |

## Line Mode

Line mode can only be entered from command mode. To enter the line mode type the colon (`:`) character.

|        Command        | Use                                                                                                  |
|:---------------------:| ---------------------------------------------------------------------------------------------------- |
|         `:w`          | Writes (saves) the file.                                                                             |
|         `w!`          | Force save the file even if the write permission is not set. (Only works if the user owns the file.) |
|         `:q`          | Quit. Only works when there are no changes made to the file.                                         |
|         `:q!`         | Quit without saving.                                                                                 |
|        `:wq!`         | Write (save) and quit.                                                                               |
|         `:x`          | Same as `wq`.                                                                                        |
|         `:n`          | Position the cursor at the line `n`. `:5` will place the cursor at the fifth line in the file.       |
|         `:$`          | Position the cursor at the last line  of the file.                                                   |
|       `:set nu`       | Turn on line numbering.                                                                              |
|      `:set nonu`      | Turn off line numbering.                                                                             |
| `:help <sub-command>` | Get help for any of the sub-commands.                                                                |
|                       |                                                                                                      |

