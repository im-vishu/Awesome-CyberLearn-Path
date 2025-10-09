# 🔎 Reconnaissance & Enumeration — Practical Guide (Lab-Only)

> Mentor-style guide for safe, effective recon. Only run these commands and workflows inside authorized labs (TryHackMe, HackTheBox, VulnHub) or on targets you own and have written permission to test.

---

## 🎯 Purpose

Reconnaissance (recon) is where every successful security engagement starts.
This guide teaches you how to gather useful information about a target, prioritize findings, and produce a compact recon report recruiters and clients actually read.

**Outcome:** You'll be able to run passive OSINT, perform controlled active scans, enumerate web endpoints, and produce a tidy recon report with prioritized attack surface items.

---

## ⚖️ Legal & Ethical Reminder

* Only perform active recon against lab targets or systems with explicit permission.
* Passive OSINT (public data) is generally acceptable, but respect privacy and terms of service.
* Document your scope and rules of engagement before you start.

---

## 🧰 Tools & Resources

* **Nmap** — host discovery, port & service scanning. [https://nmap.org](https://nmap.org)
* **Amass** — subdomain enumeration & passive discovery. [https://github.com/OWASP/Amass](https://github.com/OWASP/Amass)
* **theHarvester** — email/subdomain harvesting from public sources. [https://github.com/laramies/theHarvester](https://github.com/laramies/theHarvester)
* **Gobuster / Dirsearch** — brute-force directories and files. [https://github.com/OJ/gobuster](https://github.com/OJ/gobuster)
* **Shodan / Censys** — internet-exposed asset search engines. [https://www.shodan.io](https://www.shodan.io) / [https://censys.io](https://censys.io)
* **Wayback Machine** — historical web snapshots. [https://web.archive.org](https://web.archive.org)
* **Chrome/Firefox devtools & Burp Suite** — inspect requests, cookies, and JavaScript. [https://portswigger.net/burp](https://portswigger.net/burp)

---

## 🧭 Recon Workflow (High-level)

1. **Define scope & rules** — domains, IPs, subnets allowed, time windows, and excluded targets.
2. **Passive OSINT** — collect public facts (WHOIS, certificates, GitHub, public leak scans).
3. **Subdomain enumeration** — passive sources first (Certificate Transparency, DNSDB), then safe active checks.
4. **Port & service discovery** — Nmap scans to find live hosts and services.
5. **Web surface mapping** — list directories, endpoints, APIs, and assets.
6. **Prioritize findings** — rank by ease of exploitation, exposure, and business impact.
7. **Produce recon report** — concise, evidence-backed, and actionable.

---

## 🔍 Passive OSINT Techniques (do first)

* WHOIS and DNS history: `whois example.com` and `dig +short NS example.com`
* Certificate transparency: search certificates for subdomains (crt.sh)
* GitHub search: find leaked API keys, config files, or public S3 buckets
* Public site archives: Wayback Machine to see old endpoints or backups
* Search engines + site: `site:example.com "admin"` — helps find admin panels

**Why passive first?** It avoids noise, reduces chance of detection, and often yields high-value data (backup URLs, config files, old endpoints).

---

## 🛠 Active Enumeration — Commands & Safe Examples (Lab Only)

### 1) Host discovery (ICMP / ARP / ping sweep)

```bash
# Quick ping sweep for live hosts (lab subnet)
nmap -sn 10.10.10.0/24 -oA nmap_ping_sweep
```

### 2) Full port & service scan (non-intrusive start)

```bash
# Service/version detection on common ports
nmap -sV -p 1-65535 --top-ports 1000 --open -oA nmap_service_version 10.10.10.5
```

### 3) Aggressive enumeration (only in lab)

```bash
# OS detection, script scanning, traceroute — more noisy
nmap -A -T4 -oA nmap_aggressive 10.10.10.5
```

### 4) Web content discovery

```bash
# Directory brute force (adjust wordlist for scope)
gobuster dir -u http://10.10.10.5 -w /usr/share/wordlists/dirb/common.txt -t 50 -o gobuster_dirs.txt
```

### 5) Subdomain enumeration (passive → active)

```bash
# Passive + active using amass
amass enum -passive -d example.com -o amass_passive.txt
amass enum -active -d example.com -o amass_active.txt
```

### 6) Banner grabbing / manual inspection

```bash
# Connect to a service and read banner (example HTTP)
nc 10.10.10.5 80
GET / HTTP/1.1
Host: 10.10.10.5
```

---

## 🧪 Web Recon Tips

* Use Burp or your browser devtools to inspect JavaScript — client-side code often hides API endpoints.
* Check `robots.txt` and sitemap files for hidden paths: `curl http://example.com/robots.txt`
* Query for common admin panels: `/admin`, `/wp-admin`, `/login`, `/manage`

---

## 📦 Deliverables — What to include in your Recon Report

Create `recon-report.md` with sections:

1. **Scope & Notes** — IPs/domains scanned, time, and tools used.
2. **Executive summary** — 3–4 lines of highest-risk findings.
3. **Assets discovered** — live hosts, open ports, services, subdomains.
4. **Interesting endpoints** — admin panels, backup files, exposed APIs.
5. **Potential attack paths** — ranked list (easy → hard) with short rationale.
6. **Evidence** — Nmap outputs, gobuster hits, certificate results (sanitized).
7. **Next recommended steps** — safe tests, permissions checks, or responsible disclosure actions.

Example priority item:

* `example.com → /backup/config.bak` — contains credentials in plain text (HIGH) — recommend rotate secrets & remove backups from web root.

---

## ✅ Prioritization Checklist (Quick)

* Is the asset internet-exposed? (yes/no)
* Does it expose admin/auth endpoints or credentials? (yes/no)
* Is there an unauthenticated endpoint that reveals sensitive data? (yes/no)
* Ease of exploit (low/medium/high) — estimate based on discovered services & versions
* Business impact (public user data, financial, internal systems)

---

## ⚙️ Automation & Scripting

* Automate repetitive recon with Python (requests + asyncio) or simple bash loops.
* Save outputs in structured formats (CSV/JSON) for easy parsing:

```bash
nmap -oX nmap_result.xml 10.10.10.5
amass enum -d example.com -oA amass_output
```

* Use `jq`/`xmlstarlet` to extract useful fields into a tabular report.

---

## 🔒 Safety & Noise Management

* Prefer `-sV --top-ports` instead of full aggressive scans on live targets.
* Wait between scans to reduce load and detection.
* Maintain a scan log with timestamps and responsible contact info (if testing third-party assets under permission).

---

## 💡 Hints & Pro Tips

* Certificate transparency sites (crt.sh) often reveal forgotten subdomains.
* GitHub searches (`token`, `aws_access_key_id`) can leak secrets — if you find them, follow responsible disclosure.
* Combine OSINT with technical scans — a GitHub repo + exposed S3 bucket is a goldmine for defenders and attackers; report it, don’t abuse it.
* When in doubt, ask a mentor or team lead — recon is powerful and can cause real disruption.

---

## 🧠 Next Steps (Practice Plan)

* Run a passive OSINT sweep for a test domain (crt.sh, GitHub search, Wayback).
* Enumerate subdomains with Amass passive and compare results to active enumeration.
* Run Nmap on a lab host, capture results, and build a one-page recon summary.
* Use Gobuster on a discovered domain and note any hidden admin panels or upload points.

---

## 📚 Further Reading & Labs

* TryHackMe: Recon & OSINT rooms — [https://tryhackme.com](https://tryhackme.com)
* HackTheBox: Starting Point — [https://www.hackthebox.com](https://www.hackthebox.com)
* OWASP Amass project — [https://github.com/OWASP/Amass](https://github.com/OWASP/Amass)
* Nmap book (official) — [https://nmap.org/book/](https://nmap.org/book/)

---

> Recon is an art: combine curiosity, discipline, and ethics. Your job is to map reality — clearly, quickly, and responsibly.

---

**Maintained by Vishant Chaudhary — [GitHub: im-vishu](https://github.com/im-vishu) • [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)**
