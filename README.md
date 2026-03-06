# MASLA — Multi‑Agent Security Log Analyzer

MASLA is a lightweight, defensive‑only cybersecurity project that analyzes Windows Security Logs and Sysmon telemetry using a multi‑agent architecture. It detects suspicious authentication activity, process execution, network behavior, and multi‑stage attack patterns.

MASLA is safe to run on any machine because it only processes log files. It does **not** execute code, interact with endpoints, or perform offensive actions.

---

## Features

- Multi‑agent pipeline:
  - Parser Agent  normalizes Windows Security + Sysmon logs
  - Anomaly Agent  applies detection rules
  - Intel Agent  enriches indicators using a local JSON feed
  - Report Agent  generates a human‑readable security report

- Starter rule set:
  - Authentication anomalies (4624, 4625, 4672)
  - Suspicious process execution (Sysmon Event ID 1)
  - External network connections (Sysmon Event ID 3)
  - Multi‑stage correlations (e.g., failed logons → encoded PowerShell)

- Safe, offline‑friendly threat‑intel enrichment

- Sample logs included for instant testing

---

## Installation

```bash
git clone https://github.com/sentinelLLM/masla.git
cd masla
pip install -r requirements.txt
