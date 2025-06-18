
# 🧾 Stripe Payment Recovery System

## 💡 Deploy Guide for Clients (Plug-and-Play)

---

## ✅ Overview

This system detects failed payments in Stripe, emails the customer immediately, logs the event to Notion, and alerts your team in Slack — all in under 30 seconds.

---

## ⚙️ Prerequisites

Ensure you have:
- ✅ Stripe account (test mode is fine)
- ✅ Gmail (or SMTP provider)
- ✅ Notion account (with a logging database)
- ✅ Slack account + channel (optional)

---

## 🪜 Step-by-Step Installation

### 1. Import the JSON into n8n
- Open your n8n workspace  
- Go to **Menu → Import**  
- Upload or paste `stripe-recovery.json`

---

### 2. Configure Environment Variables

Set these in n8n Settings or your ENV file:

| Key               | Value                  |
|------------------|------------------------|
| STRIPE_SECRET_KEY| Your Stripe secret key |
| NODE_ENV         | `prod` or `test`       |

---

### 3. Setup Notion

1. Create a Notion database (table view)  
2. Add the following columns:
   - **Title** (text) — customer name  
   - **Email** (email)  
   - **Amount** (number)  
   - **InvoiceLink** (URL)  
   - **Error** (text)  
   - **EmailSent** (text or select)  
   - **Timestamp** (date/time)  
   - **Environment** (text)  
   - **TriggerEvent** (text)  
3. Share the DB with your Notion integration  
4. Paste your Notion **Database ID** into the Notion node in n8n

---

### 4. Configure Email

- Use a **Gmail App Password** or SMTP credentials  
- In the “Send Email” node, update:
  - From email address  
  - SMTP host, port, user, and password  

**Gmail Tip:** enable “less secure apps” or use a Google App Password

---

### 5. Configure Slack Alerts (Optional)

1. Create a Slack bot with `chat:write` scope  
2. Install it to your workspace  
3. Add the bot to your desired Slack channel (e.g., `#alerts`)  
4. Paste your Slack bot token into the Slack node  
5. Update the target channel name

---

### 6. Register Stripe Webhook

- Go to **Stripe → Developers → Webhooks**  
- Click **+ Add Endpoint**:
  - **URL:** your n8n webhook URL  
  - **Events:** `invoice.payment_failed`  
- Test with this card: `4000 0000 0000 9995`

---

## ✅ Success Criteria

When a Stripe payment fails:
- ✅ Email is sent to the customer  
- ✅ Log is created in Notion  
- ✅ Slack alert posts in `#alerts`  
- ✅ “EmailSent” is recorded as ✅ or ❌  
- ✅ Environment + trigger event are logged

---

## 🛠 Support

If anything fails:
- Check the n8n execution log  
- Verify API keys, webhook URL, Notion DB field names  
- You can manually log fallback data into Notion if needed
