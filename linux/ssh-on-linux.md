# SSH

#### Common commands

| Command               | Description                                                       |
| --------------------- | ----------------------------------------------------------------- |
| ssh-keygen            | Program included with OpenSSH used for generating the keys.       |
| systemctl enable sshd | Start the SSH server. The server might not be running by default. |
|                       |                                                                   |

#### sshd server

Running the sshd server to allow remote connections to the system requires a configuration file and host keys. The confiugration file is kept in the `/etc/ssh` directory. The server configuration file name is called `sshd_config`.

#### Creating ssh keys

OpenSSH comes with the `ssh-keygen` program that allows for creation of the SSH version 2 keys. There are two type of keys using the two different  cryptography alorithms, RSA and DSA.  Each set has a public key (*.pub*) and private key.

- Create the RSA key
```bash
ssh-keygen -t rsa -N '' -f /etc/ssh/ssh_hsot_rsa_key
```
- Create the DSA key
```bash
ssh-keygen -t dsa -N '' -f /etc/ssh/ssh_host_dsa_key
```

The SSH server and clients use a *key file*, called *ssh_known_hosts*, to store public keys from known hosts, meaning, to use authentication based on a remote clients identity, the servers *ssh_known_hosts* file must contain the public host keys of all trusted clients.

#### ssh client

The SSH client configuration file  `ssh_config` should be in `/etc/ssh` directory. The same directory where the `sshd_config` file resides.

- Log in to a remote host.
```bash
ssh <username>@<remote_host>
```

#### SSH file transfer

OpenSSH includes file transper programs **scp** and **sftp** that have replaces **rcp** and **ftp**. 

- Copy a file from remote host to current directory.
```bash
scp <user>@<host>:<file> .
```
- Copy a file from local host to remote host.
```bash
scp <file> <user>@<host>:<dir>
```
- Copy files between two remote hosts.
```bash
scp <user1>@<host1>:<file> <user2>@<host2>:<dir>
```

