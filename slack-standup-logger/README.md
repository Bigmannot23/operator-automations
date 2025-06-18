
# 🧑‍💻 Async Slack Standup Logger

## 💡 Deploy Guide for Clients (Plug-and-Play)

---

## ✅ Overview

This system posts a daily standup prompt to Slack, collects threaded replies, parses them into Yesterday / Today / Blockers, and logs everything to Notion — all async, no meetings required.

---

## ⚙️ Prerequisites

Ensure you have:
- ✅ Slack account (with bot token + channel)
- ✅ Notion account (with logging DB)
- ✅ n8n instance (self-hosted or cloud)

---

## 🪜 Step-by-Step Installation

### 1. Import the JSON into n8n
- Open n8n workspace
- Menu → Import
- Upload or paste `slack-standup-logger.json`

---

### 2. Create Slack Bot
- Create bot at https://api.slack.com/apps
- Enable `chat:write`, `channels:history`, and `users:read`
- Install bot to workspace
- Add bot to target Slack channel (e.g., `#standup`)
- Copy bot token and paste into Slack nodes in n8n

---

### 3. Configure Daily Cron Trigger
- Adjust Cron node to desired time (e.g., 10am daily)
- Choose “Every weekday” or custom

---

### 4. Setup Notion Database

Create a Notion DB with columns:
- Title (Contributor name)
- Date (date)
- Yesterday (text)
- Today (text)
- Blockers (text)
- FullMessage (text)
- SlackTS (text)

Share the DB with your Notion integration + paste DB ID into Notion node.

---

### 5. Message Format for Team

Slack prompt example:

```
Hi team! Please reply in this thread with your update:

*Yesterday:*  
*Today:*  
*Blockers:*  
```

Replies should follow that format to be parsed accurately.

---

### 6. Regex Message Parsing (Built-in)

The function node in the flow uses regex to extract:
- Yesterday
- Today
- Blockers

It also logs the full message and Slack TS for auditing.

---

## ✅ Success Criteria

Each weekday:
- Prompt is posted to Slack
- Team replies in thread
- Responses parsed by regex
- Structured data logged to Notion

---

## 🛠 Support

- Check Slack bot scopes and token
- Confirm Notion DB has correct column names
- Use n8n execution log for failed parsing
