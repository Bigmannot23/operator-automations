
# 🕰️ Lead Aging Notifier – Slack Reminder for Stale Deals

## 💡 Overview

This automation checks your CRM (Notion or Airtable) daily and sends a Slack alert for any lead that hasn't been updated in the last 3+ days. Ideal for keeping pipelines fresh and follow-ups timely.

---

## ⚙️ Prerequisites

- ✅ Notion (or Airtable) CRM database
- ✅ Slack workspace + bot token
- ✅ n8n cloud or self-hosted instance

---

## 🪜 Setup Steps

### 1. Import Workflow JSON to n8n
- Open n8n
- Click menu → **Import**
- Upload `lead-aging-notifier.json`

---

### 2. Configure Trigger
- Default: runs every weekday at 9AM
- Edit Cron node to your preferred schedule

---

### 3. Configure Notion Node
- Set your Notion DB ID
- Required properties:
  - Title (lead name)
  - LastUpdated (date)
  - Status (optional)

---

### 4. Define Aging Threshold
- Inside Filter or IF node:
  - If `LastUpdated < now - 3 days`, include in Slack message

---

### 5. Customize Slack Alert
- Add your Slack bot token (chat:write)
- Define target channel
- Slack message includes:
  - Lead name
  - Days stale
  - Last touched date
  - Direct Notion link (optional)

---

## ✅ Success Criteria

- Slack alert every morning with list of leads past the freshness threshold
- Each entry is traceable to Notion record
- No duplicate alerts for the same day

---

## 📦 What You Get

- JSON automation file
- Setup markdown README
- Slack alert logic template
- Aging filter pre-built
