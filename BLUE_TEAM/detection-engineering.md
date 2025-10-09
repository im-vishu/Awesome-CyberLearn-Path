# 🧠 Detection Engineering — Turning Data into Defense

Detection engineering bridges the gap between raw logs and actionable alerts. In this guide, you’ll learn to design, test, and tune detection rules using **Sigma**, **YARA**, and **MITRE ATT&CK** frameworks.

---

## 🎯 Goal

Understand how to translate attacker behavior (TTPs) into detections that trigger only when something truly suspicious happens.

**Outcome:** You’ll know how to:

* Write platform-agnostic detection rules.
* Map detections to ATT&CK techniques.
* Reduce false positives through tuning and context.

---

## 🧰 Core Tools

| Tool                         | Description                                     | Link                                                                                        |
| ---------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Sigma**                    | Generic detection rule format for SIEMs         | [github.com/SigmaHQ/sigma](https://github.com/SigmaHQ/sigma)                                |
| **YARA**                     | Pattern-matching tool for file and memory scans | [virustotal.github.io/yara](https://virustotal.github.io/yara/)                             |
| **ATT&CK Navigator**         | Visual map for MITRE techniques                 | [mitre-attack.github.io/attack-navigator](https://mitre-attack.github.io/attack-navigator/) |
| **Sigma Converter (sigmac)** | Converts Sigma rules to Splunk/ELK/Wazuh syntax | [github.com/SigmaHQ/sigma](https://github.com/SigmaHQ/sigma)                                |
| **Elastic Detections Repo**  | Prebuilt Sigma-based detections for Elastic     | [github.com/elastic/detection-rules](https://github.com/elastic/detection-rules)            |

---

## 🧩 Sigma Rule Structure

A Sigma rule describes **what to detect**, **where to detect it**, and **why it matters.**

Example — detect suspicious PowerShell use:

```yaml
title: Suspicious PowerShell Invocation
description: Detects use of PowerShell with encoded commands.
logsource:
  product: windows
  service: security
detection:
  selection:
    EventID: 4104
    ScriptBlockText|contains: 'FromBase64String'
  condition: selection
level: medium
tags:
  - attack.t1059.001
  - attack.execution
```

**Key sections:**

* `logsource` → defines where the data comes from.
* `detection` → pattern you’re looking for.
* `tags` → map to MITRE ATT&CK for classification.

---

## 🧱 YARA Rule Example

```yara
rule Suspicious_Encoded_Script {
  meta:
    description = "Detects Base64-encoded PowerShell payloads"
    author = "Vishant Chaudhary"
  strings:
    $b64 = /[A-Za-z0-9+/]{200,}={0,2}/
  condition:
    $b64 and filesize < 500KB
}
```

This rule flags unusually large Base64 blobs that may indicate encoded payloads.

---

## ⚙️ Rule Tuning Process

1. **Start broad** — Write a generic detection that might capture multiple cases.
2. **Validate** — Run against known clean and malicious logs.
3. **Add context** — Include process parents, user names, or paths to reduce noise.
4. **Map to ATT&CK** — Identify the Tactic/Technique (e.g., *Execution: PowerShell* → T1059.001).
5. **Document every rule** — include purpose, test data, and false positive notes.

---

## 🧪 Practice Labs

* [TryHackMe — Detection Engineering Room](https://tryhackme.com/room/detectionengineering)
* [SigmaHQ — Rule Testing Repo](https://github.com/SigmaHQ/sigma/wiki/Testing)
* [Elastic Detection Rules Repo](https://github.com/elastic/detection-rules)
* [Flare VM + Sysmon Lab](https://github.com/mandiant/flare-vm)

---

## 🧠 Pro Tips

* Start every detection with a **hypothesis** (“If an attacker did X, how would I see it?”).
* Maintain a private **detections registry** for your team or portfolio.
* Track **detection coverage vs. MITRE ATT&CK matrix** — aim for completeness, not just alerts.
* Build one new rule each week — consistency compounds mastery.

> Detection engineering isn’t about writing rules — it’s about understanding behavior well enough to translate it into logic.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
