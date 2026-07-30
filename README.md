# Optimus - Local Infrastructure (`infra`)

This folder manages core third-party developer dependency services (LiveKit WebRTC, MongoDB, and local DynamoDB) used by the Optimus application suite, packaged entirely inside Docker container environments.

---

## 🏗 Directory & Work Structure

```text
infra/
├── data/                     # Persistent local database volumes
│   └── dynamodb/             # DynamoDB local database file storage
├── compose.auth-api.yml      # Service definitions for the auth-api container
├── compose.meet.yml          # Service definitions for the Next.js meet container
└── docker-compose.yml        # Orchestration definitions for core MongoDB, DynamoDB, and LiveKit services
```

---

## 🚀 Running Infrastructure (Mac & Linux)

### 📋 Prerequisites
- **Docker**: Docker Desktop (Mac) or Docker Engine & Compose plugin (Linux) installed and running.

---

### 💻 Starting Services

#### 1. Launch Infrastructure
Start the core LiveKit server, MongoDB database, and DynamoDB database:
```bash
docker compose up -d
```

#### 2. Confirm Container Health
Check if all database and WebRTC services are successfully running:
```bash
docker compose ps
```
Expected output:
- `optimus-livekit` (Running, healthy)
- `optimus-mongo` (Running, healthy)
- `optimus-dynamo` (Running, healthy)

#### 3. View Logs
To view realtime application logs for diagnosing setup or connection issues:
```bash
docker compose logs -f
```

#### 4. Stop Services
To shut down the local infrastructure container environment:
```bash
docker compose down
```
_Note: Local volumes inside `data/` are persisted._
