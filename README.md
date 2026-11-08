# SLA Monitoring Automation

I built this n8n workflow to monitor support tickets against their service-level targets, identify tickets that are close to breaching or have already breached the SLA, and notify the team.

<img width="588" height="235" alt="image" src="https://github.com/user-attachments/assets/18ae9bb7-4002-4fb7-b708-bd695193858f" />

## How it works

1. The workflow checks ticket records in Google Sheets on a schedule.
2. JavaScript assigns an SLA target based on ticket priority: Critical (2 hours), High (8 hours), Medium (24 hours), and Low (72 hours).
3. The workflow calculates the remaining time and identifies tickets that are close to the deadline or have exceeded it.
4. Tickets that have exceeded the SLA trigger an urgent Telegram alert, while tickets close to the deadline trigger a warning.
5. The workflow records the SLA status and ticket information in a Google Sheets log.

## Main features

- Priority-based SLA calculation.
- Detection of tickets close to or beyond their SLA.
- Separate warning and escalation alerts.
- Automatic SLA log in Google Sheets.
- Telegram notifications.

## Technologies

n8n, Google Sheets, JavaScript, Telegram, and Schedule Trigger.

## Setup

Import [workflow.json](./workflow.json) into n8n, configure your Google Sheets and Telegram credentials, then connect your ticket sheet and SLA log sheet. Make sure the ticket data includes the priority and creation date fields before testing.
