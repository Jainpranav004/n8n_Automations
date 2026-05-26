# 🚀 AI Gmail Automation Agent using n8n

<p align="center">
  <b>Automated AI-powered Gmail workflow using n8n + Google Sheets + LLMs</b>
</p>

---

# 📌 Overview

This project is an AI-powered Gmail automation workflow built using **n8n**.

The workflow:

✅ Fetches pending email data from Google Sheets  
✅ Processes records one-by-one using loop logic  
✅ Uses AI (LLM) to generate dynamic email content  
✅ Downloads attachments/files if required  
✅ Sends automated emails through Gmail  
✅ Updates status back into Google Sheets  

---

# ❗ Problem Statement

Managing repetitive emails manually is time-consuming.

Businesses and individuals often struggle with:

- Sending repetitive emails
- Handling bulk outreach
- Managing follow-ups
- Personalizing responses
- Tracking sent emails

Manual workflows reduce productivity and scalability.

---

# 🎯 Solution

This workflow automates the entire email pipeline.

```text
Google Sheets
      ↓
Loop Through Records
      ↓
Generate AI Email
      ↓
Download Attachments
      ↓
Send Gmail Message
      ↓
Update Google Sheets
```

Users only need to add email details inside the sheet.

The automation handles everything else automatically.

---

# ⚡ Features

- Automated email generation
- AI-powered dynamic responses
- Bulk email handling
- Google Sheets integration
- Gmail automation
- Attachment support
- Loop-based processing
- Fully scalable workflow

---

# 🏗️ Workflow Architecture

```text
Schedule Trigger
       ↓
Google Sheets
       ↓
Loop Over Items
       ↓
Wait Node
       ↓
AI LLM Chain
       ↓
JavaScript Processing
       ↓
Download File
       ↓
Send Gmail Message
       ↓
Update Google Sheets
```

---

# 🖼️ Workflow Screenshot

<p align="center">
  <img src="./workflow.png" width="100%" />
</p>

---

# ⚙️ Tech Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Google Sheets | Data storage |
| Groq/OpenAI | AI email generation |
| Gmail API | Email sending |
| JavaScript Node | Data processing |
| Docker | Local deployment |

---

# 🔄 Workflow Explanation

## ⏰ Schedule Trigger

Automatically starts workflow on a schedule.

Useful for:

- Daily outreach
- Automated follow-ups
- Scheduled campaigns

---

## 📄 Get Row(s) in Sheet

Fetches email records dynamically from Google Sheets.

Example:

| Name | Email | Status |
|---|---|---|
| John | john@gmail.com | Pending |

---

## 🔁 Loop Over Items

Processes records one-by-one.

Prevents workflow overload during bulk operations.

---

## ⏳ Wait Node

Adds delay between executions.

Helps avoid:

- Gmail rate limits
- Spam detection
- API overload

---

## 🤖 Basic LLM Chain

Generates AI-powered email content dynamically.

Responsibilities:

- Personalized emails
- Professional formatting
- Dynamic responses
- Human-like tone

---

## 🧠 Groq Chat Model

Acts as the LLM backend for fast AI inference.

Used for:

- Content generation
- Smart responses
- Email drafting

---

## 💻 JavaScript Node

Processes and formats workflow data.

Used for:

- Cleaning outputs
- Formatting prompts
- Preparing attachments

---

## 📥 Download File Node

Downloads required files or attachments before sending emails.

---

## 📧 Send Gmail Message

Sends generated emails automatically using Gmail integration.

---

## 📤 Update Row in Sheet

Updates email status back into Google Sheets.

Example:

```text
Pending → Sent
```

---

# 📂 Project Structure

```text
gmail-ai-agent/
│
├── workflow/
│   └── gmail_agent.json
│
├── assets/
│   └── workflow.png
│
├── README.md
│
└── docker-compose.yml
```

---

# 📥 Import Workflow

1. Open n8n
2. Click "Import Workflow"
3. Upload:

```text
gmail_agent.json
```

4. Configure credentials
5. Run workflow

---

# 🚀 Run Locally using Docker

## Pull n8n Image

```bash
docker pull n8nio/n8n
```

---

## Run Container

```bash
docker run -it --rm \
-p 5678:5678 \
n8nio/n8n
```

---

## Open n8n

```text
http://localhost:5678
```

---

# 🧩 Docker Compose Setup

Create `docker-compose.yml`

```yaml
version: '3.8'

services:
  n8n:
    image: n8nio/n8n

    ports:
      - "5678:5678"

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

# 🔑 Environment Variables

| Variable | Purpose |
|---|---|
| `GROQ_API_KEY` | LLM access |
| `GOOGLE_CREDENTIALS` | Google Sheets auth |
| `GMAIL_CREDENTIALS` | Gmail API access |

---

# 📊 Example Execution

```text
Fetch Pending Emails
        ↓
Generate AI Response
        ↓
Send Gmail Message
        ↓
Update Sheet Status
```

---

# 🛠️ Future Enhancements

- AI follow-up generation
- Multi-email provider support
- Analytics dashboard
- Auto reply classification
- CRM integration
- AI sentiment analysis

---

# 🤝 Contributing

Contributions are welcome.

Feel free to:

- Improve workflows
- Add integrations
- Optimize prompts
- Enhance automation logic

---

# 📜 License

This project is licensed under the MIT License.

---

# ⭐ Support

If you like this project:

- ⭐ Star the repository
- 🍴 Fork the project
- 🚀 Build amazing automations

---

<p align="center">
  Made with ❤️ using n8n + AI
</p>