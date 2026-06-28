# Flask + Nginx with Docker Compose

A simple Flask application served behind an Nginx reverse proxy, containerized with Docker Compose.

## How it works

```
User → Nginx (:8080) → Flask (:5000)
```

- **Nginx** listens on port 8080 and forwards traffic to the Flask container
- **Flask** runs on port 5000, not exposed directly to the outside

## Project Structure

```
docker_compose/
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── nginx/
│   └── default.conf
└── docker-compose.yml
```

## Requirements

- Docker
- Docker Compose

## Getting Started

1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

2. Build and start the containers

```bash
docker compose -p myapp up --build -d
```

3. Open your browser and go to `http://localhost:8080`

## Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Returns a welcome JSON message |
| `/health` | GET | Health check |

## Stopping the app

```bash
docker compose -p myapp down
```
