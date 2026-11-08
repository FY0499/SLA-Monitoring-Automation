# SLA Monitoring Automation

An n8n workflow that checks support tickets against priority-based service-level targets, detects tickets that are close to or have exceeded their SLA, logs the results, and sends Telegram alerts.

## How it works

1. A scheduled trigger retrieves support tickets from Google Sheets.
2. JavaScript calculates the SLA duration from ticket priority and creation time.
3. Tickets close to the SLA deadline or past it are separated from tickets still within the target.
4. Telegram sends a warning or escalation message, and the workflow appends a monitoring record to a Google Sheet.

## Technologies

- n8n
- Google Sheets
- JavaScript
- Telegram

## Setup

1. Import workflow.json into n8n.
2. Configure Google Sheets and Telegram credentials.
3. Connect your ticket source and SLA log sheet, ensuring the expected fields are present (Ticket, Priority, Created Date).
4. Review the priority-to-SLA-hour mapping and Telegram destination before enabling the schedule.

## Notes

This repository contains the exported n8n workflow. Configure your own credentials and integrations in n8n before running it.
