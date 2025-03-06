# Docker Guide

## Introduction

This guide covers the basics of Docker, including Docker images, Dockerfiles, Docker Compose, Multi-stage builds, Docker Volumes, and Port Mapping. If you're new to Docker, this is a good starting point!

---

## 📦 What is Docker?

Docker is a platform for developing, shipping, and running applications inside lightweight, portable containers. Containers allow developers to package applications with all dependencies, making them easy to run across different environments.

---

## 🏗️ Docker Images

A **Docker Image** is a blueprint for creating Docker containers. It contains everything needed to run an application, including code, runtime, libraries, and dependencies.

- Images are **built** from a `Dockerfile`.
- They are stored in a **Docker Registry** (like Docker Hub).
- Containers are instances of images.

### Common Commands:
```sh
# Pull an image from Docker Hub
docker pull ubuntu

# List downloaded images
docker images

# Remove an image
docker rmi <image_id>
```

---

## 📜 Dockerfile

A **Dockerfile** is a script containing a set of instructions to build a Docker image.

### Example Dockerfile:
```Dockerfile
# Use an official base image
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package.json .
RUN npm install

# Copy the rest of the app
COPY . .

# Expose the application port
EXPOSE 3000

# Run the application
CMD ["node", "server.js"]
```

### Build & Run:
```sh
# Build an image from the Dockerfile
docker build -t myapp .

# Run a container from the image
docker run -p 3000:3000 myapp
```

---

## 🔌 Docker Port Mapping

Docker containers run in isolated environments, so they do not expose their ports to the host machine by default. Port mapping allows external access.

### Example:
```sh
# Run a container and map port 8080 on host to port 80 in the container
docker run -p 8080:80 nginx
```

This means that visiting `http://localhost:8080` will access the web server running inside the container.

---

## 📂 Docker Volumes

Docker **volumes** provide persistent storage for containers, allowing data to survive container restarts.

### Example:
```sh
# Create a volume
docker volume create myvolume

# Run a container with the volume mounted
docker run -v myvolume:/app/data myapp
```

Volumes are stored outside the container filesystem, making them useful for databases and persistent data.

---

## 🏗️ Docker Compose

Docker Compose allows you to manage multi-container applications using a simple YAML file.

### Example `docker-compose.yml`:
```yaml
version: '3'
services:
  app:
    build: .
    ports:
      - "3000:3000"
  db:
    image: postgres
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```

### Commands:
```sh
# Start all services
docker-compose up

# Stop services
docker-compose down
```

---

## ⚡ Docker Multi-Stage Build

Multi-stage builds help reduce image size by separating build dependencies from the final image.

### Example:
```Dockerfile
# Build stage
FROM node:18 AS builder
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

# Final stage
FROM node:18
WORKDIR /app
COPY --from=builder /app/dist ./dist
CMD ["node", "dist/server.js"]
```

### Benefits:
✅ Smaller final image size  
✅ No unnecessary dependencies  
✅ Better security  

---

## 🆚 Docker Containers vs Virtual Machines

Docker Containers and Virtual Machines (VMs) both allow running applications in isolated environments, but they work differently.

| Feature            | Docker Containers | Virtual Machines |
|--------------------|------------------|------------------|
| Startup Time      | Fast (seconds)    | Slow (minutes)   |
| Resource Usage    | Lightweight      | Heavy            |
| Isolation        | Process-level     | Full OS-level    |
| Storage          | Shared kernel     | Separate disk    |
| Performance      | Near-native       | Slower due to overhead |

Docker containers are lightweight and share the host OS kernel, whereas VMs include a full OS, making them more resource-intensive.

---

