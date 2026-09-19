# 🚀 AI Lead Triage & Dynamic State Migration Pipeline (n8n + JavaScript + Gemini)

A production-grade lead management pipeline built in **n8n** using **custom JavaScript Code Nodes** and **Google Gemini AI**. 

Unlike basic lead-capture scripts that only append new rows, this workflow handles complete **lead state management**: validating raw payloads, deduplicating returning leads, scoring intent with AI, and executing atomic tab-shifts across spreadsheet databases when lead priority updates.

<img width="1229" height="491" alt="full" src="https://github.com/user-attachments/assets/110366f5-a163-43ec-ae06-8df4539cbdea" />


---

## ⚙️ Key Technical Features

* **Custom JavaScript Validation Engine:** Pre-screens inbound form payloads to prevent malformed data from touching downline services and wasting API budget.
* **Token-Optimized Deduplication:** Performs multi-tab database checks for returning leads. Bypasses heavy processing if parameters haven't changed to optimize AI token consumption.
* **AI Intent Scoring:** Analyzes project requirements and budget parameters using **Gemini AI** to assign dynamic priority tags.
* **Atomic State Migration Engine:** Evaluates priority tab shifts (`old_tab !== new_tab`) in JavaScript code nodes, cleanly executing a delete-and-append migration without orphan records or schema breakage.
* **Multi-Channel Delivery:** Triggers context-aware Slack team alerts and automated Gmail follow-ups based on real-time lead score.

---

## 🛠️ Stack & Technologies

* **Workflow Orchestration:** [n8n](https://n8n.io/)
* **Custom Code:** JavaScript (Node.js ES6+)
* **AI Model:** Google Gemini API
* **Database / Storage:** Google Sheets API
* **Integrations:** Slack Webhooks, Gmail API
* **Frontend:** Custom HTML5 / JavaScript Form

---

## 📥 How to Import & Run

1. Clone this repository:
   ```bash
   git clone https://github.com/Syeda-Fiza-Gilani/AI-Lead-Triage-Dynamic-State-Migration-Pipeline.git
   ```
2. Open your **n8n** dashboard.
3. Click **Workflows** -> **Import from File** and select `main_workflow.json`.
4. Configure your credentials for:
   * Google Sheets API
   * Google Gemini API
   * Slack OAuth / Webhook
   * Gmail OAuth2
5. Link your lead capture form (`assets/index.html`) to the n8n Webhook node URL.

---

## 🔒 Security Note
All sensitive API keys, webhook URLs, and personal test data have been removed from the exported `.json` file. Ensure you configure your own environment credentials upon import.
