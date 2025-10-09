# 🌐 Network & Traffic Analysis Datasets

This section provides open datasets and safe PCAPs (packet captures) for practicing **network traffic analysis, intrusion detection, and SOC monitoring**. These are ideal for blue team labs, ML research, or defensive engineering projects.

---

## ⚠️ Safety & Ethics

* Analyze all traffic captures in **offline environments** (Wireshark, Zeek, etc.).
* Avoid connecting live malware or exploit PCAPs to the internet.
* Respect dataset licensing terms — most are for research or educational use.

---

## 🧰 Public PCAP Repositories

| Dataset                                                 | Description                                          | Link                                                                                 |
| ------------------------------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Wireshark Sample Captures**                           | Hundreds of clean PCAPs for protocol study           | [wiki.wireshark.org/SampleCaptures](https://wiki.wireshark.org/SampleCaptures)       |
| **Malware-Traffic-Analysis.net**                        | Real-world malicious network captures (safe offline) | [malware-traffic-analysis.net](https://www.malware-traffic-analysis.net)             |
| **Contagio Malware Dump**                               | PCAPs, malware docs, and network artifacts           | [contagiodump.blogspot.com](http://contagiodump.blogspot.com)                        |
| **PacketTotal**                                         | Web-based PCAP analysis platform                     | [packettotal.com](https://packettotal.com)                                           |
| **Stratosphere IPS Dataset (CTU-13)**                   | Botnet traffic dataset with labels                   | [stratosphereips.org/datasets-ctu13](https://www.stratosphereips.org/datasets-ctu13) |
| **CIC-IDS 2017 (Canadian Institute for Cybersecurity)** | Labeled IDS dataset for ML and SIEM                  | [unb.ca/cic/datasets/ids-2017.html](https://www.unb.ca/cic/datasets/ids-2017.html)   |

---

## 📡 IDS / IPS Datasets

| Dataset                | Focus                               | Link                                                                               |
| ---------------------- | ----------------------------------- | ---------------------------------------------------------------------------------- |
| **UNSW-NB15 Dataset**  | Modern IDS dataset with 49 features | [unsw.adfa.edu.au](https://research.unsw.edu.au/projects/unsw-nb15-dataset)        |
| **KDD Cup 99 Dataset** | Classic intrusion detection dataset | [kdd.ics.uci.edu](https://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)        |
| **NSL-KDD Dataset**    | Cleaner version of KDD99            | [nsl.cs.unb.ca/nsl-kdd](https://www.unb.ca/cic/datasets/nsl.html)                  |
| **CSE-CIC-IDS 2018**   | Updated multi-attack IDS dataset    | [unb.ca/cic/datasets/ids-2018.html](https://www.unb.ca/cic/datasets/ids-2018.html) |

---

## 🧩 Suggested Research Projects

* **Visualize Network Attacks:** Import CTU-13 dataset into ELK Stack or Kibana and map attack flow.
* **Train an IDS model:** Use NSL-KDD or CIC-IDS 2017 with Python & Scikit-Learn.
* **Detect anomalies:** Apply Zeek (Bro) scripts to large PCAPs to flag C2 traffic.
* **Build dashboards:** Parse traffic logs into Splunk or Graylog for SOC visualization.

---

## 📚 Tools for Analysis

| Tool               | Purpose                                    | Link                                                                           |
| ------------------ | ------------------------------------------ | ------------------------------------------------------------------------------ |
| **Wireshark**      | Deep packet analysis                       | [wireshark.org](https://www.wireshark.org)                                     |
| **Zeek (Bro)**     | Network monitoring & scripting             | [zeek.org](https://zeek.org)                                                   |
| **Suricata**       | IDS/IPS & traffic monitoring               | [suricata.io](https://suricata.io)                                             |
| **Security Onion** | Blue team distro for log & packet analysis | [securityonionsolutions.com](https://securityonionsolutions.com)               |
| **NetworkMiner**   | Forensics analysis of PCAPs                | [netresec.com/?page=NetworkMiner](https://www.netresec.com/?page=NetworkMiner) |

---

## 🧠 Pro Tips

* Focus on **patterns** (source IPs, ports, payload size, timing).
* Label normal vs. malicious traffic early — it trains your analysis intuition.
* Write small Zeek or Suricata rules to detect repeating patterns.

> Logs tell what happened. Packets tell *how* it happened.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
