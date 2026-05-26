# 🚀 n8n — Complete Production-Level Guide

<p align="center">
  <img src="https://raw.githubusercontent.com/n8n-io/n8n/master/assets/n8n-logo.png" width="220" alt="n8n Logo"/>
</p>

<p align="center">
  <b>Automate workflows • Connect apps • Build AI Agents • Self-host with full control</b>
</p>

---

# 📌 Table of Contents

- [What is n8n?](#-what-is-n8n)
- [Why n8n?](#-why-n8n)
- [Core Features](#-core-features)
- [Benefits of Using n8n](#-benefits-of-using-n8n)
- [Real-World Use Cases](#-real-world-use-cases)
- [How n8n Works](#-how-n8n-works)
- [Architecture Overview](#-architecture-overview)
- [Prerequisites](#-prerequisites)
- [Installing Docker](#-installing-docker)
- [Running n8n Locally Using Docker](#-running-n8n-locally-using-docker)
- [Docker Commands Explained](#-docker-commands-explained)
- [Persistent Data Storage](#-persistent-data-storage)
- [Using Docker Compose](#-using-docker-compose)
- [Environment Variables](#-environment-variables)
- [Updating n8n](#-updating-n8n)
- [Stopping & Removing Containers](#-stopping--removing-containers)
- [Common Issues & Fixes](#-common-issues--fixes)
- [Security Best Practices](#-security-best-practices)
- [Useful Integrations](#-useful-integrations)
- [Learning Resources](#-learning-resources)
- [Conclusion](#-conclusion)

---

# 📖 What is n8n?

**n8n** (pronounced *“n-eight-n”*) is an open-source workflow automation platform that allows developers, businesses, and teams to automate repetitive tasks by connecting different applications and services together.

It works similarly to tools like:

- Zapier
- Make (Integromat)
- Pipedream

But unlike many no-code automation tools, n8n provides:

✅ Self-hosting  
✅ Full data control  
✅ Custom coding support  
✅ AI integrations  
✅ Advanced workflow logic  
✅ Unlimited automation flexibility

---

# 🎯 Why n8n?

Modern businesses use dozens of apps daily:

- Gmail
- Slack
- Notion
- Google Sheets
- CRMs
- APIs
- Databases
- AI tools

Managing data manually between these systems wastes time and increases errors.

n8n solves this problem by automating workflows visually.
# 📖 Example Workflow

n8n solves this problem by automating workflows visually.

Example:

```text
New Form Submission
        ↓
Store in Database
        ↓
Send Slack Notification
        ↓
Generate AI Summary
        ↓
Send Email Reply
```

---

# ⚡ Core Features

## 🔹 Visual Workflow Builder

Drag-and-drop workflow creation with minimal coding.

---

## 🔹 400+ Integrations

Supports apps like:

- Google Sheets
- Slack
- Telegram
- GitHub
- Discord
- OpenAI
- MySQL
- PostgreSQL
- MongoDB
- Airtable

---

## 🔹 AI & Agentic Automation

Integrate with:

- OpenAI
- Anthropic
- LangChain
- Vector Databases
- AI Agents

---

## 🔹 Self Hosting

Host on:

- Local machine
- VPS
- AWS
- Azure
- GCP
- Docker
- Kubernetes

---

## 🔹 Custom JavaScript Logic

Add advanced logic directly inside workflows.

---

## 🔹 Webhooks & APIs

Trigger workflows from external systems instantly.

---

# ✅ Benefits of Using n8n

| Benefit | Description |
|---|---|
| Open Source | Full transparency and customization |
| Cost Effective | Avoid expensive automation platforms |
| Self Hosted | Complete data privacy and control |
| Scalable | Suitable for startups to enterprises |
| Developer Friendly | Supports custom code and APIs |
| AI Ready | Easily build AI workflows and agents |
| Time Saving | Automates repetitive manual tasks |
| Fast Integration | Connect multiple systems quickly |

---

# 💡 Real-World Use Cases

## 📩 Email Automation

- Auto replies
- Lead nurturing
- Invoice reminders

---

## 🤖 AI Automation

- AI resume screening
- AI customer support
- AI content generation
- AI agents

---

## 📊 Data Processing

- Sync Excel/Sheets data
- Database automation
- ETL pipelines

---

## 🔔 Notifications

- Slack alerts
- Discord notifications
- Telegram bots

---

## 🧾 Invoice Management

- Extract invoice data
- Send payment reminders
- Store records automatically

---

## 🧠 Recruitment Automation

- Resume parsing
- Candidate ranking
- HR notifications

---

# ⚙️ How n8n Works

n8n workflows consist of:

| Component | Description |
|---|---|
| Trigger Node | Starts workflow |
| Action Node | Performs task |
| Logic Node | Conditions/loops |
| API Node | Connect external APIs |
| Database Node | Store/retrieve data |

---

# 🏗️ Architecture Overview

```text
                ┌─────────────────┐
                │  Trigger/Event  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │   n8n Workflow  │
                └────────┬────────┘
                         │
      ┌──────────────────┼──────────────────┐
      ▼                  ▼                  ▼
 ┌──────────┐      ┌──────────┐      ┌──────────┐
 │ Database │      │ APIs     │      │ AI Tools │
 └──────────┘      └──────────┘      └──────────┘
```

---

# 📋 Prerequisites

Before installing n8n locally:

## Required Software

- Docker
- Docker Compose (optional but recommended)

---

## Recommended System

| Requirement | Minimum |
|---|---|
| RAM | 4 GB |
| CPU | Dual Core |
| Storage | 10 GB |

---

# 🐳 Installing Docker

## 🪟 Windows Installation

### Step 1 — Download Docker Desktop

Visit:

```text
https://www.docker.com/products/docker-desktop/
```

---

### Step 2 — Install Docker Desktop

- Run installer
- Enable WSL2 when asked
- Restart system

---

### Step 3 — Verify Installation

Open terminal:

```bash
docker --version
```

Expected output:

```text
Docker version 27.x.x
```

Check Docker Compose:

```bash
docker compose version
```

---

# 🐧 Ubuntu/Linux Installation

### Update Packages

```bash
sudo apt update
```

---

### Install Docker

```bash
sudo apt install docker.io -y
```

---

### Start Docker

```bash
sudo systemctl start docker
```

---

### Enable Docker on Boot

```bash
sudo systemctl enable docker
```

---

### Verify Installation

```bash
docker --version
```


# 🚀 Running n8n Locally Using Docker

---

# Method 1 — Quick Start (Recommended for Beginners)

## Step 1 — Pull n8n Docker Image

```bash
docker pull n8nio/n8n
```

---

## Step 2 — Run n8n Container

```bash
docker run -it --rm \
-p 5678:5678 \
n8nio/n8n
```

---

## Step 3 — Open n8n

Open browser:

```text
http://localhost:5678
```

You should now see the n8n dashboard.

---

# 📦 Docker Command Breakdown

```bash
docker run -it --rm -p 5678:5678 n8nio/n8n
```

| Command | Meaning |
|---|---|
| `docker run` | Start container |
| `-it` | Interactive terminal |
| `--rm` | Remove container after stop |
| `-p 5678:5678` | Map local port |
| `n8nio/n8n` | Official n8n image |

---

# 💾 Persistent Data Storage

Without persistence, data is lost after container removal.

Use Docker volumes to persist workflows and credentials.

---

## Create Docker Volume

```bash
docker volume create n8n_data
```

---

## Run n8n with Persistent Storage

```bash
docker run -it --rm \
-p 5678:5678 \
-v n8n_data:/home/node/.n8n \
n8nio/n8n
```

---

# 📁 Local Folder Persistence

Instead of Docker volumes, you can directly map a local folder.

---

## 🪟 Windows

```bash
docker run -it --rm ^
-p 5678:5678 ^
-v C:\n8n-data:/home/node/.n8n ^
n8nio/n8n
```

---

## 🐧 Linux/Mac

```bash
docker run -it --rm \
-p 5678:5678 \
-v ~/.n8n:/home/node/.n8n \
n8nio/n8n
```

---

# 🧩 Using Docker Compose (Production Recommended)

Docker Compose makes container management easier and cleaner.

---

# 📂 Step 1 — Create Project Folder

```bash
mkdir n8n-docker
cd n8n-docker
```

---

# 📄 Step 2 — Create `docker-compose.yml`

```yaml
version: '3.8'

services:
  n8n:
    image: n8nio/n8n
    container_name: n8n

    ports:
      - "5678:5678"

    environment:
      - TZ=Asia/Kolkata
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=admin123

    volumes:
      - ./n8n_data:/home/node/.n8n

    restart: always
```

---

# ▶️ Step 3 — Start n8n

```bash
docker compose up -d
```

---

# 🔍 Step 4 — Verify Running Containers

```bash
docker ps
```

Expected output:

```text
CONTAINER ID   IMAGE         STATUS
xxxxxxxxxxxx   n8nio/n8n    Up
```

---

# 🌐 Step 5 — Open Browser

```text
http://localhost:5678
```

---

# 🔐 Login Credentials

```text
Username: admin
Password: admin123
```

---

# 🔑 Environment Variables

| Variable | Purpose |
|---|---|
| `TZ` | Timezone |
| `N8N_BASIC_AUTH_ACTIVE` | Enable login |
| `N8N_BASIC_AUTH_USER` | Username |
| `N8N_BASIC_AUTH_PASSWORD` | Password |
| `WEBHOOK_URL` | Public webhook URL |
| `N8N_HOST` | Hostname |
| `N8N_PORT` | Port |

---

# 📂 Understanding Docker Volumes

Docker volumes help preserve:

- Workflows
- Credentials
- Execution history
- User settings

Without volumes, all data is deleted when the container stops.

---

# 📌 Where Data Gets Stored

| Method | Storage Location |
|---|---|
| Docker Volume | Managed by Docker |
| Local Folder Mapping | Your local machine folder |

---

# 🛠️ Useful Docker Commands

## View Running Containers

```bash
docker ps
```

---

## View All Containers

```bash
docker ps -a
```

---

## View Docker Images

```bash
docker images
```

---

## View Container Logs

```bash
docker logs n8n
```

---

## Restart Container

```bash
docker restart n8n
```

---

## Enter Container Shell

```bash
docker exec -it n8n sh
```


# 🔄 Updating n8n

Keeping n8n updated ensures:

- Better performance
- Security patches
- Latest integrations
- New workflow features
- Bug fixes

---

# 📥 Pull Latest n8n Image

```bash
docker pull n8nio/n8n
```

---

# 🛑 Stop Existing Containers

If using Docker Compose:

```bash
docker compose down
```

If using normal Docker:

```bash
docker stop n8n
```

---

# 🚀 Restart with Latest Version

Using Docker Compose:

```bash
docker compose up -d
```

Using Docker:

```bash
docker run -it --rm \
-p 5678:5678 \
-v n8n_data:/home/node/.n8n \
n8nio/n8n
```

---

# 🛑 Stopping & Removing Containers

---

## Stop Running Container

```bash
docker stop n8n
```

---

## Remove Container

```bash
docker rm n8n
```

---

## Remove Docker Image

```bash
docker rmi n8nio/n8n
```

---

## Remove Docker Volume

⚠️ Warning: This permanently deletes workflows and credentials.

```bash
docker volume rm n8n_data
```

---

# 🧪 Common Issues & Fixes

---

# ❌ Port Already in Use

## Error

```text
Bind for 0.0.0.0:5678 failed
```

---

## Solution

Run n8n on another port:

```bash
docker run -it --rm \
-p 8080:5678 \
n8nio/n8n
```

Open:

```text
http://localhost:8080
```

---

# ❌ Docker Permission Denied (Linux)

## Error

```text
permission denied while trying to connect to Docker daemon
```

---

## Solution

```bash
sudo usermod -aG docker $USER
```

Restart terminal afterward.

---

# ❌ Container Keeps Restarting

## Check Logs

```bash
docker logs n8n
```

---

## Possible Reasons

- Wrong environment variables
- Port conflicts
- Corrupted volumes
- Missing permissions

---

# ❌ Cannot Access UI

## Verify Running Containers

```bash
docker ps
```

---

## Verify Port Mapping

Check if port `5678` is mapped correctly.

---

## Check Firewall

Allow incoming traffic on:

```text
5678
```

---

# ❌ Docker Compose Command Not Found

## Install Docker Compose

Ubuntu:

```bash
sudo apt install docker-compose-plugin
```

Verify:

```bash
docker compose version
```

---

# 🔒 Security Best Practices

Running n8n securely is extremely important in production.

---

# ✅ Always Enable Authentication

Never expose public n8n without login protection.

Example:

```yaml
environment:
  - N8N_BASIC_AUTH_ACTIVE=true
  - N8N_BASIC_AUTH_USER=admin
  - N8N_BASIC_AUTH_PASSWORD=strongpassword
```

---

# ✅ Use Strong Passwords

Avoid weak credentials like:

```text
admin123
password
123456
```

Use strong random passwords instead.

---

# ✅ Use HTTPS in Production

Recommended reverse proxies:

- Nginx
- Traefik
- Caddy
- Cloudflare Tunnel

---

# ✅ Backup Workflow Data

Backup folder:

```text
/home/node/.n8n
```

Important files include:

- Workflows
- Credentials
- Execution history
- User settings

---

# ✅ Use Environment Variables for Secrets

Avoid hardcoding:

- API Keys
- Database passwords
- Tokens
- Authentication secrets

Inside workflows.

---

# 🌍 Deploying n8n to Cloud

n8n can be deployed on:

| Platform | Supported |
|---|---|
| AWS | ✅ |
| Azure | ✅ |
| Google Cloud | ✅ |
| DigitalOcean | ✅ |
| Railway | ✅ |
| Render | ✅ |
| VPS Servers | ✅ |
| Kubernetes | ✅ |

---

# ☁️ Recommended Production Stack

```text
Internet
    ↓
Cloudflare
    ↓
Nginx / Traefik
    ↓
Docker Container
    ↓
n8n
```

---

# 🔗 Useful Integrations

| Category | Examples |
|---|---|
| Communication | Slack, Discord, Telegram |
| Databases | MySQL, PostgreSQL, MongoDB |
| Productivity | Notion, Airtable, Sheets |
| AI Tools | OpenAI, Anthropic, LangChain |
| DevOps | GitHub, GitLab, Jenkins |
| Cloud Services | AWS, Azure, GCP |

---

# 🤖 AI + n8n

n8n is becoming extremely popular for building:

- AI Agents
- AI Workflows
- Autonomous Systems
- Multi-Agent Pipelines
- RAG Applications
- AI Automation Systems

---

# 🧠 Example AI Workflow

```text
User Query
     ↓
OpenAI Processing
     ↓
Database Retrieval
     ↓
Generate AI Response
     ↓
Send Slack/Email Reply
```

---

# 📚 Learning Resources

---

# 📖 Official Documentation

```text
https://docs.n8n.io/
```

---

# 🌐 Official Website

```text
https://n8n.io/
```

---

# 💻 GitHub Repository

```text
https://github.com/n8n-io/n8n
```

---

# 👥 Community Forum

```text
https://community.n8n.io/
```

---

# 🎥 YouTube Tutorials

Search:

```text
n8n beginner tutorial
n8n AI workflows
n8n Docker setup
```

---

# 🏁 Conclusion

n8n is one of the most powerful open-source automation tools available today.

It combines:

- ✅ No-code simplicity
- ✅ Developer flexibility
- ✅ AI integrations
- ✅ Self-hosting freedom
- ✅ Enterprise-grade automation

Whether you are:

- A developer
- Startup founder
- AI engineer
- Freelancer
- Enterprise team

n8n can massively improve productivity and automate repetitive workflows efficiently.

---

# ⭐ Support n8n

If you like n8n:

- ⭐ Star the GitHub repository
- 🤝 Contribute workflows
- 💬 Join the community
- 🚀 Build amazing automations

---

<p align="center">
  Made with ❤️ - Pranav Jain
</p>