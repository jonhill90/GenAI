# 🚀 n8n - Docker Compose Setup

This repository provides a **Docker Compose** configuration to run **n8n**, an automation tool for integrating various services and automating workflows.

## 📌 Overview

This setup includes:
- **n8n**: A workflow automation tool.
- **Basic Authentication**: Secured access with username and password.
- **Persistent Storage**: Keeps your workflow data saved across restarts.

## 🛠 Installation Guide

### 1️⃣ Install Docker & Docker Compose

If you haven't already, install Docker:

- **Mac**:  
  ```bash
  brew install --cask docker
  ```
  Then, open Docker Desktop and ensure it is running.

- **Linux**: Follow the official [Docker installation guide](https://docs.docker.com/get-docker/).

- **Windows**: Download and install [Docker Desktop](https://www.docker.com/products/docker-desktop/).

To verify installation:
```bash
docker --version
docker-compose --version
```

### 2️⃣ Clone this Repository

```bash
git clone https://github.com/jonhill90/GenAI.git
cd n8n-sandbox
```

### 3️⃣ Start the Containers

```bash
docker-compose up -d
```

This will start:
- **n8n** at [http://localhost:5678](http://localhost:5678) (requires authentication)

## 🔑 Accessing n8n

By default, **basic authentication** is enabled for `n8n`.  
Login using the credentials set in `docker-compose.yml`:

- **Username**: `admin`
- **Password**: `securepassword` (change this in `docker-compose.yml`)

## 🛠 Configuration

Modify **`docker-compose.yml`** if needed:

- **n8n API Port:** Change `N8N_PORT=5678` if needed.
- **Authentication:** Update `N8N_BASIC_AUTH_USER` and `N8N_BASIC_AUTH_PASSWORD`.
- **Persistent Storage:** Data is stored in `./n8n_data/`.

## 🔧 Stopping and Restarting

To stop all containers:

```bash
docker-compose down
```

To restart:

```bash
docker-compose up -d
```

## 🏗️ Managing Data

- **Persistent Storage**: Data is stored in `./n8n_data/`.
- **Change Authentication**: Modify `N8N_BASIC_AUTH_*` in `docker-compose.yml`.

## 🧐 Troubleshooting

### ❓ Check Container Logs

```bash
docker-compose logs -f n8n
```

### ❓ Restart a Specific Container

```bash
docker-compose restart n8n
```

### ❓ Verify Running Containers

```bash
docker ps
```