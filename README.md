# n8n and Make automation portfolio

Portfolio projects built for simulated clients (not paid client work). Each build is documented as Problem, Process, Tools, Automation, Result, plus known limitations. Workflow JSON files are sanitized: credential IDs, chat IDs, sheet IDs, and personal emails are replaced with placeholders.

| Build | Tools | Status |
|---|---|---|
| [Pipedrive Lead Intake](n8n/pipedrive-lead-intake) | n8n, Pipedrive, Telegram | Live-tested |
| [Won Deal to ClickUp Onboarding](n8n/won-deal-clickup-onboarding) | n8n, Pipedrive, ClickUp | Ran on a real deal in my own trial account |
| [Naga Homes Assistant](n8n/naga-homes-assistant) | n8n, Groq, Airtable, Telegram | Published and tested |
| [Voice-Note Listing Bot](n8n/voice-note-listing-bot) | n8n, Telegram, Groq (Whisper + LLM) | Published and tested |
| [Global Error Handler](n8n/global-error-handler) | n8n, Telegram, Google Sheets | Tested with a deliberate failure |
| [Shopify Abandoned Cart Recovery](make/shopify-cart-recovery) | Make, Shopify dev store, Groq, Gmail, Google Sheets | Real dev-store checkout webhook, test checkouts only |

Other Make scenarios (lead follow-up, onboarding, invoice intake, AI inquiry triage, dashboard) are described in the case study PDFs: https://drive.google.com/drive/folders/1n9clnJjOrgrulIw-aEedwhg27_hazmpA?usp=sharing

Portfolio site: https://rafael-automates.github.io

## How to import a workflow
1. In n8n, create a new workflow, then use the menu to import from file.
2. Re-create each credential (the JSON holds only placeholders) and select it on each node.
3. Replace placeholder IDs (sheet, chat, folder) with your own.
