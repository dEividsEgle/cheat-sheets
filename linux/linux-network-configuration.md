# Linux Networking

# Common Network Commands

| Command              | Description                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| `ip address show`    | Show the current IP address configuration on the network interfaces.                              |
| `ip route show`      | View the routing table.                                                                           |
| `ip -6 address show` | View the IPv6 confiugration.                                                                      |
| `ip -6 route show`   | View the IPv6 route table.                                                                        |
| `ping <host>`        | Send ICMP packet. Use the `-4` and `-6` options to either use IPv4 or IPv6.                       |
| `host`               | Find and address behind a domain name.                                                            |
| `netstat`            | View currently open connections. Use the `-t` option to limit the output to only TCP connections. |
| netstat -l           | List all ports that the local machine are listening on.                                           |
| `ip -r neigh`        | View IPv4 arp table.                                                                              |
|                      |                                                                                                   |

----
# Interface Configuration

#### Manually Configure Interfaces
 - Add IP address and subnet for kernel network interface
```bash
ip address add <address/subnet? dev <interface>
```

#### Adding and Deleting Routes
- Add a default gateway route
```bash
ip route add default via <gw-address> dev <interface>
```
- Delete default gateway route
```bash
ip route del default
```
- Add a route
```bash
ip route add <192.168.10.0/24> via <172.16.0.1>
```
- Delete a route
```bash
ip route del <192.168.10.0/24>
```

----
# DNS

#### /etc/hosts

On most systems, `/etc/hosts` file can be user to override hostname lookups.

#### resolv.conf

The `/etc/resolv.conf` is the traditional DNS server configuration file.

#### Link-Local Multicast Name Resolution

Link-Local Multicast Name Resolution (LLMNR) is a zero-configuration name servcie system that can find a host by name on the local network by broadcasting a request over the network; if present, the target hot replies with it's address. Another such system is the   **Multicast DNS (mDNS)** zero-configuration name service system.

#### /etc/nsswitch.conf

The `/etc/nsswitch.conf` file is the traditional interface for controlling several name-related precedence settings on the system, such as user and password information, and it has a host lookup setting.

----
# DHCP

#### DHCP clients

The *dhcpclient* stores it's process ID in `/var/run/dhcplient.pid` and it's lease information in `/var/lib/dhcp/dhcpclient.leases`. 

----
# Wireless

The `iw` command can be used to view and change the network configuration. To use the `iw` command you must know the interface name, such as *wlp1s0* (predictable device name) or *wlan0* (traditional name).

#### Common commands

| Command                    | Description                        |
| -------------------------- | ---------------------------------- |
| `iw dev wlp1so scan`       | Scan for available networks.       |
| `iw dev wlp1so link`       | View the wireless network details. |
| `iw wlp1so connect <SSID>` | Connect to an unsecure network.    |
|                            |                                    |

----

# Diagnostics

## Netstat

Netstat can be an usefule tool to diagnose some common probelms at the application layer. Netstat can display a number of transport and network layer statistics. It is available on both windows and linux, however, the option parameters differe between the systems.

#### Common `netstat` options

| Option | Description                                               |
| ------ | --------------------------------------------------------- |
| `-t`   | TCP port information.                                     |
| `-u`   | UDP port information.                                     |
| `-l`   | Prints listening ports.                                   |
| `-a`   | Prints active ports.                                      |
| `-n`   | Disable name lookups (a must in case DNS is not working). |
| `-4`   | Limit output to IPv4.                                     |
| `-6`   | Limit output to IPv6.                                     |

## Netcat

Netcat can be used to connect to remote TCP/UDP ports, specify a local port, listen on ports, scan ports, redirect standard I/O to and from network connections, and more.

- Open a TCP connection to a port.
```bash
netcat <host> <port>
```
- Listen on a specified port.
```bash
netcat -l <port>
```


> **_NOTE:_**  Add the `-v` option to display verbose mesages. By default, there is no debugging output provided in the shell.


## Port Scanning

#### Network mapper (nmap)

To find what services are being offered or which IP addresses are being used, use the `nmap` program. Nmap scans all ports on network of machines and looks for open ports.

Nmap can be ran on local network and from outside the local network to give an overview of what the firewall might or might not be blocking.

- Run a genereic scan on a *host*.
```bash
nmap <host>
```

