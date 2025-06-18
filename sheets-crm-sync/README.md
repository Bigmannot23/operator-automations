
# 📊 Google Sheets → Notion CRM Sync Tool

## 💡 Deploy Guide for Clients (Plug-and-Play)

---

## ✅ Overview

This automation listens for new rows added to a Google Sheet and syncs the data into a Notion CRM database — perfect for teams logging leads, deals, or client data in spreadsheets.

---

## ⚙️ Prerequisites

Ensure you have:
- ✅ Google Sheet with columns: Name, Email, Company, Status
- ✅ Notion account with CRM database
- ✅ n8n workspace with Google Sheets + Notion integrations

---

## 🪜 Setup Steps

### 1. Import the JSON into n8n
- Open your n8n dashboard
- Go to **Menu → Import**
- Upload `sheets-to-notion-crm.json`

---

### 2. Configure Google Sheets Trigger
- Set the **Spreadsheet ID** (from your Google Sheet URL)
- Choose the **Sheet Name**
- Set polling interval or event trigger

---

### 3. Map Fields in Set Node (Optional)
Normalize column names:
```js
{
  "Name": $json["Name"],
  "Email": $json["Email"],
  "Company": $json["Company"],
  "Status": $json["Status"]
}
```

---

### 4. Configure Notion Node
- Paste in your **Notion DB ID**
- Map each field:
  - Name → Title
  - Email → Email property
  - Company → Text
  - Status → Select or multi-select
- Ensure your Notion integration has access

---

### 5. Test the Sync
- Add a test row to your Google Sheet
- Confirm it appears in Notion within 1–2 minutes

---

## ✅ Success Criteria

- Each new row from the sheet becomes a new CRM entry
- Fields match and populate correctly
- Sync handles multiple entries without duplicates

---

## 🛠 Tips

- Add a filter or deduplication node to avoid re-syncing old rows
- You can upgrade this to bi-directional sync later

---

## 📦 Included

- `sheets-to-notion-crm.json` – automation flow
- Setup instructions (this file)
- Field-mapping logic
