# Services

In this section, I describe the services deployed in my homelab using Docker.

## Overview

Services are deployed using Docker containers.

This allows easy management, isolation, and scalability.

## Portainer

Portainer is used as a web-based interface to manage Docker containers.

### Why Portainer?

- simplifies container management
- provides a graphical interface
- allows easy deployment and monitoring

### Deployment

Portainer was deployed using Docker Compose.

It runs on:

http://SERVER-IP:9000

### Functionality

With Portainer, I can:

- start and stop containers
- view logs
- manage volumes
- deploy new services

## Data Storage

All service data is stored in:

/srv/data/docker/

This ensures:

- persistence across container restarts
- centralized storage
- easy backups

## Example Structure

/srv/data/docker/portainer
/srv/data/docker/jellyfin

Each service has its own directory.

## Networking

Services are exposed via specific ports.

Example:

- Portainer -> 9000
- future services -> different ports

This allows access from other devices in the network.

## Future Services

Planned services include:

- Jellyfin (media server)
- Netdata (monitoring)
- vulnerable applications for testing

## Key Takeaways

- Docker enables fast deployment of services
- Portainer simplifies management
- structured storage is important
- services can be expanded over time

## Netdata (Monitoring)

Netdata is used for real-time monitoring of the server.

It provides:

- CPU usage
- memory usage
- disk activity
- network statistics
- process monitoring

The service runs on:

http://SERVER-IP:19999

This allows easy observation of system behavior and performance.

## Notes

This is the starting point of the homelab service layer.
