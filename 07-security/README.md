# Security

In this section, I describe basic security measures applied to my homelab server.

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

## Firewall

I use a firewall to limit access to the system.

Only necessary ports should be open.

Example:

- SSH (22)
- web services (e.g. 9000 for Portainer)

## Fail2Ban

Fail2Ban protects against brute-force attacks.

It monitors logs and blocks IPs after repeated failed login attempts.

## Principle of Least Privilege

Only required services and ports should be enabled.

Unused services should be removed or disabled.

## Monitoring

Monitoring tools help detect unusual behavior.

This will be implemented later (Netdata).

## Future Improvements

- SSH key authentication
- disable password login
- intrusion detection tools
- network segmentation

## Key Takeaways

- security is a continuous process
- even basic protection is important
- understanding threats is essential
