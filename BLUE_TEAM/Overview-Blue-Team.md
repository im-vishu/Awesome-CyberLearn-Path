# 🛡️ Blue Team — Defensive Security Track

Welcome to the **Blue Team** section — your guide to mastering the defensive side of cybersecurity.
This track focuses on **detection engineering**, **log analysis**, **SIEM setup**, and **incident response playbooks** — the backbone of every modern Security Operations Center (SOC).

---

## 🎯 Purpose

The goal here is simple: help you think, act, and respond like a SOC Analyst or Security Engineer.
By following these guides, you’ll learn how to:

* Detect suspicious activity across systems and networks.
* Investigate alerts and respond to real incidents.
* Build dashboards and correlation rules in SIEMs.
* Automate repetitive tasks using scripts and APIs.

---

## 🧭 Learning Path

| Stage                         | Focus                                        | Example Labs                                                                  |
| ----------------------------- | -------------------------------------------- | ----------------------------------------------------------------------------- |
| **1️⃣ Foundation**            | Log sources, Sysmon, Event IDs, MITRE ATT&CK | TryHackMe: [SOC Level 1 Path](https://tryhackme.com/path/outline/soc-level-1) |
| **2️⃣ Monitoring**            | ELK, Wazuh, Splunk dashboards                | [Wazuh Docs](https://documentation.wazuh.com/)                                |
| **3️⃣ Detection Engineering** | Correlation rules, Sigma/YARA                | [SigmaHQ](https://github.com/SigmaHQ/sigma)                                   |
| **4️⃣ Incident Response**     | Playbooks, containment steps, triage         | [Blue Team Labs Online](https://blueteamlabs.online)                          |
| **5️⃣ Automation**            | SOAR, Python scripts for alerts              | [Shuffle SOAR](https://shuffler.io/)                                          |

---

## 🧰 Tools & Platforms

| Category          | Tool             | Link                                                         |
| ----------------- | ---------------- | ------------------------------------------------------------ |
| SIEM              | Splunk           | [splunk.com](https://www.splunk.com)                         |
| SIEM              | Wazuh            | [wazuh.com](https://wazuh.com)                               |
| Log Analysis      | ELK Stack        | [elastic.co](https://www.elastic.co)                         |
| Detection         | Sigma Rules      | [github.com/SigmaHQ/sigma](https://github.com/SigmaHQ/sigma) |
| Threat Hunting    | Velociraptor     | [velociraptor.app](https://www.velociraptor.app)             |
| Incident Response | TheHive & Cortex | [thehive-project.org](https://thehive-project.org)           |

---

## 📘 Folder Contents

| File                                                     | Description                                   |
| -------------------------------------------------------- | --------------------------------------------- |
| [`siem-and-monitoring.md`](./siem-and-monitoring.md)     | Build, configure, and analyze SIEM dashboards |
| [`detection-engineering.md`](./detection-engineering.md) | Write Sigma rules and tune detections         |
| [`incident-playbooks.md`](./incident-playbooks.md)       | Real-world response workflows for SOC teams   |

---

## 🧠 Pro Tips for Blue Teamers

* Always tag your findings with **MITRE ATT&CK technique IDs**.
* Log everything, even failed events — they tell hidden stories.
* Focus on *understanding attacker behavior*, not just alerts.
* Keep a small lab running — it’s your best teacher.

> Offense inspires creativity. Defense builds resilience.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
