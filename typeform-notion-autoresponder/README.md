
# 📩 Typeform Auto-Responder – Lead Logger + Email Follow-Up System

## 💡 Deploy Guide for Clients (Plug-and-Play)

---

## ✅ Overview

This system watches for new Typeform submissions, sends a personalized follow-up email with service-specific info, and logs the full entry (plus message and reply) to Notion.

---

## ⚙️ Prerequisites

Ensure you have:
- ✅ Typeform account (or use webhook from Tally, Webflow, etc.)
- ✅ Gmail or SMTP email provider
- ✅ Notion account + database for logging
- ✅ n8n workspace

---

## 🪜 Step-by-Step Installation

### 1. Import JSON into n8n
- Go to Menu → Import
- Upload `typeform-lead-autoresponder.json`

---

### 2. Configure Trigger (Webhook)

- Set up Typeform webhook to POST to your n8n webhook URL
- Ensure it includes: Name, Email, Service Type, Message

---

### 3. Configure Email Node

- SMTP credentials or Gmail App Password
- Edit subject and body with your brand’s tone
- Reference dynamic fields:
  - Name
  - ServiceType (Web Design, SEO, Email Marketing)
  - FAQ Link

---

### 4. Customize FAQ Routing Logic (Optional)

In the Set or Function node:
```js
if (service === 'Web Design') {
  body += 'Here’s our design FAQ: example.com/design-faq';
} else if (service === 'SEO') {
  body += 'SEO tips here: example.com/seo-faq';
}
```

---

### 5. Setup Notion Logging

- Create a Notion DB with:
  - Title (Name)
  - Email
  - Service Type
  - Message
  - Email Sent? (Yes/No)
  - Email Content
  - Timestamp

- Connect your Notion integration + insert DB ID into the Notion node

---

## ✅ Success Criteria

- Lead submits Typeform →  
- Auto-response email sent (customized by service)  
- Message + metadata logged to Notion  
- No failures — logs email status per entry

---

## 🛠 Support

Use n8n execution log to trace any missing fields or message mismatches.
