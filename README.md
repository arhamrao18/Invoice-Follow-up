<div align="center">

# 🧾 Invoice Follow-Up Automation

**Stop manually chasing unpaid invoices. Let n8n do it for you — every day, automatically.**

[![n8n](https://img.shields.io/badge/built%20with-n8n-orange?style=flat-square)](https://n8n.io)
[![Google Docs](https://img.shields.io/badge/data%20source-Google%20Docs-4285F4?style=flat-square&logo=google-docs&logoColor=white)](#)
[![Google Sheets](https://img.shields.io/badge/logging-Google%20Sheets-34A853?style=flat-square&logo=google-sheets&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-lightgrey?style=flat-square)](#license)

</div>

---

## 💡 The Problem

Every day, freelancers and small business owners lose hours doing the same repetitive task:

- Opening a client list
- Checking who hasn't paid
- Typing out the same reminder message, one client at a time
- Trying to remember who was *already* messaged today

Miss a follow-up, and payment gets delayed even further. Send too many, and it looks unprofessional.

## ✅ The Solution

This workflow automates the entire process, end to end:

- 📄 Pulls client and invoice data directly from **Google Docs**
- 🔍 Checks whether each invoice is still **unpaid**
- 🚫 Skips any client who's **already been followed up with today** — no spamming
- ✉️ Sends a personalized follow-up automatically
- 📊 Logs the **follow-up count** and **last sent date** back into **Google Sheets**

Result: what used to take 1–2 hours a day now takes **zero** — and you always know exactly who's been followed up with, and when.

---

## 🗺️ Workflow Diagram

https://github.com/user-attachments/assets/d7410453-946f-4e82-a96a-d170b9ead1c4


## ⚙️ How It Works

| Step | Node | What It Does |
|------|------|---------------|
| 1 | **Daily Schedule Trigger** | Runs the workflow automatically once a day (time configurable) |
| 2 | **Fetch Client & Invoice Data** | Reads client names, invoice amounts, due dates, and payment status from Google Docs |
| 3 | **Loop Through Each Client** | Processes one invoice record at a time |
| 4 | **Invoice Status Check** | If the invoice is already marked **Paid**, the client is skipped |
| 5 | **Duplicate Follow-Up Check** | Checks the Google Sheet log — if a follow-up was already sent **today**, skip |
| 6 | **Send Follow-Up Message** | Sends a personalized reminder to the client |
| 7 | **Update Google Sheet** | Increments the follow-up count and logs the latest sent date |

---

## 🧰 Requirements

- An active [n8n](https://n8n.io) instance (Cloud or self-hosted)
- A Google account with:
  - **Google Docs API** access (client/invoice source data)
  - **Google Sheets API** access (follow-up log)
- A messaging/email credential configured for sending the follow-up (e.g. Gmail, WhatsApp, or your preferred channel)

---

## 🚀 Setup

1. **Import the workflow** JSON into your n8n instance.
2. Connect your **Google Docs** and **Google Sheets** credentials under each respective node.
3. Update the **Google Docs URL** and **Google Sheet ID** to point to your own client/invoice data.
4. Configure the **message-sending node** with your preferred channel and credentials.
5. Adjust the **Schedule Trigger** to your preferred run time (default: once daily).
6. Activate the workflow. ✅

---

## 🛡️ Safety Features

- **No duplicate messages** — the workflow checks the log before sending, so a client is never followed up with twice in the same day.
- **Paid invoices are automatically skipped** — no awkward reminders after payment has been received.
- **Fully logged** — every follow-up sent is recorded with a timestamp for full transparency.

---

## 🧭 Possible Enhancements

- Escalating follow-up tone based on how many reminders have been sent
- Multi-channel escalation (Email → WhatsApp → LinkedIn) if no response after X days
- Automatic "Paid" status detection via payment gateway webhooks (Stripe / PayPal / JazzCash)
- Daily summary report sent to the business owner (Email / Telegram / Slack)
- Conditional formatting in Google Sheets for at-a-glance overdue tracking

---

## 📄 License

This project is open for personal and commercial use. Attribution appreciated but not required.

---

<div align="center">
  <sub>Built to eliminate one more manual task from your day.</sub>
</div>
