🚀 DevOps Internship Assignment – Nginx Reverse Proxy + Docker
This project sets up a Docker Compose-based microservice system with an Nginx reverse proxy routing traffic to two backend services: a Golang app and a Python app.

📁 Project Structure
css
Copy code
.
├── docker-compose.yml
├── nginx
│   ├── nginx.conf
│   └── Dockerfile
├── service_1
│   ├── Dockerfile
│   └── main.go
├── service_2
│   ├── Dockerfile
│   └── app.py
└── README.md
⚙️ Setup Instructions
Clone this repository

bash
Copy code
git clone https://github.com/ayushyarrr/devops-nginx-docker.git
cd devops-nginx-docker
Build and start the system

bash
Copy code
docker compose up --build
Wait for services to become healthy
Check with:

bash
Copy code
docker ps
You should see both services marked as healthy.

Access services via Nginx reverse proxy:

http://localhost:8080/service1/hello → Golang Service

http://localhost:8080/service2/ping → Python Service

Stop everything

bash
Copy code
docker compose down
🔁 Routing via Nginx
The Nginx container acts as a reverse proxy, routing:

/service1/ → service_1 (Go app on port 8001)

/service2/ → service_2 (Python app on port 8002)

Logs each request with timestamp and request path using custom Nginx access.log.

✅ Features
🐳 Fully containerized setup using Docker Compose

🌐 Nginx reverse proxy with URL-based routing

💖 Health checks for both services

📜 Request logging (timestamp + path)

🧪 One-command startup: docker compose up --build

✨ Bonus
Health checks implemented via /hello and /ping endpoints

Nginx logs all incoming requests in custom format

🧠 Notes
Nginx runs inside a Docker container (not host)

Uses bridge networking only (no host networking)

Tested on Docker Desktop (Linux containers)

