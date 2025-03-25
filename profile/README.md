# MarketCircleAPI Docker Setup

This project provides a Dockerized version of the **MarketCircle API**. It is designed to simplify deployment and ensure consistency across different environments.

## Prerequisites

Before using the Docker image, ensure you have the following:

- Docker installed on your machine. If not, follow the [official Docker installation guide](https://docs.docker.com/get-docker/).
- An active GitHub account (for pulling from GitHub Container Registry).

## Getting Started

### 1. **Pull the Docker Image**

You can pull the Docker image directly from GitHub Container Registry using the following command:

```bash
docker pull ghcr.io/marketcircleproject/marketcircleapi:main
```

### 2. **Run the Docker Image**

After pulling the image, you can run it with the following command:

```bash
docker run -d --name marketcircleapi-container -p 8080:80 ghcr.io/marketcircleproject/marketcircleapi:main
```

### 3. **Platform Mismatch Issue**

If you're encountering the following error due to a platform mismatch:

```bash
The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8)
```

you can run this command by specifying the platform
```bash
docker run --platform linux/amd64 -d --name marketcircleapi-container -p 8080:80 ghcr.io/marketcircleproject/marketcircleapi:main
```

### 4. **Composer Install**
After running the docer image, you open the docker app, click on the container and select the 'Exec' tab, then type the command below and press enter, once it's done running restart the docker container
```bash
composer install
```

### 5. **Access API**
You should be able to access the api Using the base url below
```bash
http://localhost:8080
```

## **Remove the Local Image**

You can delete the local image using the  image name & tag
```bash
docker rmi ghcr.io/marketcircleproject/marketcircleapi:main
```
