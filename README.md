# 🚀 DevOps Internship Assignment – Nginx Reverse Proxy + Docker

This project sets up a Docker Compose-based microservice system with an Nginx reverse proxy routing traffic to two backend services: a Golang app and a Python app.

## 📁 Project Structure

├── docker-compose.yml
├── nginx
│ ├── nginx.conf
│ └── Dockerfile
├── service_1
│ ├── .dockerignore
│ ├── Dockerfile
│ ├── main.go
│ └── README.md
├── service_2
│ ├── .dockerignore
│ ├── .python-version
│ ├── Dockerfile
│ ├── README.md
│ ├── app.py
│ ├── pyproject.toml
│ ├── uv.lock
│ └── .venv/
└── README.md


## ⚙️ Setup Instructions

1. Clone this repository

```bash
git clone https://github.com/ayushyarrr/devops-nginx-docker.git
cd devops-nginx-docker
```
2. Build and start the system
```bash
docker compose up --build
```
3. Wait for the services to become healthy (check with:)
```bash
docker ps
```
***You should see both services marked as healthy.

4. Access services via Nginx reverse proxy:

Golang Service:
http://localhost:8080/service1/hello

Python Service:
http://localhost:8080/service2/ping

5. To stop everything:

```bash
docker compose down
```


🔁 Routing via Nginx
The Nginx container acts as a reverse proxy, routing requests:

/service1/ → service_1 (Go app on port 8001)

/service2/ → service_2 (Python app on port 8002)

It also logs each request with timestamp and request path using a custom Nginx access.log format.


✅ Features
🐳 Fully containerized setup using Docker Compose

🌐 Nginx reverse proxy with URL-based routing

💖 Health checks for both services

📜 Request logging (timestamp + path)

🧪 One-command startup: docker compose up --build


✨ Bonus
Health checks implemented via /hello and /ping endpoints

Nginx logs all incoming requests in a custom format


🧠 Notes
Nginx runs inside a Docker container (not on the host)

Uses bridge networking only (no host networking)

Tested on Docker Desktop (Linux containers)



