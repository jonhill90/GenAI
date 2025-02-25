# 🚀 LangFlow + Milvus + Ollama - Docker Compose Setup

This repository provides a **Docker Compose** configuration to run **LangFlow**, **Milvus**, and **Ollama** together, enabling AI-powered applications with vector search capabilities.

## 📌 Overview

This setup includes:
- **Ollama**: A local LLM engine (connected via `OLLAMA_API_BASE`).
- **LangFlow**: A visual programming interface for building LLM applications.
- **Milvus**: A vector database for similarity search.
- **ETCD**: Metadata store for Milvus.
- **MinIO**: Object storage for Milvus.

## 🛠 Installation Guide

### 1️⃣ Install Ollama

Ollama must be installed and running on your local machine.  
Download and install Ollama from [https://ollama.com](https://ollama.com).  
After installation, verify that Ollama is running:

```bash
ollama run deepseek
```

### 2️⃣ Install Docker & Docker Compose

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

### 3️⃣ Clone this Repository

```bash
git clone https://github.com/jonhill90/GenAI.git
cd langflow-sandbox
```

### 4️⃣ Start the Containers

```bash
docker-compose up -d
```

This will start:
- **LangFlow** at [http://localhost:7860](http://localhost:7860)
- **Milvus** at `localhost:19530`
- **MinIO Console** at [http://localhost:9001](http://localhost:9001)
- **Ollama API** assumed to be running at `http://host.docker.internal:11434`

## 🛠 Configuration

Modify **`docker-compose.yml`** if needed:

- **LangFlow API Port:** Change `LANGFLOW_PORT=7860` if needed.
- **Ollama API Connection:** Ensure `OLLAMA_API_BASE=http://host.docker.internal:11434` points to your Ollama instance.
- **Milvus Storage:** Adjust MinIO and ETCD storage locations.

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

- **Persistent Storage**: Data is stored in `./volumes` directory.
- **Accessing MinIO**:  
  - URL: [http://localhost:9001](http://localhost:9001)  
  - User: `minioadmin`  
  - Password: `minioadmin`

## 🧐 Troubleshooting

### ❓ Check Container Logs

```bash
docker-compose logs -f langflow
```

### ❓ Restart a Specific Container

```bash
docker-compose restart langflow
```

### ❓ Verify Running Containers

```bash
docker ps
```