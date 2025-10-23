#  Detection Templates

Use this template to document every detection or correlation search you create.

| Field                 | Description                                               |
| --------------------- | --------------------------------------------------------- |
| **Detection Name**    | Example: PowerShell Execution Detection                   |
| **Technology**        | Splunk / CrowdStrike                                      |
| **Query**             | `index=windows EventCode=4688 CommandLine="*powershell*"` |
| **MITRE ATT&CK ID**   | T1059 — Command and Scripting Interpreter                 |
| **Severity**          | High                                                      |
| **Response Action**   | Trigger SOAR playbook for enrichment and ticket creation  |
| **Validation Method** | Simulated process execution in test VM                    |
| **Created On**        | 2025-10-21                                                |
| **Author**            | Tim Barczewski                                            |

---

### Example: Failed Login Attempts (Splunk)

```spl
index=windows EventCode=4625
| stats count by user, src_ip
| where count > 5
```

**Purpose:** Detect repeated failed logins (potential brute-force).
**Response:** Trigger Splunk SOAR IP enrichment and blocklist workflow.
