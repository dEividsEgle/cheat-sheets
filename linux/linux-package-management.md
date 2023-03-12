# Managing Linux Packages

### Package manager
Package manager install, upgrades, and removes packages. By default the package manager will pull the packages from an online repository, but this can be configured to point to a local repository to download and install packages from there.

## RPM Based Distros

### Yellow Dog Updater (YUM)
`yum` is a package manager that has been used to install RPM based packages on RPM based distros, such as CentOS and RHEL. YUM provides dependency resolution, meaning, that all the dependencies will be install during installation or removed during un-installation. 

Starting with RHEL7 the `yum` package manager has been replaced by `dnf`. All the command that worked with `yum` will work with `dnf`.

#### Install, upgrade, and remove packages with dnf
| Command                                   | Description                                                                      |
| ----------------------------------------- | -------------------------------------------------------------------------------- |
| `dnf search <string>`                     | Search a package by it's name or description.                                    |
| `dnf list installed`                      | List installed packages.                                                         |
| `dnf info <package>`                      | Display info about the package.                                                  |
| `dnf install <package>`                   | Install a package.                                                               |
| `dnf remove package`                      | Remove the installed package.                                                    |
| `dnf upgrade`</br>`dnf upgrade <package>` | Upgrade all packages on the system.</br>Upgrade specified package on the system. |
| `dnf autoremove`                          | Remove all the unused dependencies on the system.                                                                                 |

### RPM
`rpm` allows sysadmin to install, update, and remove packages similar to `yum`. However, unline `yum`, `rpm` cannot manage dependency resolution. 

#### Install, upgrade, and remove packages with rpm
| Command                  | Description                                        |
| ------------------------ | -------------------------------------------------- |
| `rpm -qa`                | View all installed packages.                       |
| `rpm -qf <file-path>`    | List the package that the defined file belongs to. |
| `rpm -ql <package>`      | List files that belong to the package.             |
| `rpm -ivh <package>.rpm` | Install a package from the defined file.           |
| `rpm -e <package>`       | Remove the package.                                                   |

## DEB Based Distros

### Advanced Packagin Tool (APT)
`apt` package manager works similar to `yum` only on DEB based disctros, such as Ubunut and Kali. Just as `yum`, `apt` provides dependency resolution and will install all the required dependiecies during isntallation.

#### Install, upgrade, and remove packages with apt
| Command                      | Description                                                                       |
| ---------------------------- | --------------------------------------------------------------------------------- |
| `apt update`                 | Update the list of available packages to be isntalled.                            |
| `apt search <package>`       | Find the package to install.                                                      |
| `apt install [-y] <package>` | Install the package including all it's dependencies.                              |
| `apt remove <package>`       | Remove the package binaries.                                                      |
| `apt purge <paclage>`        | Completely remove the package including all the binaries and configuration files. |
| `apt upgrade`                | Check and install system updates.                                                 |
| `apt autoremove`             | Remove all the unused dependencies on the system.                                                                                  |

#### Install, upgrade, and remove packages with dpkg
| Command                 | Description                              |
| ----------------------- | ---------------------------------------- |
| `curl -O <URL>`         | Dowloade the package.                    |
| `dpkg -i <package>.deb` | Install the downloaded package.          |
| `dpkg -l <package>`     | Search for the installed package.        |
| `dpkg -L <package>`     | View all the files owned by the package. |
| `dpkg -r <package>`     | Remove the installed package.            |
|                         |                                          |

