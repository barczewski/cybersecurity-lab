#  Cybersecurity Lab Portfolio

This repository documents hands-on projects and detections built while learning **SIEM**, **EDR**, and **SOAR** technologies such as **Splunk**, **CrowdStrike Falcon**, **Cribl**, and **Splunk SOAR**.
It follows a 12-week roadmap designed to build practical blue-team engineering skills.

---

##  Folder Structure

```
cybersecurity-lab/
├── detections/
│   ├── splunk/
│   │   ├── powershell_execution.spl
│   │   ├── failed_logins.spl
│   ├── crowdstrike/
│       ├── suspicious_process.fql
│       ├── lateral_movement.fql
│
├── soar_playbooks/
│   ├── splunk_soar/
│   │   ├── ip_enrichment.json
│   │   ├── jira_ticket_creation.json
│   ├── tines/
│       ├── vt_enrichment_story.json
│
├── cribls/
│   ├── pipelines/
│   │   ├── filter_logs.json
│   │   ├── normalize_syslog.json
│
├── docs/
│   ├── architecture_diagram.png
│   ├── weekly_progress.md
│   ├── detection_templates.md
│   ├── soar_workflow_notes.md
│
└── README.md
```

---

##  Folder Purpose

### `detections/`

Splunk SPL and CrowdStrike Falcon Query Language (FQL) rules.

* **splunk/** — Detection rules, dashboards, and correlation searches.
* **crowdstrike/** — FQL detections for process creation, network activity, and IOC hunting.

### `soar_playbooks/`

Automation workflows for Splunk SOAR and Tines.

* `ip_enrichment.json` — Example playbook that looks up IP reputation with VirusTotal.
* `jira_ticket_creation.json` — Playbook for automatically opening a Jira incident.

### `cribls/`

Cribl Stream pipelines and route definitions for filtering and routing log data.

### `docs/`

Documentation, architecture diagrams, and your weekly notes.
Start with:

* `weekly_progress.md` — A short summary of what you did each week.
* `detection_templates.md` — Template for documenting detection rules.
* `soar_workflow_notes.md` — Description of SOAR automations and lessons learned.

---

##  Suggested Use

1. Clone this repository:

   ```bash
   git clone https://github.com/<yourusername>/cybersecurity-lab.git
   cd cybersecurity-lab
   ```

2. As you complete each week’s labs:

   * Add SPL or FQL rules to `detections/`.
   * Export SOAR playbooks as JSON and save them in `soar_playbooks/`.
   * Update `docs/weekly_progress.md` with screenshots and notes.

3. Commit your changes:

   ```bash
   git add .
   git commit -m "Week 4 - Added failed login detection and dashboard"
   git push origin main
   ```

4. At the end of Week 12, include your full architecture diagram and a summary of the automated response project.

---

##  Example Detection Template (`docs/detection_templates.md`)

| Field               | Description                                               |
| ------------------- | --------------------------------------------------------- |
| **Detection Name**  | PowerShell Execution Detection                            |
| **Technology**      | Splunk                                                    |
| **Query**           | `index=windows EventCode=4688 CommandLine="*powershell*"` |
| **MITRE ATT&CK ID** | T1059 – Command and Scripting Interpreter                 |
| **Severity**        | High                                                      |
| **Response**        | Trigger SOAR playbook to enrich IP and open Jira ticket   |
| **Test Data**       | Simulated PowerShell commands in Windows VM               |

---

##  Example SOAR Playbook Summary (`docs/soar_workflow_notes.md`)

**Name:** IP Enrichment & Jira Ticket
**Trigger:** Splunk alert for suspicious IP activity
**Actions:**

1. VirusTotal IP reputation check
2. Create Jira ticket if malicious
3. Post to Slack “Security-Alerts” channel

---

##  End Goal

By the end of the 12-week program, this repository will include:

* 3+ custom detections (SPL/FQL)
* 2+ SOAR playbooks
* 1 full “Automated Threat Response” architecture
* Weekly documentation and screenshots

Use this repo in interviews to showcase your hands-on security engineering skills.
