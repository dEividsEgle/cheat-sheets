# File Sharing

## Quick Copy (Python HTTP Server)

Create a simple python web server within a directory to copy files from one device to another. This is only to be used in a private secure network.

- Make the directory available on port 8000
```bash
python -m SimpleHTTPServer
```

## rsync

Rsync is a standard synchronizer used for transfering files, that can also perform analysis and verification.

The `rsync` program must be installed on both the source and destination machine, with available connection between the two.

- Copy group of files to home directory on *host*.
```bash
rsync <file1> <file2> ... <host>:
```
- Transfer entire directory hierarchies, complete with symbolic links, permissions, modes, and devices.
```bash
rsync -a <dir> <host>:<dest_dir>
```
- Run the `rsync` program in *dry run* mode.
```bash
rsync -nva <dir> <hsot>:<dest_dir>
```
- Make an exact copy of directory structure
```bash
rsync -a --delete <dir> <host>:<dest_dir>
```

- Add forward slash(/) to copy everything inside *dir* to *dest_dir*. By default, without a forward slash, *dir* would be placed within *dest_dir*.
```bash
rsync -a <dir/> <host>:<dest_dir>
```
- Transfer directory excluding particular files and directories (pattern matched).
```bash
rsync -a --exclude=.html <source> <host>:
```

> **_NOTE:_**  Add forward slash (/) to exclude only one specific item.

- Transfer files from the remote host to local machine.
```bash
rsync -a <host<:<src_dir> <dest_dir>
```

## Samba

Samba is the standard file sharing software for Unix. With *samba* you can have you Windows devices get to the Linux system and the other way around.

#### Setup samba

1. Create an `smb.conf` file
2. Add file sharing section to `smb.conf`
3. Add printer sharing section to smb.conf
4. Start samba daemons `nmbd` and `smbd`