# 📧 Phishing & Email Security Datasets

This section curates **open phishing, spam, and email security datasets** to help you practice detection, analysis, and machine learning classification. Perfect for Blue Teamers, analysts, and security data scientists.

---

## ⚠️ Safe Use Reminder

* Do not send or forward any dataset emails to live accounts — handle data **offline**.
* Many corpora contain **synthetic or anonymized** email samples.
* When using URLs or attachments, never open them in an unprotected system — use a VM or sandbox.

---

## 🧰 Public Phishing Datasets

| Dataset                                                      | Description                                        | Link                                                                               |
| ------------------------------------------------------------ | -------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **PhishTank**                                                | Verified community-submitted phishing URLs         | [phishtank.org](https://phishtank.org)                                             |
| **OpenPhish (Free Feed)**                                    | Continuously updated phishing URLs feed            | [openphish.com](https://openphish.com)                                             |
| **CIC-Phishing 2019 (Canadian Institute for Cybersecurity)** | Complete labeled phishing vs. benign dataset       | [unb.ca/cic/datasets/phishing.html](https://www.unb.ca/cic/datasets/phishing.html) |
| **APWG eCrime Exchange (Academic Access)**                   | Large phishing URL and payload repository          | [apwg.org/ecx](https://apwg.org/ecx/)                                              |
| **PhishStats.info API**                                      | JSON feed of phishing indicators (IP, domain, ASN) | [phishstats.info](https://phishstats.info)                                         |

---

## 📬 Spam & Email Corpora

| Dataset                               | Description                               | Link                                                                                                                   |
| ------------------------------------- | ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Enron Email Dataset**               | Real corporate email dataset (anonymized) | [kaggle.com/wcukierski/enron-email-dataset](https://www.kaggle.com/datasets/wcukierski/enron-email-dataset)            |
| **SpamAssassin Public Corpus**        | Clean dataset of spam and ham emails      | [spamassassin.apache.org/publiccorpus](https://spamassassin.apache.org/publiccorpus/)                                  |
| **LingSpam Dataset**                  | Simple labeled spam/ham dataset           | [nlp.cs.aueb.gr/software_and_datasets/lingspam_public.tar.gz](https://www.cs.aueb.gr/~ion/data/lingspam_public.tar.gz) |
| **SMS Spam Collection Dataset (UCI)** | SMS-based spam detection dataset          | [archive.ics.uci.edu/ml/datasets/sms+spam+collection](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection)     |

---

## 📊 Suggested ML & SOC Projects

* **Train a spam filter** using the Enron or SpamAssassin corpus with Python & Scikit-Learn.
* **Visualize phishing domains** using data from PhishTank + OpenPhish.
* **Automate IOC enrichment** by querying PhishStats API for each domain.
* **Detect anomalies in subject lines** using NLP embeddings (TF-IDF, BERT).

---

## 🧠 Tools for Email & Phishing Analysis

| Tool                               | Purpose                                           | Link                                                                 |
| ---------------------------------- | ------------------------------------------------- | -------------------------------------------------------------------- |
| **MSTICPy**                        | Threat intelligence enrichment & visualization    | [github.com/microsoft/msticpy](https://github.com/microsoft/msticpy) |
| **TheHive Project**                | Incident response platform with email correlation | [thehive-project.org](https://thehive-project.org)                   |
| **MailParser.io (API)**            | Extract structured data from email headers        | [mailparser.io](https://mailparser.io)                               |
| **Cuckoo Sandbox (Email Plugins)** | Analyze attachments in isolated VM                | [cuckoosandbox.org](https://cuckoosandbox.org)                       |

---

## 📚 Research & Learning References

* [MITRE ATT&CK — Phishing Technique (T1566)](https://attack.mitre.org/techniques/T1566/)
* [Google Safe Browsing Transparency Report](https://transparencyreport.google.com/safe-browsing/overview)
* [SANS Phishing Response Guide (PDF)](https://www.sans.org/white-papers/3983/)

---

> Phishing attacks are about human trust. Study the patterns, not just the payloads.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
