# Arch Linux Installation

This guide will be on how to install Arch Linux with my preferences generally.  
A more specific guide for my desktop and laptop setup can be found here:
- Laptop
- Desktop
 
## Table of Contents

# General Dependencies

You will just need a live boot stick with Arch Linux.  
You can find more information on this here:  
- [Arch Wiki](https://wiki.archlinux.org/index.php/USB_flash_installation_medium)
- [Youtube Guide](https://www.youtube.com/watch?v=xb4fiFda4no)
  - It is done using a linux distro but the GUI interface should be the same as windows

# Guide

As for my preference to install Arch Linux, I mainly go for a very standard installation, following very closely to the Arch Wiki Installation Guide.
You may find that I do things in a different order, mainly due to preference.
The only things I really change are how I connect to the internet and the option for dual boot.  

**Note:*** I will not be showing screenshots of the installation phase (As it does not have a GUI then anyway), instead I will be showing the bash commands to act as references.
This guide is mainly targetted at intermediate and advanced users of Arch Linux.

## Connecting to the internet

Depending on whether you are connected to Wifi or Ethernet, how you connect to the internet here will defer.
As such I will leave it to you to connect to the internet.  

## Partitioning the disks

This step is also quite dependent on your system.
For me, I usually just have a `UEFI`, `Linux Swap` and `Linux File System` partition.
The thing to take note off, is that in setting it up and linking them, you have to be very careful, as generating the wrong fstab can brick the system.  

We will mainly be using the `cfdisk`  utility to partition our disks.  

```bash
cfdisk [device..] # Make sure to specify the disk, if using multiple disk
cfdisk /dev/nvme0n1 # Example using an nvme ssd

# Afterwards create a UEFI, Linux Swap and Linux File System partitions

# Note that the UEFI partition can be shared with Windows UEFI partition
# So if the windows one already exists, there is no need for one more
```

In order to check how our partitions are like, we can use:  

```bash
# Using fdisk, has more details
fdisk -l [device...]
fdisk -l /dev/nvme0n1 # Example

# We can also use lsblk, more general overview
lsblk [device...]
lsblk /dev/nvme0n1 # Example
```

## Format the partitions

Now that you have your partitions, you have to format them such that the partition type matches what that partition is for.  

Generally, you would want: (Note you can use other partition types depending on your situation)  
- `UEFI` partition &rarr; `FAT32`
- `Linux Swap` partition &rarr; `Swap`
- `Linux File System` partition &rarr; `EXT4`

The code to do this would be:

```bash
mkfs.fat -F32 <device> # For FAT32 partition type
swapon <device> # For the swap partition type
mkfs.ext4 <device> # For the EXT4 partition type

# Examples
mkfs.fat -F32 /dev/nvme0n1p1
swapon /dev/nvme0n1p2
mkfs.ext4 /dev/nvme0n1p3
```

# Conclusion

# References

### Updates


<!-- 
REMOVE ME WHEN COPYING

Make sure to add Table of Contents (TOC) when done
Make sure to generate section numbers when done

Take note to comment out the first two sections when doing this
 -->


