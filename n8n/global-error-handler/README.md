# Global Error Handler
Portfolio project. Tested with a deliberate failure.

## Problem
Automations fail silently, so nobody knows a lead or task was missed.

## Process
Built one central error workflow and attached it to each production workflow. Added retries to absorb temporary API errors.

## Tools
n8n Error Trigger, Telegram, Google Sheets (service account).

## Automation
Error Trigger, Telegram alert (workflow, node, message, link), append a row to an error log sheet. API nodes use Retry On Fail: 3 tries, 3000 ms apart.

## Result
A deliberately failing HTTP node retried (execution took about 9 seconds), then alerted Telegram and logged the error.

## Known limitations
Does not fire on manual test runs. It cannot report that n8n itself is down; a Docker restart policy covers that.

## Screenshots
Add to `screenshots/`: canvas, retry settings, failed execution, Telegram alert, sheet row.
