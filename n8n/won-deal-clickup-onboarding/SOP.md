# SOP: Won Deal to ClickUp Onboarding

**Owner:** YOUR NAME | **Last updated:** DATE

## 1. Purpose
Create a ClickUp onboarding workspace automatically when a Pipedrive deal is won.

## 2. Trigger and scope
Pipedrive deal updated. Runs only when `won_time` is newly set. Re-won or edited deals are ignored.

## 3. Flow
1. Pipedrive Trigger receives the deal update.
2. IF node checks that `won_time` is newly set.
3. Get Organization fetches the client name.
4. ClickUp: create a folder, then an Onboarding list.
5. Code node builds 5 tasks with assignee, relative due dates, and priority.
6. ClickUp: create each task.

## 4. Credentials needed (names only)
Pipedrive API, ClickUp API, Telegram bot (via the error handler), Google service account (error log).

## 5. Common failures and fixes
- **No trigger after n8n restarts:** the Cloudflare tunnel URL changed. Update `WEBHOOK_URL` in the Docker run command, restart, and re-publish the workflow.
- **Auth error:** reconnect or replace the API credential.
- **Duplicate folder or tasks:** a retry followed a timeout. Delete the extras and, if it repeats, turn off retry on that node.
- **No task created:** check the Code node output for empty fields.

## 6. Restart and recovery
Check the error log sheet and Telegram alerts, open the failed execution via its link, fix the cause, and re-run from the Executions tab.

## 7. Safe testing
Use a dummy deal and organization, then delete the generated ClickUp folder afterward.
