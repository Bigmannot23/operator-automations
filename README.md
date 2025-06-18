---

## ✅ n8n Post-Import Setup Checklist

Quick guide to activate this workflow after importing the `.json`.

### 1️⃣ Confirm Import Success
- Workflow appears in your n8n Workflows list
- Name, trigger, and nodes are visible in the canvas

### 2️⃣ Review & Activate Trigger
- Ensure trigger node is present (Webhook, Schedule, Stripe, etc.)
- For Webhooks: copy the test/live URL and configure at the source
- For Scheduled: set interval (e.g. every 10 mins, daily)
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

### 6️⃣ Optional – Export or Clone
- Use top-right `... → Export` to save a backup
- Duplicate for variants or client installs

---

### 🔁 Fast Version (for pros)

- [ ] Import .json
- [ ] Activate trigger (Webhook/Schedule)
- [ ] Add credentials (Stripe, Notion, etc.)
- [ ] Test with real data
- [ ] Save + tag for reuse