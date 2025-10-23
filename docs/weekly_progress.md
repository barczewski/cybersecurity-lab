#  Weekly Progress Tracker

This document tracks weekly progress for the Cybersecurity Lab portfolio.

---

## Week 1 — Splunk Setup & First Detection

**Goal:** Install Splunk locally and ingest sample logs.
**Tasks:**

* Install Splunk Enterprise or Splunk Free in a VM or container.
* Ingest `/var/log/secure` or sample Windows Event logs.
* Create and test your first SPL query (failed logins).
* Save detection to `detections/splunk/failed_logins.spl`.
* Document the detection in `docs/detection_templates.md`.

**Outcome:** First working Splunk detection with screenshots.

---

## Week 2 — Cribl Log Routing

**Goal:** Install and configure Cribl Stream.
**Tasks:**

* Route Syslog or Windows Event logs to Splunk via Cribl.
* Create a pipeline to filter and normalize data.
* Save pipeline JSON to `cribls/pipelines/filter_logs.json`.
* Document lessons learned.

**Outcome:** Logs successfully routed and enriched before reaching Splunk.

---

## Week 3 — CrowdStrike Query Practice

**Goal:** Learn and test FQL (Falcon Query Language).
**Tasks:**

* Use the CrowdStrike Falcon console (or demo dataset).
* Build queries for process creation, network activity, or IOC searches.
* Save queries to `detections/crowdstrike/*.fql`.

**Outcome:** Understand how to hunt threats using FQL syntax.

---

## Week 4 — Splunk SOAR Setup

**Goal:** Automate alert response using Splunk SOAR.
**Tasks:**

* Install Splunk SOAR (VM or cloud).
* Connect to Splunk via REST API.
* Create “IP Enrichment” playbook (VirusTotal lookup).
* Save playbook JSON to `soar_playbooks/splunk_soar/ip_enrichment.json`.

**Outcome:** Automatic enrichment triggered by Splunk alerts.

---

## Week 5 — Jira Integration

**Goal:** Automate ticket creation from SOAR alerts.
**Tasks:**

* Integrate SOAR with Jira Cloud.
* Build playbook: Enrich IOC → Create Jira ticket → Slack notification.
* Document workflow in `docs/soar_workflow_notes.md`.

**Outcome:** Automated incident tickets for validated detections.

---

*(Continue through Week 12 with additional detections, automation, and documentation.)*
