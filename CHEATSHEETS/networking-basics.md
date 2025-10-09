# 🌐 Networking Basics Cheatsheet for Cybersecurity Learners

This cheatsheet helps you understand networking essentials every cybersecurity learner must know — from IP layers to packet analysis. It’s your quick-start guide for network defense and offense.

---

## 🧭 OSI Model (7 Layers)

| Layer            | Function                     | Example Protocols           |
| ---------------- | ---------------------------- | --------------------------- |
| 7️⃣ Application  | User-facing communication    | HTTP, HTTPS, DNS, FTP, SMTP |
| 6️⃣ Presentation | Data formatting & encryption | SSL/TLS, MIME               |
| 5️⃣ Session      | Manages sessions             | NetBIOS, RPC                |
| 4️⃣ Transport    | Reliable delivery            | TCP, UDP                    |
| 3️⃣ Network      | Routing, addressing          | IP, ICMP                    |
| 2️⃣ Data Link    | MAC addressing, switching    | Ethernet, ARP               |
| 1️⃣ Physical     | Transmission media           | Cables, Wi-Fi               |

**Mnemonic:** *All People Seem To Need Data Processing* 🧠

---

## 🔢 Common Ports & Services

| Port   | Protocol       | Description              |
| ------ | -------------- | ------------------------ |
| 20, 21 | FTP            | File Transfer Protocol   |
| 22     | SSH            | Secure Shell             |
| 23     | Telnet         | Remote access (insecure) |
| 25     | SMTP           | Mail transfer            |
| 53     | DNS            | Domain Name System       |
| 80     | HTTP           | Web traffic              |
| 110    | POP3           | Mail retrieval           |
| 143    | IMAP           | Mail access              |
| 443    | HTTPS          | Secure web traffic       |
| 3389   | RDP            | Remote Desktop Protocol  |
| 8080   | Alternate HTTP |                          |

**Tip:** Learn to recognize these ports when scanning or analyzing traffic — it saves time during triage.

---

## 🧰 Networking Commands (Linux/Windows)

| Task                       | Command                                        |
| -------------------------- | ---------------------------------------------- |
| Show network interfaces    | `ip addr show` / `ifconfig`                    |
| Display routing table      | `route -n` / `ip route`                        |
| Ping a host                | `ping -c 4 target.com`                         |
| DNS lookup                 | `nslookup target.com` / `dig target.com`       |
| Traceroute                 | `traceroute target.com` / `tracert target.com` |
| Capture packets            | `tcpdump -i eth0 -w capture.pcap`              |
| Analyze packets            | `wireshark capture.pcap`                       |
| View open ports            | `netstat -tuln` / `ss -tuln`                   |
| Check connection to a port | `nc -zv target 80`                             |

---

## 📡 Network Analysis Tips

* Always identify **source/destination IPs** and **protocols** first.
* Look for **unusual ports**, **large data transfers**, or **frequent failed logins**.
* Use filters in Wireshark (e.g., `http`, `tcp.port==443`, `ip.addr==10.0.0.5`).
* Save filtered captures for reports (`File → Export Specified Packets`).

---

## 🧩 Subnetting Basics

| CIDR | Subnet Mask     | # Hosts | Example Range               |
| ---- | --------------- | ------- | --------------------------- |
| /24  | 255.255.255.0   | 254     | 192.168.1.0 – 192.168.1.255 |
| /25  | 255.255.255.128 | 126     | 192.168.1.0 – 192.168.1.127 |
| /26  | 255.255.255.192 | 62      | 192.168.1.0 – 192.168.1.63  |
| /30  | 255.255.255.252 | 2       | Point-to-point links        |

**Quick Check:**

```bash
ipcalc 192.168.1.0/24
```

---

## 🔐 Common Network Attacks

| Attack        | Description                      | Prevention                  |
| ------------- | -------------------------------- | --------------------------- |
| ARP Spoofing  | Redirecting traffic via fake MAC | Use static ARP entries, IDS |
| DNS Spoofing  | Fake DNS replies                 | DNSSEC, trusted resolvers   |
| MITM          | Intercepting communication       | HTTPS, VPNs                 |
| DDoS          | Flooding network resources       | Firewalls, rate limiting    |
| Port Scanning | Recon of open ports              | IDS/IPS, rate limits        |

---

## 📘 Tools to Master

| Purpose          | Tool                  | Link                                                   |
| ---------------- | --------------------- | ------------------------------------------------------ |
| Packet capture   | Wireshark             | [wireshark.org](https://www.wireshark.org)             |
| CLI analyzer     | tcpdump               | [tcpdump.org](https://www.tcpdump.org)                 |
| Network scanning | Nmap                  | [nmap.org](https://nmap.org)                           |
| Recon            | netdiscover, arp-scan | [tools.kali.org](https://tools.kali.org)               |
| Traffic replay   | tcpreplay             | [tcpreplay.appneta.com](https://tcpreplay.appneta.com) |

---

## 🧠 Pro Tips for Learners

* Draw network topologies for every lab you do.
* Always validate which interface you’re analyzing (`eth0`, `wlan0`, etc.).
* Learn to read **packet headers** — it’s 80% of network analysis.
* Practice filtering noisy captures — clarity comes from pattern recognition.

> In cybersecurity, networking isn’t a topic — it’s the foundation of everything.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
