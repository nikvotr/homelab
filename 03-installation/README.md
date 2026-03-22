# Operating System Installation

In this section, I describe how I installed and configured the base system for my homelab.

## OS Choice

I chose Ubuntu Server 24.04 LTS for the following reasons:

- lightweight and stable
- widely used in real-world environments
- good documentation and community support
- no unnecessary graphical interface

## Installation Process

The installation was done using a bootable USB drive.

Steps:
1. Download Ubuntu Server ISO
2. Create bootable USB
3. Boot from USB
4. Start installation

## Disk Selection

I used a dedicated SSD for the operating system:

- 240GB SSD -> system (Ubuntu)
- 2TB HDD -> data (configured later)
- 160GB HDD -> reserved for future use

Using an SSD for the OS significantly improves system performance.

## Disk Configuration

During installation, I selected:

- "Use entire disk" on the SSD

This is a simple and reliable setup for a homelab environment.

## Network Configuration

Initially, the system used DHCP.

After installation, I configured a static IP to ensure stable access via SSH.

This is important because:

- services depend on a fixed address
- remote access becomes predictable

## SSH Setup

I enabled OpenSSH during installation.

This allows:

- remote management of the server
- no need for monitor/keyboard after setup

## Post-Installation Setup

After the system was installed, I performed:

sudo apt update && sudo apt upgrade -y

Installed basic tools:

sudo apt install -y curl wget git htop net-tools

## Key Takeaways

- Always install the OS on SSD if possible
- Keep the system minimal (no GUI)
- Enable SSH for remote management
- Plan disk usage from the beginning

## Issues Encountered

During setup, I experienced a network issue where SSH connections failed with:

"No route to host"

This was caused by a network configuration inconsistency after reboot.

The issue was resolved by restarting the system and verifying the assigned IP address.

## Notes

This setup is optimized for learning and experimentation, not for production use.
