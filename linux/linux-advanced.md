# Kernel Initialization

Kernel initialization order during startup:
1. CPU Inspection
2. Memory inspection
3. Device bus discovery
4. Device discovery
5. Auxiliary kernel subsystem setup (networking)
6. Root filesystem mount
7. User space start

## Kernel Parameters

- View the parameters passed to the systems kernel
```bash
cat /proc/cmdline
```

# Boot Loaders

- Check if the system is using BIOS or UEFI
```bash
ls /sys/firmware/efi
```

If the above path does not exists, the system is using BIOS. Alternatively, run the `efibootmgr` command to see if any *boot targets* are returned, if so, then the system is using UEFI, otherwise, it will be using BIOS.

## Boot Loader Tasks

Boot Loader core functionality:
- Select from multiple kernels.
- Switch between sets of kernel parameters.
- Allow the user to manually override and edit kernel image names and parameters.
- Provide support ofr booting other operating systems.

# GRUB

GRUB (Grand Unified Boot Loader) navigates the filesystem that allow for kernel image and configuration selection.

GRUB menu can be accesed by holding down `shift` during boot process, or `esc` if the system uses UEFI.

## How GRUB Works

1. The PC BIOS or firmware initializes the hardware and searches its bootorder storage devices.
2. Upon finding the boot code, the BIOS/firmware loads and executes the code.
3. The GRUB core loads.
4. The core initializes. GRUB can now access disks and filesystems.
5. GRUB identifies its boot partitions and loads a configuration there.
6. GRUB gives the user a chance to change the configuration.
7. After a timeout or user action, GRUB executes the *grub.cfg* (configuration) file.
8. During the execution of the configuration, GRUB might load additional modules in the boot partition.
9. GRUB executes a boot command to load and execute the kernel as specified by the configuration linux command.

