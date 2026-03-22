# Docker Setup

In this section, I describe how I installed and configured Docker on my homelab.

## What is Docker?

Docker is a containerization platform that allows running applications in isolated environments.

Instead of installing software directly on the system, services run inside containers.

## Why Docker?

I chose Docker because:

- easy to deploy services
- isolation between applications
- reproducible environments
- widely used in real-world infrastructure

## Installation

Docker was installed using the package manager:

sudo apt update
sudo apt install -y docker.io docker-compose-v2

## Enable Docker

To ensure Docker starts automatically:

sudo systemctl enable docker
sudo systemctl start docker

## User Permissions

To avoid using sudo for every command, I added my user to the docker group:

sudo usermod -aG docker $USER

Then applied it:

newgrp docker

## Verification

To verify that Docker works:

docker --version
docker compose version

Test container:

docker run hello-world

If the container runs successfully, Docker is working correctly.

## Why Containers?

Containers allow:

- running multiple services without conflicts
- easy updates and removal
- quick deployment of applications
- better resource management

## Project Structure

I use the following structure for Docker services:

/srv/data/docker/

Each service has its own folder.

Example:

/srv/data/docker/portainer
/srv/data/docker/jellyfin

## Example: Portainer

I deployed Portainer as a Docker container to manage other containers.

It runs on port 9000 and provides a web interface.

## Key Takeaways

- Docker simplifies service deployment
- containers are isolated from the system
- using docker group improves usability
- structure matters for long-term management

## Notes

Docker is the foundation of this homelab and will be used for all services.
