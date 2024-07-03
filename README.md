# Docker

## What is Docker?
Docker is a platform for developing, shipping, and running applications inside containers. Containers are lightweight, portable, and self-sufficient units that package an application and all its dependencies, ensuring that it runs consistently in any environment.

## Key Concepts
### Image: 
A lightweight, stand-alone, and executable software package that includes everything needed to run a piece of software, including the code, runtime, libraries, environment variables, and configuration files.
### Container:
A runnable instance of an image. Containers are isolated from each other and the host system.
### Dockerfile:
A text file with instructions on how to build a Docker image.

### Docker Hub:
A cloud-based registry service where Docker images are stored and shared.

### Installation
To install Docker, follow the official Docker installation guide for your operating system: Docker Installation

## Basic Docker Commands
docker version: Check the Docker version installed.

```
docker version
```

docker pull: Download an image from Docker Hub.

```

docker pull ubuntu

```

docker images: List all images on your local system.

```

docker images

```
docker run: Run a container from an image.

```

docker run ubuntu

```
docker ps: List running containers.

```
docker ps

```
docker ps -a: List all containers, including stopped ones.

```
docker ps -a

```
docker stop: Stop a running container.

```
docker stop <container_id>

```

docker rm: Remove a stopped container.


```

docker rm <container_id>

```
docker rmi: Remove an image.

```
docker rmi <image_id>

```

# Writing a Dockerfile
A Dockerfile is a text file that contains a series of instructions on how to build a Docker image.

## Example Dockerfile for a simple Python application:

```
# Use the official Python image from the Docker Hub
FROM python:3.8-slim-buster

# Set the working directory in the container
WORKDIR /app

# Copy the requirements.txt file to the working directory
COPY requirements.txt .

# Install any dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code to the working directory
COPY . .

# Specify the command to run the application
CMD ["python", "app.py"]


```

