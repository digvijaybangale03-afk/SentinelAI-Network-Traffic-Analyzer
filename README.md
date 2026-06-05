# ⚡ SentinelAI — AI Tool Activity Monitor

Monitor AI tool usage across all company machines. Get real-time email, Slack, or Teams alerts.

## Tracks 70+ AI Tools Including
ChatGPT · Claude · Gemini · Perplexity · Microsoft Copilot · Grok · Meta AI · Poe · Character.AI
GitHub Copilot · Cursor · Tabnine · Codeium · Windsurf · Devin · Amazon CodeWhisperer
Midjourney · DALL-E · Stable Diffusion · Adobe Firefly · Runway · ElevenLabs · Suno · Udio
Jasper · Grammarly · QuillBot · Writesonic · Notion AI · Elicit · Perplexity · Phind
OpenAI Playground · Anthropic Console · Google AI Studio · Groq · Together AI · Replicate
...and many more

## Architecture

```
[Employee Machine]     [Employee Machine]     [Employee Machine]
  agent/monitor.py  →   agent/monitor.py  →   agent/monitor.py
         ↓                      ↓                      ↓
                    [Central Server]
                    server/app.py
                         ↓           ↓           ↓
                    Dashboard    Email       Slack/Teams
```

## Quick Start

See `docs/SETUP_GUIDE.md` for full instructions.

```bash
# Server (run once, central machine)
cd server && pip install -r requirements.txt && python app.py

# Dashboard (build once)
cd dashboard && npm install && npm run build

# Agent (deploy on each employee machine)
cd agent && pip install -r requirements.txt
# Edit config.json with server IP and employee name
python monitor.py
```

## Notification Channels
- ✉️ Gmail (SMTP with App Password)
- 💬 Slack (Incoming Webhook)
- 🟦 Microsoft Teams (Incoming Webhook)
- 🔗 Generic Webhook (Discord, Telegram, PagerDuty, Zapier, etc.)
- 📄 Local JSONL log file (always on)
- 🌐 REST API (`GET /api/events`)
