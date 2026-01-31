# 🚀 Deployment Guide

This guide provides instructions for running the microservices using Docker Compose.

## 📋 Prerequisites

- Docker installed on your system
- Docker Compose installed
- All services configured properly

## 🏃 Quick Start

### Run All Services

Execute the following command from the **root directory** of the project:

```bash
docker compose up --build
```

This command will:
- Build all Docker images from scratch
- Start all services in the foreground
- Display logs from all containers in the terminal

### Run in Background Mode

To run services in detached mode (background):

```bash
docker compose up -d --build
```

This is useful when you want to:
- Keep your terminal free for other tasks
- Run services as background processes
- Avoid terminal output clutter

### View Logs (Background Mode)

If running in background mode, view logs with:

```bash
docker compose logs -f
```

## 🛑 Stopping Services

To stop and remove all running containers:

```bash
docker compose down
```

This command will:
- Stop all running containers
- Remove containers
- Remove networks created by Docker Compose

### Stop and Remove Volumes

To also remove volumes (⚠️ **this will delete data**):

```bash
docker compose down -v
```

## 📊 Service Status

Check the status of running services:

```bash
docker compose ps
```

## 🔧 Useful Commands

| Command | Description |
|---------|-------------|
| `docker compose up --build` | Build and start all services |
| `docker compose up -d --build` | Build and start in background |
| `docker compose down` | Stop and remove containers |
| `docker compose logs -f` | Follow logs from all services |
| `docker compose ps` | List running services |
| `docker compose restart` | Restart all services |

## 📝 Notes

- Always run commands from the **root directory** of the project
- Use `--build` flag to ensure latest code changes are included
- Background mode (`-d`) is recommended for development environments
