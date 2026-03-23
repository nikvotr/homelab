# Homelab Cybersecurity Project

This repository documents the setup and evolution of my personal homelab.

The goal of this project is to learn:

- system administration
- networking
- cybersecurity
- containerization (Docker)
- monitoring and infrastructure

## Hardware

- Intel i3-4430
- 6GB RAM
- 240GB SSD (OS)
- 2TB HDD (data)
- 160GB HDD (unused)

## Architecture

- OS: Ubuntu Server 24.04 LTS
- Remote access: SSH
- Containerization: Docker
- Data storage: /srv/data
- Services: Portainer, Netdata, Cowrie (honeypot)

## Features

- Headless server (no GUI)
- Static IP configuration
- SSH key authentication
- Firewall (UFW)
- Fail2Ban protection
- Docker-based services
- Real-time monitoring (Netdata)
- Honeypot for attack analysis (Cowrie)

## Project Structure

- 01-intro → project overview
- 02-hardware → hardware details
- 03-installation → OS installation
- 04-storage → disk configuration
- 05-docker → Docker setup
- 06-services → deployed services
- 07-security → security configuration

## Goals

- build real-world infrastructure knowledge
- practice cybersecurity concepts
- document everything clearly
- create a portfolio project for university

## Notes

This homelab is designed for learning and experimentation, not production use.
