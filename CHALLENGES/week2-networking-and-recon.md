# 🌐 Week 2 — Networking & Reconnaissance Fundamentals

## 🎯 Goal

Learn the essentials of network scanning, reconnaissance, and traffic analysis. You’ll use common tools to discover hosts, analyze open ports, and interpret network behavior like a junior analyst or pentester.

**Outcome:** You’ll be able to identify network assets, understand communication flow, and analyze potential attack surfaces safely in a lab environment.

---

## ⏱ Duration

4–6 hours (split across 2–3 sessions)

---

## 🧰 Tools & Setup

| Tool           | Purpose            | Link                                                                                  |
| -------------- | ------------------ | ------------------------------------------------------------------------------------- |
| Nmap           | Network scanning   | [nmap.org](https://nmap.org)                                                          |
| Wireshark      | Packet analysis    | [wireshark.org](https://www.wireshark.org)                                            |
| Netcat (nc)    | Manual connections | [nmap.org/ncat](https://nmap.org/ncat/)                                               |
| TryHackMe Room | Guided labs        | [TryHackMe — Network Fundamentals](https://tryhackme.com/module/network-fundamentals) |
| TCPDump        | CLI packet capture | [tcpdump.org](https://www.tcpdump.org)                                                |

---

## 🧪 Tasks

1. **Basic network scan:** Use `nmap -sP <target-subnet>` to find active hosts.
2. **Service discovery:** Run `nmap -sV -p- <target-ip>` and document running services.
3. **Banner grabbing:** Use `nc <target-ip> 80` to connect manually and read HTTP headers.
4. **Traffic capture:** Capture 2 minutes of network traffic using Wireshark or `tcpdump -i eth0 -w capture.pcap`. Identify top 3 protocols used.
5. **Analyze connections:** Filter TCP vs UDP packets and note differences.
6. **Bonus:** Identify open SSH or RDP ports on a test lab and explain what each service does.

---

## 💡 Hints

* Use `nmap -A` for aggressive scanning (OS + service detection).
* Wireshark filter example: `tcp.port == 80` or `ip.addr == 10.10.1.5`.
* Always document the `command + purpose + result` format — it builds your report-writing habit early.

---

## 📦 Deliverables

* A short Markdown report (`network-scan-report.md`) containing:

  * Discovered IPs and open ports
  * Top 5 protocols seen in traffic capture
  * Observations from banner grabbing
* Screenshot(s) of Wireshark filters or Nmap results.

---

## 📚 Recommended Resources

* [TryHackMe — Network Fundamentals](https://tryhackme.com/module/network-fundamentals)
* [Wireshark Labs](https://wiki.wireshark.org/SampleCaptures)
* [Nmap Network Scanning Book (Free)](https://nmap.org/book/)
* [Practical Networking YouTube Channel](https://www.youtube.com/@PracticalNetworking)

---

## 🧠 Reflection

At the end of this week, you should be able to:

* Scan and identify live hosts and open ports.
* Capture and interpret network traffic.
* Document and explain what common protocols (HTTP, SSH, DNS) do.

> Reconnaissance is where every attack — and every defense — begins. Learn to see the network before anyone else does.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
