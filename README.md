# doctainer-lab

# docktainer-lab

A step-by-step guide to simplifying Docker management using Portainer, based on the tutorial ["learning Docker is HARD!! (this makes it easy)"](https://www.youtube.com/watch?v=iX0HbrfRyvc) by NetworkChuck. This project helps streamline container operations through a visual interface.

## Overview

Portainer is a web-based Docker GUI that makes managing containers, images, volumes, networks, and stacks much easier—without relying on the command line. This repo documents how to install, configure, and use Portainer effectively.

## Prerequisites

- Docker must be installed and running on your machine.
- A terminal with Docker CLI access.

## Installation

1. Create a persistent volume for Portainer data:

   ```bash
   docker volume create portainer_data


docker run -d -p 8000:8000 -p 9443:9443 \
  --name=portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce:latest


https://localhost:9443
