# 📊 SIEM & Monitoring — Building Your Detection Pipeline

Security Information and Event Management (SIEM) tools are the heart of modern Blue Team operations. They collect logs, correlate alerts, and help analysts detect suspicious activity in real time.

This guide shows how to start small — with local labs — and gradually move toward enterprise-grade setups using open tools like **Wazuh**, **ELK Stack**, and **Splunk Free**.

---

## 🎯 Learning Objectives

By the end of this module, you’ll be able to:

* Ingest and normalize logs from different systems (Windows, Linux, network).
* Build dashboards and correlation searches.
* Investigate alerts using MITRE ATT&CK mappings.
* Automate alert triage with scripting or SOAR tools.

---

## 🧰 Recommended Tools

| Tool                           | Description                                                 | Link                                                             |
| ------------------------------ | ----------------------------------------------------------- | ---------------------------------------------------------------- |
| **Splunk Free / Splunk Cloud** | Industry-leading SIEM with rich dashboarding                | [splunk.com](https://www.splunk.com)                             |
| **Wazuh**                      | Open-source SIEM built on ELK Stack                         | [wazuh.com](https://wazuh.com)                                   |
| **Elastic Stack (ELK)**        | Log collection, search, and visualization                   | [elastic.co](https://www.elastic.co)                             |
| **Graylog**                    | Open-source alternative for log management                  | [graylog.org](https://www.graylog.org)                           |
| **Security Onion**             | All-in-one monitoring distro (includes Zeek, Suricata, ELK) | [securityonionsolutions.com](https://securityonionsolutions.com) |

---

## ⚙️ Lab Setup Options

1. **Local VM Setup** — Use Wazuh or Splunk in a single-node Ubuntu VM.
2. **Docker Deployment** — Launch ELK or Graylog containers for quick testing.
3. **Cloud Setup** — Use free-tier instances (AWS, Azure) to collect remote system logs.

Example for Wazuh Docker setup:

```bash
git clone https://github.com/wazuh/wazuh-docker.git
cd wazuh-docker/docker-compose
sudo docker-compose -f generate-indexer-certs.yml run --rm generator
sudo docker-compose up -d
```

Then access your dashboard at: `https://localhost:5601`

---

## 🔍 Key Monitoring Use Cases

| Use Case                 | Log Source                | Example Query / Action                         |
| ------------------------ | ------------------------- | ---------------------------------------------- |
| **Failed Logins**        | Windows Security / Syslog | `EventCode=4625 OR syslog.severity=error`      |
| **Privilege Escalation** | Sysmon / Linux auth.log   | `process_name=sudo OR winlog.event_id=4672`    |
| **Web Attacks**          | Apache / Nginx Logs       | `uri_path="/wp-admin" AND status=403`          |
| **Malware Beaconing**    | Network Flow Logs         | `destination_port=443 AND bytes_out > 1000000` |

---

## 🧠 Correlation Rules (MITRE ATT&CK)

| Technique                     | Description                       | Example Detection                                            |
| ----------------------------- | --------------------------------- | ------------------------------------------------------------ |
| **T1059 — Command Execution** | Suspicious PowerShell or Bash use | `process_name=powershell.exe AND command_line LIKE 'Invoke'` |
| **T1078 — Valid Accounts**    | Brute-force or reused credentials | Multiple login failures followed by success                  |
| **T1566 — Phishing**          | User clicked malicious link       | Email URL + proxy logs + DNS query correlation               |

> Learn to think in **attack chains** — each detection rule is one link that helps you reconstruct the full story.

---

## 🧩 Suggested Mini Projects

* Build a dashboard showing top 10 failed logins by IP.
* Create an alert for new administrative accounts.
* Visualize SSH activity by country using GeoIP data.
* Connect Wazuh → TheHive → Shuffle to automate incident escalation.

---

## 📚 Recommended Learning Resources

* [Wazuh Documentation](https://documentation.wazuh.com/)
* [Elastic Security Labs Blog](https://www.elastic.co/security-labs)
* [Splunk Security Use Case Library](https://lantern.splunk.com/)
* [MITRE ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/)

> A great Blue Teamer doesn’t just collect logs — they make the data tell a story.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
