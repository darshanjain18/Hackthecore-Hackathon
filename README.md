<div align="center">

# 🧠 CortexGuard AI
### Adaptive Threat Intelligence Platform

**Real-time, AI-powered detection of phishing attacks, scams, and malicious content — across emails, messages, and links.**

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-Backend-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-DistilBERT-FFD21E?style=flat-square&logo=huggingface&logoColor=black)](https://huggingface.co)
[![Gmail API](https://img.shields.io/badge/Gmail-OAuth%202.0-EA4335?style=flat-square&logo=gmail&logoColor=white)](https://developers.google.com/gmail)


</div>

---

## 🔍 Overview

CortexGuard AI is a **context-aware, multi-layered threat detection platform** built for the modern threat landscape. Unlike legacy keyword-based filters, CortexGuard combines deep NLP semantic analysis with real-time URL intelligence and protocol validation — delivering explainable, high-confidence verdicts for every scan.

Built for **HacktheCore Hackathon**, CortexGuard demonstrates how AI can shift security from reactive blocklisting to proactive, intelligent threat reasoning.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📬 **Real-Time Gmail Scanning** | Scans your last 72 hours of inbox via OAuth 2.0 |
| 🤖 **AI Analysis Chatbot** | Submit any message or link for instant threat assessment |
| 🌐 **URL & Domain Intelligence** | Regex-based URL extraction + domain reputation checks |
| 🧠 **NLP Scam Detection** | DistilBERT model fine-tuned on phishing datasets |
| ⚡ **Live Streaming Dashboard** | Real-time scan events via Server-Sent Events (SSE) |
| 📊 **Threat Analytics** | Visual dashboard with historical threat trends |
| 🗂️ **Filterable Archive** | Browse and filter past scans by verdict (Safe / Suspicious) |
| 💡 **Explainable AI** | Every verdict includes a human-readable reason and confidence score |

---

## 🏗️ Architecture
```
                        ┌─────────────────────────┐
                        │       User Interface      │
                        │  (Gmail · Chatbot · URL)  │
                        └────────────┬────────────┘
                                     │
                        ┌────────────▼────────────┐
                        │      Flask Backend        │
                        └──┬──────────────────┬───┘
                           │                  │
              ┌────────────▼───┐     ┌────────▼────────────┐
              │  NLP Engine     │     │   URL Analyzer       │
              │  (DistilBERT)   │     │  Regex → Domain →   │
              │  Intent · Tone  │     │  Whitelist → WHOIS  │
              │  Urgency · Fraud│     │  → SSL Validation   │
              └────────────┬───┘     └────────┬────────────┘
                           │                  │
                        ┌──▼──────────────────▼──┐
                        │      Scoring Engine      │
                        │  Reputation · Protocol   │
                        │  AI Confidence → Score   │
                        └────────────┬────────────┘
                                     │
                     ┌───────────────▼──────────────┐
                     │         MySQL Database         │
                     │       (threat_history)         │
                     └───────────────┬──────────────┘
                                     │
                     ┌───────────────▼──────────────┐
                     │     Live Dashboard (SSE)       │
                     │  Score · Verdict · Explanation │
                     └──────────────────────────────┘
```

---

## 🔄 Detection Pipeline

CortexGuard processes every input through an 8-stage pipeline:
```
1. Data Ingestion      →  Gmail API fetch or user-submitted content
2. NLP Analysis        →  Detect urgency, fraud tone, and semantic intent
3. URL Extraction      →  Identify all links via regex
4. Reputation Check    →  Match domains against trusted whitelist
5. WHOIS Lookup        →  Estimate domain age and registration patterns
6. SSL Validation      →  Verify certificate presence and validity
7. Protocol Scoring    →  HTTP = High Risk · HTTPS = deeper analysis
8. Final Verdict       →  Composite score → Safe / Suspicious + Explanation
```

---

## 🧰 Tech Stack

**Frontend**
- HTML5 + Tailwind CSS
- Glassmorphism + Aurora UI design system
- Vanilla JavaScript with SSE client

**Backend**
- Python · Flask
- MySQL (`threat_history` table)

**AI / NLP**
- Hugging Face Transformers
- DistilBERT (fine-tuned for phishing detection)

**Integrations**
- Gmail API (OAuth 2.0)
- WHOIS lookup
- SSL certificate inspection

---

## ⚙️ Installation

**Prerequisites:** Python 3.10+, MySQL, Gmail API credentials
```bash
# 1. Clone the repository
git clone https://github.com/your-repo/cortexguard-ai.git
cd cortexguard-ai

# 2. Install dependencies
pip install -r requirements.txt

# 3. Configure environment variables
cp .env.example .env
# → Add your Gmail OAuth credentials and MySQL connection string

# 4. Initialize the database
python db_init.py

# 5. Start the server
python app.py
```

---

## 🚀 Usage

Once running, open your browser at:
```
http://127.0.0.1:5000
```

- **Dashboard** — View live scan results as they stream in
- **Chatbot** — Paste any suspicious email or message for analysis
- **Gmail Scan** — Authorize once via OAuth to scan your recent inbox
- **Archive** — Review historical scans, filtered by verdict

---

## 🏆 What Makes CortexGuard Different

> Most phishing filters ask *"does this look suspicious?"*  
> CortexGuard asks *"why is this suspicious — and how confident are we?"*

- **Context-aware detection** — understands semantic intent, not just keywords  
- **Hybrid AI + rule-based system** — NLP confidence combined with deterministic protocol checks  
- **Explainable verdicts** — every result includes a human-readable reasoning trace  
- **Multi-channel analysis** — emails, messages, raw URLs, and live Gmail inbox  
- **Real-time streaming** — results surface as they're computed, not after a full batch

---

## 🔮 Roadmap

- [ ] 📱 SMS scam detection
- [ ] 🧠 Personalized risk profiling per user
- [ ] 🌍 Multi-language phishing detection
- [ ] 🤖 Autonomous AI agent for continuous inbox monitoring
- [ ] 📈 Threat intelligence feeds integration

---
