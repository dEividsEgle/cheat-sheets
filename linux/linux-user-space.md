# User Space

User space starting order:
1. `inti`
2. Low-level services.
3. Network configuration.
4. Mid-and high-level services (cron, printing, etc.)
5. Login prompts, GUIs, and high-level applications.

## init

`init` is a user-space program that starts and stops the essential service processes on the system. This is usually a series of scripts that `init` runs in sequence, one at a time. One script usually starts a service or configures a piece of software. 

`init` can be found in the `/sbin` along with the other system bineries. 

## systemd

There are different implementations of init such as System V and Upstart, however, systemd is the standard implementation of init.

Systemd configuration files are spread amond many directories across the system. 