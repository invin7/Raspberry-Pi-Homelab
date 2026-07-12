# Raspberry Pi Homelab

A self-hosted homelab built on a Raspberry Pi 5 to explore Linux system administration, networking, storage management, containerization, and self-hosting.

The server provides private cloud storage, media streaming, secure password management, and remote access while running entirely on a headless Raspberry Pi OS installation. Data is stored on a Samsung T7 external SSD, and services are managed using a combination of native Linux services and Docker Compose.

---

## Features

- 📁 Private cloud storage with Nextcloud
- 🎬 Media streaming using Jellyfin
- 🔐 Self-hosted password manager with Vaultwarden
- 🔒 Secure remote access using Tailscale + MagicDNS
- 🐳 Docker Compose for containerized services
- 💾 Persistent storage on an external Samsung T7 SSD
- 🖥️ Headless server managed entirely over SSH

---

## Architecture

```mermaid
flowchart TD

    Laptop[Laptop]
    Phone[Phone]

    Laptop --> TS[Tailscale + MagicDNS]
    Phone --> TS

    TS --> Pi[Raspberry Pi 5]

    Pi --> Apache[Apache + PHP]
    Pi --> Docker[Docker Compose]

    Apache --> Nextcloud[Nextcloud]

    Docker --> Jellyfin[Jellyfin]
    Docker --> Vaultwarden[Vaultwarden]

    Nextcloud --> SSD[Samsung T7 SSD]
    Jellyfin --> SSD
    Vaultwarden --> SSD
```

---

## Hardware

| Component | Specification |
|-----------|---------------|
| SBC | Raspberry Pi 5 |
| Storage | Samsung T7 Portable SSD (500 GB) |
| OS | Raspberry Pi OS (64-bit, Headless) |

---

## Software Stack

| Category | Technology |
|----------|------------|
| Operating System | Raspberry Pi OS (64-bit) |
| Web Server | Apache |
| Database | MariaDB |
| PHP | PHP 8.4 |
| Containers | Docker & Docker Compose |
| Cloud Storage | Nextcloud |
| Media Server | Jellyfin |
| Password Manager | Vaultwarden |
| Remote Access | Tailscale + MagicDNS |
| Server Management | SSH |

---

## Services

| Service | Purpose | Deployment |
|----------|---------|------------|
| Nextcloud | Private cloud storage and file synchronization | Native |
| Jellyfin | Personal media streaming | Docker Compose |
| Vaultwarden | Self-hosted password management | Docker Compose |

---

## What I Learned

This project provided hands-on experience with:

- Linux system administration
- Docker Compose and container management
- Apache, PHP, and MariaDB configuration
- Storage management using an external SSD
- Persistent filesystem mounting
- SSH-based server administration
- Secure networking using Tailscale and MagicDNS
- Deploying and maintaining multiple self-hosted services

---

## Future Improvements

- Add automated backups
- Configure HTTPS using a reverse proxy
- Add monitoring with Grafana and Prometheus
- Automate deployments with Ansible
- Implement container health monitoring

---

## Repository

The repository contains documentation, configuration files, and setup instructions used to build and maintain the homelab.

> **Note:** Sensitive configuration files, credentials, API keys, and personal data have been intentionally excluded from this repository.
