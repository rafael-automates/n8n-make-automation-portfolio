# Pipedrive Lead Intake
Portfolio project (simulated client). Live-tested with test deals in my own Pipedrive trial.

## Problem
Leads from forms and social links were copied into the CRM by hand, with no record of where each one came from.

## Process
Designed one form whose hidden field captures `?lead_source=` from the link (fallback "unknown"). Phone is required so every lead can be called.

## Tools
n8n (self-hosted, Docker), Pipedrive, Telegram.

## Automation
Form Trigger, create Organization, create Person, create Deal, create Activity (call due tomorrow), Telegram alert. Retry on fail (3 tries, 3 s) on API nodes; failures go to the Global Error Handler.

## Result
A submitted form becomes a fully linked CRM record with a follow-up task in seconds. Tested with instagram, instagram_bio, and facebook_ad links.

## Known limitations
No duplicate-contact check. A retry after a timeout could create a duplicate record.

## Screenshots
Add to `screenshots/`: workflow canvas, form, resulting deal, Telegram alert.
