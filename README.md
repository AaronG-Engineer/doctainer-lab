
# doctainer-lab

A lightweight Docker lab environment powered by Porter for GUI-based container orchestration. This project demonstrates containerized management across local and remote hosts using a web interface, eliminating CLI overhead while providing full visibility into Docker environments through Porter's agent-based architecture.

## How It Works

1️⃣ Deploy Porter server as a Docker container with GUI access.  
2️⃣ Install remote agents on Docker hosts for centralized management.  
3️⃣ Deploy Docker Compose stacks through the web interface.  
4️⃣ Monitor and manage containers across multiple hosts from one dashboard.

**Tech Stack:** Docker | Porter | Linux | Docker Compose | Remote Agents

# 🐳 Docker Management Pipeline

An automated **container orchestration system** using **Docker, Porter, and remote agents**. When Porter is deployed as a container, it provides a **web-based GUI** for managing Docker environments, deploys **Docker Compose stacks**, and connects to **remote Docker hosts** through secure agents.

---

# Docker Management Pipeline

## Overview

This project sets up an automated pipeline for Docker container management using Porter's web-based interface. The system leverages Docker for container runtime, Porter for GUI orchestration, persistent volumes for data storage, and remote agents for multi-host management.

## Steps Taken

### 1. **Host Preparation**
- Updated system and installed Docker on the host machine.
- Verified Docker installation with test container deployment.

```bash
sudo apt update
sudo apt install docker.io -y
docker run -d -p 8080:80 nginx
docker ps
```

### 2. **Porter Server Deployment**
- Created persistent volume for Porter data storage.
- Deployed Porter server container with GUI and API access.

```bash
docker volume create container_stuff_stuff
docker run -d \
  -p 9443:9443 \
  -p 8000:8000 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v container_stuff_stuff:/portervolume \
  portertech/porter
```

### 3. **GUI Access and Configuration**
- Accessed Porter web interface at `https://<host-ip>:9443`.
- Created admin user account for container management.
- Configured local Docker environment through the dashboard.

### 4. **Remote Agent Installation**
- Generated agent install commands through Porter GUI.
- Installed agents on remote Docker hosts for centralized management.
- Verified secure connections without exposing additional ports.

### 5. **Stack Deployment**
- Deployed **Docker Compose** applications through Porter interface.
- Configured multi-container orchestration with real-time monitoring.
- Added environment variables and persistent volumes as needed.

### 6. **Multi-Host Management**
- Connected multiple Docker hosts through agent-based architecture.
- Managed containers, volumes, and networks from single dashboard.
- Monitored container states and resource usage across environments.

### 7. **Testing and Troubleshooting**
- Deployed sample stacks and monitored performance.
- Initial issues:
  - Docker socket mounting errors—resolved by ensuring proper volume mounts.
  - Agent connection failures—fixed by running install commands with sudo privileges.
  - HTTPS certificate warnings—accepted browser security warnings for self-signed certificates.

## Results

The pipeline now successfully manages Docker containers across multiple hosts through Porter's web interface. The system provides centralized visibility, simplified stack deployment, and secure remote management without manual CLI operations.

## Tech Stack

**Infrastructure:**
- Docker Engine
- Porter (GUI Orchestration)
- Ubuntu Linux
- Docker Volumes

**Orchestration:**
- Docker Compose
- Porter Stacks
- Remote Agents

**Deployment:**
- Containerized GUI
- Agent-based Remote Management
- Web-based Interface

### 📌 Credits

This project was built following a tutorial by [NetworkChuck](https://youtu.be/iX0HbrfRyvc?si=lTzVcGlM5ItT1AwD).
