# 🏦 Bank Reconciliation Automation (n8n + AI)

An end-to-end **finance automation workflow** built with **n8n**, **Google Sheets**, **Gmail**, and **Google Gemini AI** — designed to automatically reconcile bank statements with accounting records, flag discrepancies, and generate AI-powered summary reports.

## 📌 Overview

Manual bank reconciliation is time-consuming and error-prone. This project automates the entire process — from reading transaction data to generating a professional summary report — with zero manual intervention.
## ⚙️ Workflow Architecture

```mermaid
flowchart TD
    A[Manual Trigger] --> B[Google Sheets - Bank Statement]
    A --> C[Google Sheets - Accounting Records]
    B --> D[Code Node - Dynamic Comparison Logic]
    C --> D
    D --> E{IF: Status = Matched?}
    D --> F[Gemini AI - Summary]
    E -->|True: Matched| G[Google Sheets - Report]
    E -->|False: Unmatched| H[Gmail Alert]
    F --> I[Google Docs - Report Created]
```
## ✨ Features

- 🔄 **Dynamic comparison** — works with any invoice/reference number, no hardcoded values
- ✅ Automatically detects:
  - Matched Transactions
  - Amount Mismatches
  - Missing in Books
  - Missing in Bank
- 📊 Saves matched records into a Google Sheets reconciliation report
- 📧 Sends instant Gmail alerts for unmatched transactions
- 🤖 Generates an AI-powered summary (via Google Gemini) with insights & recommendations
- 📄 Automatically saves the summary report into Google Docs

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **n8n** | Workflow automation engine |
| **Google Sheets** | Data source (Bank Statement & Accounting Records) |
| **JavaScript (Code Node)** | Dynamic reconciliation logic |
| **Gmail** | Automated alert notifications |
| **Google Gemini AI** | AI-generated summary reports |
| **Google Docs** | Final report storage |

## 📷 Workflow Screenshot

![Workflow Screenshot](./screenshots/workflow-screenshot.png)

## 📈 Sample Output

| Reference | Bank Amount | Accounting Amount | Status |
|---|---|---|---|
| INV001 | 1000 | 1000 | ✅ Matched |
| INV002 | 2500 | 2500 | ✅ Matched |
| INV003 | 1500 | – | ❌ Missing in Books |
| INV004 | – | 1800 | ❌ Missing in Bank |

## 🚀 How It Works

1. Trigger reads transactions from both Bank Statement and Accounting Records sheets.
2. A Code node dynamically compares transactions by `Reference` and `Amount`.
3. Results are routed through an IF node:
   - **Matched** → saved to Google Sheets report
   - **Unmatched** → Gmail alert sent
4. Simultaneously, all results are sent to Gemini AI to generate a professional summary.
5. The summary is inserted into a Google Docs report, timestamped by date.

## 📥 Import This Workflow

Want to use this workflow yourself? Download the JSON file below and import it directly into your n8n instance:

👉 [bank-reconciliation-workflow.json](./bank-reconciliation-workflow.json)

**To import:**
1. Open n8n
2. Click **Import from File**
3. Select the downloaded JSON file
4. Reconnect your Google Sheets, Gmail, and Gemini credentials

## 💡 About This Project

Built as part of my journey into **Finance Automation**, combining my background in tax compliance, treasury operations, and banking reconciliations with automation tools like n8n and AI.

## 📫 Let's Connect

I'm currently open to **remote opportunities** in Finance Automation, Tax & Treasury, or Process Automation.

- LinkedIn: [https://www.linkedin.com/in/syed-ali-raza1990/]
- Email: [Alisherazi51215@Yahoo.Com]

---
⭐ If you found this useful, feel free to star the repo!


