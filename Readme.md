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


⚡ Core Features
🔹 Visual Workflow Builder

Drag-and-drop workflow creation with minimal coding.

🔹 400+ Integrations

Supports apps like:

Google Sheets
Slack
Telegram
GitHub
Discord
OpenAI
MySQL
PostgreSQL
MongoDB
Airtable
🔹 AI & Agentic Automation

Integrate with:

OpenAI
Anthropic
LangChain
Vector Databases
AI Agents
🔹 Self Hosting

Host on:

Local machine
VPS
AWS
Azure
GCP
Docker
Kubernetes
🔹 Custom JavaScript Logic

Add advanced logic directly inside workflows.

🔹 Webhooks & APIs

Trigger workflows from external systems instantly.

✅ Benefits of Using n8n
Benefit	Description
Open Source	Full transparency and customization
Cost Effective	Avoid expensive automation platforms
Self Hosted	Complete data privacy and control
Scalable	Suitable for startups to enterprises
Developer Friendly	Supports custom code and APIs
AI Ready	Easily build AI workflows and agents
Time Saving	Automates repetitive manual tasks
Fast Integration	Connect multiple systems quickly
💡 Real-World Use Cases
📩 Email Automation
Auto replies
Lead nurturing
Invoice reminders
🤖 AI Automation
AI resume screening
AI customer support
AI content generation
AI agents
📊 Data Processing
Sync Excel/Sheets data
Database automation
ETL pipelines
🔔 Notifications
Slack alerts
Discord notifications
Telegram bots
🧾 Invoice Management
Extract invoice data
Send payment reminders
Store records automatically
🧠 Recruitment Automation
Resume parsing
Candidate ranking
HR notifications
⚙️ How n8n Works

n8n workflows consist of:

Component	Description
Trigger Node	Starts workflow
Action Node	Performs task
Logic Node	Conditions/loops
API Node	Connect external APIs
Database Node	Store/retrieve data
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

# 📖 Example Workflow

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

# 🧠 AI Resume Screening Workflow

```text
Resume Upload
     ↓
Extract PDF Text
     ↓
OpenAI Analysis
     ↓
Candidate Scoring
     ↓
Slack Notification
```

---

# 🧾 Invoice Automation Workflow

```text
Invoice Upload
      ↓
OCR Extraction
      ↓
Excel Entry
      ↓
Due Date Tracking
      ↓
Reminder Email
```

---

# 📲 Social Media Automation Workflow

```text
New Blog Published
       ↓
Generate Caption
       ↓
Post to LinkedIn
       ↓
Post to Twitter
```

---

# 🐳 Docker Installation Commands

## Windows

### Verify Docker Installation

```bash
docker --version
```

### Verify Docker Compose

```bash
docker compose version
```

---

## Ubuntu/Linux

### Update Packages

```bash
sudo apt update
```

### Install Docker

```bash
sudo apt install docker.io -y
```

### Start Docker

```bash
sudo systemctl start docker
```

### Enable Docker on Boot

```bash
sudo systemctl enable docker
```

### Verify Docker

```bash
docker --version
```

---

# 🚀 Running n8n Using Docker

## Pull n8n Image

```bash
docker pull n8nio/n8n
```

---

## Run n8n Container

```bash
docker run -it --rm \
-p 5678:5678 \
n8nio/n8n
```

---

## Open n8n Dashboard

```text
http://localhost:5678
```

---

# 📦 Docker Command Breakdown

```bash
docker run -it --rm -p 5678:5678 n8nio/n8n
```

| Command | Meaning |
|---|---|
| `docker run` | Starts container |
| `-it` | Interactive mode |
| `--rm` | Removes container after stop |
| `-p 5678:5678` | Port mapping |
| `n8nio/n8n` | Official image |

---

# 💾 Persistent Storage

## Create Docker Volume

```bash
docker volume create n8n_data
```

---

## Run with Persistent Storage

```bash
docker run -it --rm \
-p 5678:5678 \
-v n8n_data:/home/node/.n8n \
n8nio/n8n
```

---

# 📁 Local Folder Persistence

## Windows

```bash
docker run -it --rm ^
-p 5678:5678 ^
-v C:\n8n-data:/home/node/.n8n ^
n8nio/n8n
```

---

## Linux/Mac

```bash
docker run -it --rm \
-p 5678:5678 \
-v ~/.n8n:/home/node/.n8n \
n8nio/n8n
```

---

# 🧩 Docker Compose Setup

## Create Project Directory

```bash
mkdir n8n-docker
cd n8n-docker
```

---

## Create `docker-compose.yml`

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

## Start n8n

```bash
docker compose up -d
```

---

## Check Running Containers

```bash
docker ps
```

---

## Open Browser

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

# 🔄 Updating n8n

## Pull Latest Image

```bash
docker pull n8nio/n8n
```

---

## Stop Existing Containers

```bash
docker compose down
```

---

## Restart Containers

```bash
docker compose up -d
```

---

# 🛑 Stop & Remove Containers

## Stop Container

```bash
docker stop n8n
```

---

## Remove Container

```bash
docker rm n8n
```

---

## Remove Docker Volume

⚠️ Warning: Deletes all workflow data permanently.

```bash
docker volume rm n8n_data
```

---

# 🧪 Common Issues & Fixes

## ❌ Port Already in Use

Error:

```bash
Bind for 0.0.0.0:5678 failed
```

Fix:

```bash
-p 8080:5678
```

Open:

```text
http://localhost:8080
```

---

## ❌ Docker Permission Denied

```bash
sudo usermod -aG docker $USER
```

Restart terminal afterward.

---

## ❌ Container Restart Loop

Check logs:

```bash
docker logs n8n
```

---

## ❌ Cannot Access UI

Check containers:

```bash
docker ps
```

---

# 🔒 Security Best Practices

## Enable Authentication

Never expose public n8n without authentication.

---

## Use HTTPS

Recommended options:

- Nginx
- Traefik
- Cloudflare Tunnel

---

## Backup Important Data

Backup folder:

```text
/home/node/.n8n
```

---

## Use Environment Variables

Avoid hardcoding secrets directly in workflows.

---

# 🔗 Useful Links

## Official Documentation

```text
https://docs.n8n.io/
```

---

## Official Website

```text
https://n8n.io/
```

---

## GitHub Repository

```text
https://github.com/n8n-io/n8n
```

---

## Community Forum

```text
https://community.n8n.io/
```

---

# 🏁 Conclusion

n8n is one of the most powerful automation platforms available today.

It combines:

- ✅ No-code simplicity
- ✅ Developer flexibility
- ✅ AI capabilities
- ✅ Self-hosting freedom
- ✅ Enterprise-grade automation

Perfect for:

- Developers
- Startups
- AI Engineers
- Automation Enthusiasts
- Enterprises

---

# ⭐ Support n8n

If you like n8n:

- ⭐ Star the GitHub repository
- 🤝 Contribute workflows
- 💬 Join the community
- 🚀 Build amazing automations

---

<p align="center">
  Made with ❤️ using n8n Automation
</p>