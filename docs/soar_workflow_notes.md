#  SOAR Workflow Notes

This document summarizes automation workflows built in Splunk SOAR or Tines.

---

## Playbook: IP Enrichment and Ticketing

**Goal:** Automatically enrich suspicious IP addresses and create Jira tickets.

| Step | Action       | Description                                            |
| ---- | ------------ | ------------------------------------------------------ |
| 1    | Input        | Triggered by Splunk detection (failed login attempts). |
| 2    | Enrichment   | Query VirusTotal for IP reputation.                    |
| 3    | Decision     | If malicious score > threshold → proceed.              |
| 4    | Jira Ticket  | Create a Jira issue with enrichment details.           |
| 5    | Notification | Post message to Slack `#security-alerts` channel.      |

---

## Playbook: Endpoint Containment

**Goal:** Quarantine infected endpoints using SOAR → CrowdStrike API integration.

| Step | Action      | Description                                       |
| ---- | ----------- | ------------------------------------------------- |
| 1    | Input       | Triggered by high-severity CrowdStrike alert.     |
| 2    | Validation  | Confirm IOC via Threat Intelligence feed.         |
| 3    | Containment | Execute CrowdStrike API call to isolate endpoint. |
| 4    | Reporting   | Create Jira ticket and notify SOC team.           |

---

Add screenshots, JSON exports, and workflow diagrams here as you build them.
