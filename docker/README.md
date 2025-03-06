# Docker Guide

## Introduction

This guide covers the basics of Docker, including Docker images, Dockerfiles, Docker Compose, Multi-stage builds, Docker Volumes, and Docker Port Mapping. If you're new to Docker, this is a good starting point!

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

## 📂 Docker Volumes

Docker Volumes allow data to persist across container restarts and enable sharing data between containers.

### Create and Use a Volume:
```sh
# Create a volume
docker volume create my_volume

# Run a container with a volume
docker run -v my_volume:/data ubuntu
```

### List and Remove Volumes:
```sh
# List all volumes
docker volume ls

# Remove a volume
docker volume rm my_volume
```

---

## 🔌 Docker Port Mapping

Docker allows you to map ports from the container to the host machine, enabling external access to services.

### Example:
```sh
# Run a container with port mapping
docker run -p 8080:80 nginx
```

### Explanation:
- `-p 8080:80` maps port `80` inside the container to port `8080` on the host machine.
- You can now access the Nginx server on `http://localhost:8080`.

---

## 🚀 Conclusion

Docker simplifies the deployment of applications by packaging everything needed into containers. Mastering Docker images, Dockerfiles, Compose, Multi-stage builds, Volumes, and Port Mapping will improve your workflow and efficiency. Happy coding! 🎉
