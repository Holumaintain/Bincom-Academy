# Bincom Academy

A full-stack web application with a production-style monitoring and observability stack built with **Next.js, Docker, Prometheus, Grafana, Node Exporter, and Alertmanager**.

The project demonstrates how a modern web application can be containerized, monitored, and visualized using an open-source observability stack.

---

## 📌 Project Overview

**Bincom Academy** is a web application project developed with a focus on modern web development, containerization, infrastructure monitoring, and application observability.

The project includes a dedicated monitoring stack that collects application and infrastructure metrics and presents them through Grafana dashboards.

The monitoring environment provides visibility into:

* Application availability
* HTTP request traffic
* Request duration
* Endpoint activity
* CPU utilization
* Memory usage
* System load
* Disk activity
* Service health
* Application uptime
* Prometheus target status

---

## 🚀 Key Features

### Application

* Next.js web application
* Responsive frontend
* Production-oriented application configuration
* Custom application metrics endpoint
* Dockerized application deployment

### Monitoring & Observability

* Prometheus metrics collection
* Grafana dashboards
* Node Exporter infrastructure metrics
* Alertmanager integration
* Application HTTP metrics
* Application uptime monitoring
* Endpoint-level request monitoring
* Request duration monitoring
* Infrastructure resource monitoring
* Prometheus target health monitoring

### DevOps

* Docker and Docker Compose
* Multi-container development environment
* Production-style container configuration
* Health monitoring
* Metrics collection
* Centralized observability dashboard

---

## 🏗️ Architecture

The project uses Docker Compose to run the application and monitoring services together.

```text
                         ┌─────────────────────┐
                         │     Web Browser      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Bincom Academy    │
                         │      Next.js        │
                         │      :3006          │
                         └──────────┬──────────┘
                                    │
                              Application
                                Metrics
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │     Prometheus      │
                         │       :9091         │
                         └──────────┬──────────┘
                                    │
                          ┌─────────┴─────────┐
                          │                   │
                          ▼                   ▼
                 ┌────────────────┐   ┌────────────────┐
                 │    Grafana     │   │  Alertmanager  │
                 │     :3001      │   │     :9093      │
                 └────────────────┘   └────────────────┘
                          ▲
                          │
                          │
                 ┌────────┴────────┐
                 │  Node Exporter  │
                 │      :9100      │
                 └─────────────────┘
```

---

## 🛠️ Technology Stack

### Frontend / Application

* Next.js
* React
* TypeScript
* JavaScript
* HTML
* CSS

### Monitoring

* Prometheus
* Grafana
* Node Exporter
* Alertmanager

### DevOps / Infrastructure

* Docker
* Docker Compose
* Linux
* Windows / WSL development environment
* Git
* GitHub

---

## 📂 Project Structure

```text
Bincom-Academy/
│
├── frontend-app/
│   │
│   ├── app/
│   │   └── Application routes and pages
│   │
│   ├── monitoring/
│   │   └── Monitoring-related configuration
│   │
│   ├── public/
│   │   └── Static assets
│   │
│   ├── src/
│   │   └── Application source code
│   │
│   ├── next.config.ts
│   ├── package.json
│   ├── Dockerfile
│   └── ...
│
├── docker-compose.yml
├── .gitignore
└── README.md
```

> The exact structure may vary as the project evolves.

---

# 📊 Monitoring Stack

The monitoring environment consists of four primary observability components.

## Prometheus

Prometheus collects and stores time-series metrics from the application and infrastructure.

It monitors targets such as:

* Bincom Academy application
* Node Exporter
* Prometheus itself

Example application metrics include:

```text
http_requests_total
app_uptime_seconds
```

Prometheus is exposed locally through:

```text
http://localhost:9091
```

---

## Grafana

Grafana provides dashboards for visualizing the metrics collected by Prometheus.

The project includes a dashboard named:

```text
Bincom-Academy Monitoring
```

The dashboard provides visibility into application and infrastructure performance.

### Dashboard Panels

The monitoring dashboard includes panels for:

* CPU Utilization
* Available Memory
* Available Memory Percentage
* Load Average
* Disk Read Rate
* HTTP Request Rate
* Total HTTP Requests
* Average Request Duration
* Requests by Endpoint
* Service Status

Grafana is exposed locally through:

```text
http://localhost:3001
```

---

## Node Exporter

Node Exporter collects infrastructure-level metrics from the host environment.

The metrics can be used to monitor:

* CPU usage
* Memory utilization
* System load
* Disk activity
* Other operating-system-level statistics

Node Exporter runs on:

```text
http://localhost:9100
```

---

## Alertmanager

Alertmanager is included as part of the observability stack and is responsible for handling alerts generated by Prometheus.

It can be extended to support notification integrations such as:

* Email
* Slack
* Microsoft Teams
* Webhooks
* Other supported notification channels

Alertmanager is exposed locally through:

```text
http://localhost:9093
```

---

# 🐳 Docker Services

The project uses Docker Compose to run the application and observability services.

| Service             | Purpose               |   Port |
| ------------------- | --------------------- | -----: |
| Next.js Application | Web application       | `3006` |
| Prometheus          | Metrics collection    | `9091` |
| Grafana             | Metrics visualization | `3001` |
| Node Exporter       | Host metrics          | `9100` |
| Alertmanager        | Alert management      | `9093` |

---

# ⚙️ Prerequisites

Before running the project, make sure you have the following installed:

* Git
* Node.js
* npm
* Docker Desktop
* Docker Compose

Recommended:

* Node.js 20+
* Docker Desktop with WSL 2 enabled on Windows

Verify your installations:

```bash
node --version
npm --version
docker --version
docker compose version
git --version
```

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/Holumaintain/Bincom-Academy.git
```

Move into the project:

```bash
cd Bincom-Academy
```

Then enter the application directory:

```bash
cd frontend-app
```

---

# 💻 Running the Application Locally

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The application will normally be available at:

```text
http://localhost:3000
```

---

# 🐳 Running with Docker

From the project directory, start the complete environment with:

```bash
docker compose up -d --build
```

Check running containers:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs -f
```

View logs for a specific service:

```bash
docker compose logs -f nextjs-metrics
```

---

# 📈 Accessing the Monitoring Services

Once the Docker services are running, the following interfaces are available.

### Bincom Academy

```text
http://localhost:3006
```

### Prometheus

```text
http://localhost:9091
```

### Grafana

```text
http://localhost:3001
```

### Alertmanager

```text
http://localhost:9093
```

### Node Exporter

```text
http://localhost:9100
```

---

# 🔍 Application Metrics

The application exposes metrics that can be scraped by Prometheus.

Examples include:

```text
http_requests_total
```

Tracks the total number of HTTP requests handled by the application.

```text
app_uptime_seconds
```

Tracks the application uptime in seconds.

These metrics allow Prometheus to collect application-level performance data and make it available for visualization in Grafana.

---

# 📊 Prometheus Targets

The Prometheus environment monitors multiple targets.

Typical targets include:

```text
Bincom Academy
Node Exporter
Prometheus
```

A healthy monitoring environment should show the targets as:

```text
UP
```

You can inspect the targets from the Prometheus interface.

---

# 📉 Grafana Dashboard

The project includes a dedicated Grafana monitoring dashboard:

```text
Bincom-Academy Monitoring
```

The dashboard combines application and infrastructure metrics into a single monitoring interface.

Example monitoring categories:

```text
Application
├── HTTP Request Rate
├── Total Requests
├── Request Duration
├── Requests by Endpoint
└── Application Status

Infrastructure
├── CPU Utilization
├── Memory Usage
├── Load Average
└── Disk Activity

Monitoring
├── Prometheus Target Status
└── Service Health
```

---

# 🔄 Monitoring Flow

The monitoring workflow can be summarized as:

```text
Application
     │
     │ exposes metrics
     ▼
Prometheus
     │
     │ stores time-series data
     ▼
Grafana
     │
     │ visualizes metrics
     ▼
Monitoring Dashboard
```

Infrastructure metrics follow a similar flow:

```text
Host System
     │
     ▼
Node Exporter
     │
     ▼
Prometheus
     │
     ▼
Grafana
```

Alerting can be integrated through:

```text
Prometheus
     │
     │ alerts
     ▼
Alertmanager
     │
     ▼
Notification Channels
```

---

# 🧪 Health Checks & Verification

After starting the environment, verify the containers:

```bash
docker compose ps
```

Check application logs:

```bash
docker compose logs nextjs-metrics
```

Check Prometheus logs:

```bash
docker compose logs prometheus
```

Check Grafana logs:

```bash
docker compose logs grafana
```

Check Node Exporter:

```bash
docker compose logs node-exporter
```

Check Alertmanager:

```bash
docker compose logs alertmanager
```

---

# 🛑 Stopping the Environment

To stop the containers:

```bash
docker compose down
```

To stop the containers and remove associated volumes:

```bash
docker compose down -v
```

> Use `-v` carefully because it removes Docker volumes and can delete persistent monitoring data.

---

# 🔄 Rebuilding the Environment

If you make changes to the application or Docker configuration:

```bash
docker compose down
```

Then rebuild:

```bash
docker compose up -d --build
```

Check the environment:

```bash
docker compose ps
```

---

# 🔐 Environment Variables

Sensitive configuration should not be committed to GitHub.

Use environment files for local configuration:

```text
.env
.env.local
.env.production
```

These files are excluded through `.gitignore`.

For collaborators, provide an example configuration such as:

```text
.env.example
```

without including real secrets.

---

# 🔒 Security Considerations

This project is intended for development, learning, and portfolio demonstration.

Before deploying the application publicly:

* Protect Grafana with secure credentials.
* Protect Prometheus where necessary.
* Avoid exposing internal monitoring endpoints unnecessarily.
* Store secrets outside source control.
* Use HTTPS in production.
* Configure appropriate firewall rules.
* Restrict access to monitoring services.
* Configure secure authentication.
* Review Docker container permissions.
* Keep dependencies updated.

Never commit:

```text
API keys
Passwords
Database credentials
Cloud credentials
Private tokens
Production secrets
```

---

# ☁️ Production Considerations

For a production deployment, the project can be extended with:

* AWS deployment
* Terraform infrastructure
* Kubernetes
* AWS ECS
* Amazon EKS
* Application Load Balancer
* CloudWatch integration
* Managed databases
* HTTPS/TLS
* Domain configuration
* CI/CD pipelines
* Automated testing
* Automated Docker image builds
* Container registry integration

---

# 🔮 Future Improvements

Planned improvements can include:

* [ ] Add comprehensive application test coverage
* [ ] Add automated CI/CD with GitHub Actions
* [ ] Add Prometheus alert rules
* [ ] Configure Alertmanager notifications
* [ ] Add additional Grafana dashboards
* [ ] Add database monitoring
* [ ] Add application error-rate metrics
* [ ] Add latency percentile metrics
* [ ] Add Docker image optimization
* [ ] Add security scanning
* [ ] Add container vulnerability scanning
* [ ] Deploy to AWS
* [ ] Provision infrastructure with Terraform
* [ ] Explore Kubernetes deployment
* [ ] Add centralized logging
* [ ] Add distributed tracing

---

# 🧰 Useful Docker Commands

### View containers

```bash
docker compose ps
```

### Start services

```bash
docker compose up -d
```

### Build and start

```bash
docker compose up -d --build
```

### Stop services

```bash
docker compose down
```

### View logs

```bash
docker compose logs -f
```

### View a specific service

```bash
docker compose logs -f prometheus
```

### Restart a service

```bash
docker compose restart grafana
```

### Inspect Docker images

```bash
docker images
```

### Inspect running containers

```bash
docker ps
```

---

# 🧑‍💻 Development Workflow

A typical development workflow for this project is:

```text
Code
 │
 ▼
Git
 │
 ▼
GitHub
 │
 ▼
Docker Build
 │
 ▼
Docker Compose
 │
 ├───────────────┐
 ▼               ▼
Application    Monitoring
 │               │
 ▼               ▼
Metrics       Prometheus
 │               │
 └───────┬───────┘
         ▼
      Grafana
         │
         ▼
   Observability
```

---

# 📚 Learning Objectives

This project demonstrates practical experience with:

* Next.js application development
* TypeScript
* Docker containerization
* Docker Compose
* Application instrumentation
* Prometheus metrics
* Grafana dashboards
* Node Exporter
* Alertmanager
* Infrastructure monitoring
* Application observability
* Containerized development
* Git and GitHub
* DevOps practices

---

# 👨‍💻 Author

**Oshifeko Olumide Clement**

Software Engineer | Full-Stack Developer | DevOps Engineer

GitHub: [@Holumaintain](https://github.com/Holumaintain)

---

# 📄 License

This project is intended for educational, development, and portfolio purposes.

Add a specific open-source license here if you decide to distribute the project under one.
