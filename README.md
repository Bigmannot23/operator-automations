# 🛠 Operator Automations – 5 Ready-to-Run n8n Workflows

Welcome to your operator-grade automation stack.  
This repo includes 5 fully documented, import-ready workflows for async ops, client systems, and internal workflows.

---

## 🚀 Included Automations

### 1. **Stripe Payment Recovery**
→ Catches failed payments, sends branded email, logs to Notion  
📂 `/1-stripe-payment-recovery`

### 2. **Slack Standup Logger**
→ Posts daily Slack standup, logs responses to Notion  
📂 `/2-slack-standup-logger`

### 3. **Typeform Auto-Responder**
→ Sends personalized email replies to Typeform submissions and logs them  
📂 `/3-typeform-auto-responder`

### 4. **Sheets → Notion CRM Sync**
→ Syncs new rows in a Google Sheet to a Notion CRM database  
📂 `/4-sheets-to-notion-crm`

### 5. **Lead Aging Notifier**
→ Scans Notion CRM for stale leads and sends Slack alerts  
📂 `/5-lead-aging-notifier`

---

## ✅ n8n Post-Import Setup Checklist

Use this to go from `.json` to live system in under 2 minutes.

### 1️⃣ Confirm Import Success
- Workflow appears in your n8n Workflows list
- Name, trigger, and nodes are visible in the canvas

### 2️⃣ Review & Activate Trigger
- Ensure trigger node is present (Webhook, Schedule, Stripe, etc.)
- For Webhooks: copy the test/live URL and configure at the source
- For Scheduled: set your preferred interval
- Toggle workflow to **Active**

### 3️⃣ Plug In Credentials
- Resolve any red credential errors
- Open each third-party node (Stripe, Notion, Gmail, etc.)
- Add/select credentials from dropdown
- Click “Test” to verify connection

### 4️⃣ Test With Live Data
- Use “Execute Workflow” or send a real webhook/form
- Watch each node execute
- Confirm correct behavior or inspect errors

### 5️⃣ Save & Tag
- Rename for clarity (e.g. `Stripe Recovery - Live`)
- Add tags: `live`, `test`, `client-name`, etc.
- Click **Save**

---https://github.com/Bigmannot23/operator-automations

**Built by Lexvion – async systems studio**  
Questions or requests? → [github.com/bigmannot23](https://github.com/bigmannot23)