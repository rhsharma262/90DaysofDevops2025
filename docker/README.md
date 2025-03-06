# Docker Guide

## Table of Contents
- [Introduction to Docker](#introduction-to-docker)
- [Docker Images](#docker-images)
- [Dockerfile](#dockerfile)
- [Docker Compose](#docker-compose)
- [Multi-Stage Builds](#multi-stage-builds)
- [Useful Commands](#useful-commands)

---

## Introduction to Docker
Docker is a platform that enables developers to build, ship, and run applications in isolated environments called containers. It ensures consistency across different environments and simplifies application deployment.

### Key Features:
- Lightweight and portable containers
- Fast deployment and scaling
- Isolation of applications and dependencies

---

## Docker Images
A Docker image is a lightweight, standalone, and executable software package that includes everything needed to run an application: code, runtime, libraries, and dependencies.

### Managing Images:
```sh
# List available images
docker images

# Pull an image from Docker Hub
docker pull <image_name>

# Remove an image
docker rmi <image_id>
```

---

## Dockerfile
A Dockerfile is a script containing a set of instructions to build a Docker image.

### Example Dockerfile:
```dockerfile
# Use an official base image
FROM node:16

# Set the working directory
WORKDIR /app

# Copy application files
COPY package.json .
COPY . .

# Install dependencies
RUN npm install

# Expose application port
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
```

### Building an Image:
```sh
docker build -t myapp .
```

### Running a Container:
```sh
docker run -p 3000:3000 myapp
```

---

## Docker Compose
Docker Compose is a tool for defining and running multi-container Docker applications using a YAML file.

### Example `docker-compose.yml`:
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  app:
    build: .
    depends_on:
      - db
  db:
    image: postgres
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
```

### Running the Application:
```sh
docker-compose up -d
```

---

## Multi-Stage Builds
Multi-stage builds help create smaller, optimized Docker images by using multiple `FROM` statements.

### Example Multi-Stage Dockerfile:
```dockerfile
# Build stage
FROM node:16 as builder
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

# Production stage
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
```

This reduces the final image size by eliminating unnecessary dependencies.

---

## Useful Commands
```sh
# List running containers
docker ps

# Stop a container
docker stop <container_id>

# Remove a container
docker rm <container_id>

# Remove all stopped containers
docker container prune
```

---

## Conclusion
This guide covers the basics of Docker, Docker images, Dockerfile, Docker Compose, and Multi-Stage Builds. Understanding these concepts will help you deploy and manage containerized applications effectively.

For more details, visit [Docker Documentation](https://docs.docker.com/).
