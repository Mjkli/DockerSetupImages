# Docker Setup Images

This repository contains a small set of Alpine-based Docker images used for common infrastructure and frontend tooling.

The images are published to Docker Hub here:
https://hub.docker.com/repositories/mjkli

## Repository structure

- `containers/packer/` – image with Packer, AWS CLI, and supporting build tooling
- `containers/react-vite/` – image with Node.js and Vite for frontend development
- `containers/terraform/` – image with Terraform, AWS CLI, and supporting build tooling

## Included images

### 1. Packer image
Location: `containers/packer/Dockerfile`

Includes:
- Alpine Linux
- Packer 1.9.2
- Python 3, pip, build dependencies
- AWS CLI
- Docker, make, and OpenRC support tools

### 2. React + Vite image
Location: `containers/react-vite/Dockerfile`

Includes:
- Alpine Linux
- Node.js current
- npm
- Vite globally installed

### 3. Terraform image
Location: `containers/terraform/Dockerfile`

Includes:
- Alpine Linux
- Terraform 1.5.4
- Python 3, pip, build dependencies
- AWS CLI
- Docker, make, and OpenRC support tools

## Build images locally

From the repository root, run:

```bash
docker build -t mjkli/packer:1.9.2 ./containers/packer
docker build -t mjkli/react-vite:latest ./containers/react-vite
docker build -t mjkli/terraform:1.5.4 ./containers/terraform
```

## Push to Docker Hub

```bash
docker login
docker push mjkli/packer:1.9.2
docker push mjkli/react-vite:latest
docker push mjkli/terraform:1.5.4
```

## Example usage

### Packer

```bash
docker run --rm -it mjkli/packer:1.9.2 packer --version
```

### Terraform

```bash
docker run --rm -it mjkli/terraform:1.5.4 terraform --version
```

### Vite app

```bash
docker run --rm -it -p 5173:5173 -v $(pwd):/app mjkli/react-vite:latest sh -lc "cd /app && npm install && npm run dev -- --host 0.0.0.0"
```

## Notes

These images are intentionally lightweight and built on Alpine for portability and quick startup. They are useful for CI/CD workflows, local development environments, and infrastructure automation tasks.

