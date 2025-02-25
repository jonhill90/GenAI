# 🚀 LangFlow - Docker Compose Setup

This repository provides a **Docker Compose** configuration to run **LangFlow**, a visual programming interface for building LLM applications.

## 📌 Overview

This setup includes:
- **LangFlow**: A web-based interface for designing AI-powered applications.
- **Persistent Storage**: Data is stored in `./langflow_data`.

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
cd langflow-sandbox
```

### 3️⃣ Start the Container

```bash
docker-compose up -d
```

This will start **LangFlow**, which will be accessible at:

🔗 **LangFlow UI**: [http://localhost:7860](http://localhost:7860)

## 🛠 Configuration

Modify **`docker-compose.yml`** if needed:

- **Change API Port**: Modify `LANGFLOW_PORT=7860` in the environment variables.
- **Persistent Storage**: The `./langflow_data` directory stores LangFlow data.

## 🔧 Stopping and Restarting

To stop the LangFlow container:

```bash
docker-compose down
```

To restart:

```bash
docker-compose up -d
```

## 🏗️ Managing Data

- **Persistent Storage**: LangFlow data is stored in `./langflow_data`.

## 🧐 Troubleshooting

### ❓ Check Container Logs

```bash
docker-compose logs -f langflow
```

### ❓ Restart LangFlow

```bash
docker-compose restart langflow
```

### ❓ Verify Running Containers

```bash
docker ps
```