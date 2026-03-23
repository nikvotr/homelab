# Security

In this section, I describe basic security measures applied to my homelab server.

## Overview

Security is an important part of any infrastructure, even in a home environment.

The goal is to reduce the attack surface and understand real-world threats.

## Why Security Matters

Even a simple home server can be exposed to attacks.

Basic hardening is important to:

- protect services
- prevent unauthorized access
- reduce attack surface

## SSH Security

SSH is the main way to access the server.

Basic improvements:

- disable root login
- use strong passwords
- (future) use SSH keys instead of passwords

## SSH Hardening
SSH is the primary access method to the server.

The following changes were applied:

- disabled root login
- (later) switched to SSH key authentication
- restricted access to trusted users only

Configuration file:

/etc/ssh/sshd_config

## Firewall (UFW)

A firewall was configured to limit network access.

Allowed ports:

- 22 (SSH)
- 9000 (Portainer)
- 19999 (Netdata)
- 3000 (Grafana)
- 2222 (Cowrie honeypot)

All other ports are blocked by default.

## Fail2Ban

Fail2Ban was installed to protect against brute-force attacks.

It monitors login attempts and blocks suspicious IPs.

## Honeypot (Cowrie)

A Cowrie SSH honeypot was deployed on port 2222.

It simulates a vulnerable SSH server and captures:

- login attempts
- usernames and passwords
- executed commands

This allows observing attacker behavior in a controlled environment.

## Issues Encountered

### SSH Connection Issue

At one point, SSH connections failed with:

"No route to host"

This was caused by a network configuration issue after reboot.

The problem was resolved by restarting the system and verifying the assigned IP address.

---

### SSH Host Key Warning

After restarting the honeypot, SSH produced:

"REMOTE HOST IDENTIFICATION HAS CHANGED"

This happened because the honeypot generates a new SSH key on each restart.

Solution:

ssh-keygen -f ~/.ssh/known_hosts -R "[SERVER-IP]:2222"

---

### Docker Volume Misconfiguration

Initially, the honeypot failed with errors like:

"No such file or directory: /var/lib/cowrie/..."

This was caused by incorrect volume mapping.

Fix:

./data:/var/lib/cowrie

---

### Missing Directories

Even after fixing the volume, Cowrie failed due to missing directories.

Solution:

- created required folders manually
- adjusted permissions

---

## Key Takeaways

- security is not optional, even in a homelab
- understanding errors is part of learning
- proper configuration prevents real vulnerabilities
- observing attacks provides valuable insight

## Notes

This setup focuses on learning practical cybersecurity concepts through real implementation.
