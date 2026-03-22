# Storage Configuration

In this section, I describe how I configured storage for my homelab.

## Disk Overview

My system has multiple drives:

- SSD (240GB) -> operating system
- HDD (2TB) -> main data storage
- HDD (160GB) -> secondary storage (not used yet)

## Why Separate Storage?

I decided to separate the operating system and data storage for the following reasons:

- better performance (OS on SSD)
- easier data management
- safer upgrades and reinstalls
- clearer structure

## Disk Identification

To identify available disks, I used:

lsblk

This showed all connected drives and partitions.

## Formatting the Data Disk

The 2TB HDD was formatted using ext4 filesystem:

sudo mkfs.ext4 /dev/sdc1

Note: This deletes all existing data on the disk.

## Mount Point

I created a dedicated directory for data storage:

sudo mkdir -p /srv/data

This directory is used for:

- media files
- Docker volumes
- application data

## Mounting the Disk

To mount the disk:

sudo mount /dev/sdc1 /srv/data

After mounting, I verified it using:

df -h

## Persistent Mount (fstab)

To ensure the disk is mounted automatically after reboot, I added it to /etc/fstab.

First, I got the disk UUID:

sudo blkid /dev/sdc1

Then I edited fstab:

sudo nano /etc/fstab

And added:

UUID=YOUR-UUID-HERE /srv/data ext4 defaults 0 1

## Why UUID?

Using UUID instead of /dev/sdc1 is important because:

- device names can change after reboot
- UUID ensures stable mounting

## Verification

After configuration, I tested it:

sudo mount -a

If no errors appear, the configuration is correct.

## Key Takeaways

- always separate OS and data
- use /srv for server data
- use UUID in fstab
- verify mounts after changes

## Notes

This setup is simple but effective for a homelab environment.
