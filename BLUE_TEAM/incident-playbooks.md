# 🚨 Incident Response Playbooks — Act Fast, Stay Calm

Incident response (IR) is where detection meets action.
These playbooks provide structured, repeatable workflows to handle the most common security incidents in a SOC or enterprise environment.

Each playbook follows the **NIST IR lifecycle**:

1. **Preparation** — Train, configure tools, and establish baselines.
2. **Identification** — Detect and confirm the incident.
3. **Containment** — Limit the impact.
4. **Eradication** — Remove the threat.
5. **Recovery** — Restore services safely.
6. **Lessons Learned** — Document, improve, repeat.

---

## 🧩 Playbook 1 — Phishing Email

| Phase        | Steps                      |
| ------------ | -------------------------- |
| **Identify** | - Alert from user or SIEM. |

* Collect email headers and attachments.  |
  | **Contain** | - Block sender domain in email gateway.
* Quarantine similar emails.  |
  | **Eradicate** | - Remove phishing emails from all inboxes.
* Check user machines for malicious payloads.  |
  | **Recover** | - Reset credentials of affected users.  |
  | **Lessons Learned** | - Update spam filters.
* Conduct awareness training.  |

🧰 **Tools:** Outlook header analyzer, VirusTotal, PhishTool, TheHive.

---

## 💻 Playbook 2 — Ransomware Attack

| Phase        | Steps                                        |
| ------------ | -------------------------------------------- |
| **Identify** | - Detect encryption activity or ransom note. |

* Review endpoint logs for initial infection vector.  |
  | **Contain** | - Isolate affected endpoints immediately (network disconnect).
* Block C2 domains/IPs.  |
  | **Eradicate** | - Remove malware using EDR tools (CrowdStrike, Defender ATP).
* Restore clean images from backups.  |
  | **Recover** | - Verify system integrity.
* Reconnect machines to network in phases.  |
  | **Lessons Learned** | - Audit backup policy.
* Patch exploited vulnerabilities.  |

🧰 **Tools:** Wazuh, ELK, Velociraptor, Any.Run, CyberChef.

---

## 🔐 Playbook 3 — Privilege Escalation / Insider Threat

| Phase        | Steps                                                      |
| ------------ | ---------------------------------------------------------- |
| **Identify** | - Detect new admin accounts or unauthorized privilege use. |
| **Contain**  | - Suspend affected accounts.                               |

* Review group membership and role assignments.  |
  | **Eradicate** | - Remove rogue accounts or policies.
* Revoke unnecessary privileges.  |
  | **Recover** | - Rebuild trust with new credentials and MFA.  |
  | **Lessons Learned** | - Enhance role-based access control.
* Review audit logs for policy gaps.  |

🧰 **Tools:** Splunk, AD Audit, BloodHound, Sysmon.

---

## 🌐 Playbook 4 — Web Server Compromise

| Phase         | Steps                                                    |
| ------------- | -------------------------------------------------------- |
| **Identify**  | - Alert from WAF or SIEM for unusual traffic or uploads. |
| **Contain**   | - Disable affected web service or isolate container.     |
| **Eradicate** | - Replace compromised files from backup.                 |

* Patch CMS/plugins.  |
  | **Recover** | - Verify web content integrity.
* Enable monitoring for abnormal requests.  |
  | **Lessons Learned** | - Strengthen input validation.
* Add WAF rules for prevention.  |

🧰 **Tools:** Wazuh, OWASP ModSecurity, ELK, ClamAV.

---

## 📦 Deliverable Template — IR Report

```markdown
# Incident Report — <Incident Name>

## Summary
Short description (who, what, when, impact).

## Timeline
| Time | Event | Source |
|------|--------|--------|
| 09:21 | Alert triggered from Wazuh | SIEM |
| 09:23 | User confirmed phishing email | Outlook |
| 09:30 | Containment initiated | SOC |

## Root Cause
Describe the weakness exploited.

## Lessons Learned
Bullet points on how to prevent recurrence.
```

---

## 📚 Recommended References

* [NIST Computer Security Incident Handling Guide (SP 800-61r2)](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)
* [MITRE ATT&CK for Incident Response](https://attack.mitre.org/)
* [SANS IR Poster](https://www.sans.org/posters/incident-response/)
* [TheHive + Cortex Workflow Guide](https://thehive-project.org/)

> Incident response is about discipline, not panic — the more you practice, the calmer you act when it counts.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
