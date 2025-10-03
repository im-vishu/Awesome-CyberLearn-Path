# Awesome CyberLearn-Path
Practical, curated cybersecurity learning resources — beginner → hireable.

> Here’s the thing: learning security is messy. This repo makes the path clear — roadmaps, curated courses, labs, projects, datasets, and a practice plan so you build a portfolio that gets you interviews.

---

## Who this repo is for
- Students and early-career engineers who want a structured, practical path into cybersecurity.
- Career-switchers with basic IT/dev skills who need a hands-on roadmap and cert guidance.
- Intermediate learners looking to deepen skills (cloud security, red teaming, DFIR) and build portfolio projects.

---

## Quick start — how to use this repo
- `README.md` — Project overview, career roadmap highlights, and quick links.
- `ROADMAP.md` — Expanded career roadmaps and timelines per role.
- `RESOURCES/` — Curated lists: courses, books, tools, labs, datasets.
- `PROJECTS/` — Step-by-step project ideas (deliverables you can show).
- `CERTIFICATIONS/` — Certification timetable and notes.
- `CTF_PLAN.md` — 3-month CTF/practice plan.
- `CONTRIBUTING.md` & `CODE_OF_CONDUCT.md` — How to contribute and community rules.
- `DARK_WEB.md` — Safety-first, high-level notes for researchers.

---

## Table of contents
- [Purpose & audience](#who-this-repo-is-for)  
- [Career roadmap (roles & paths)](#cybersecurity-career-roadmap)  
- [Learning path & resources (by level)](#learning-path-and-resources)  
- [Tooling & datasets](#tooling-and-datasets)  
- [Projects & portfolio ideas](#hands-on-projects--portfolio)  
- [CTF / practice plan (3 months)](#ctf--practice-plan)  
- [Study-plan template](#study-plan-template)  
- [Contributing & growth](#contributing--growth)  
- [Citations & sources](#citations--sources)

---

## Cybersecurity career roadmap
Below are common role paths. For each role: milestones, suggested timeline (months), and sample portfolio projects.

> **How to read this:** milestones show the practical skills you should own. Timelines are realistic estimates assuming 10–15 hours/week.

### SOC Analyst / SOC L1
- Milestones:
  1. Fundamentals: TCP/IP, basic Linux, log formats (syslog, Windows Event), SIEM basics.  
  2. Detection basics: yara rules, basic signature hunting, alerts triage.  
  3. Incident triage: containment/escalation playbooks, case management.  
  4. Automation: scripting detection workflows (Python).  
  5. Become L2-ready: host/network forensics basics and threat intel correlation.  
- Timeline: 2–4 months to be hireable for L1 (with labs + projects).
- Portfolio projects:
  - Build a mini SIEM dashboard (ELK/Elastic + sample logs).  
  - Create playbooks for common alerts and a GitHub-runbook.  

### Incident Responder / Digital Forensics
- Milestones:
  1. Disk & memory basics, acquisition tools (FTK, Autopsy, Volatility).  
  2. Memory forensics and timeline analysis.  
  3. Malware triage & static/dynamic basics.  
  4. Reporting & legal/chain-of-custody best practices.  
- Timeline: 6–12 months (after L1 / with focused practice).
- Portfolio:
  - DFIR case report: include evidence, timelines, artifacts, mitigations.
  - Memory analysis lab writeup (Volatility).

### Penetration Tester / Red Team
- Milestones:
  1. Recon + OSINT, basic pentest methodology.  
  2. Web app exploitation (OWASP Top 10), network exploitation basics.  
  3. Privilege escalation, pivoting, persistence techniques.  
  4. Report writing and remediation guidance.  
- Timeline: 6–12 months to be hireable for a junior / internship role (intensive labs/OSCP-style training recommended).  
- Portfolio:
  - Public HTB/THM machine writeups (sanitized).  
  - Small internal pentest engagement report (vuln findings + fixes).

### Vulnerability Assessor / Appsec (SAST/DAST)
- Milestones:
  1. Static analysis tools and SAST pipelines.  
  2. DAST tooling and Burp Suite workflows.  
  3. CI/CD security integration (pre-commit, scanning).  
  4. Remediation guidance & secure coding fundamentals.  
- Timeline: 4–8 months with focused projects.
- Portfolio:
  - Create a GitHub Action that runs SAST on a sample repo and reports issues.  
  - DAST report for an intentionally vulnerable app (PortSwigger labs).

### Security Engineer / DevSecOps
- Milestones:
  1. Cloud basics (AWS/Azure/GCP), IAM, networking.  
  2. Infrastructure as Code security (Terraform scanning), secrets management.  
  3. CI/CD security, container hardening, runtime security.  
  4. Observability and incident response integration.  
- Timeline: 6–12 months depending on cloud experience.
- Portfolio:
  - Hardened terraform infra + automated policy checks (OPA / Conftest).  
  - Demo showing secrets scanning and runtime EDR integration.

### Cloud Security Engineer
- Milestones:
  1. Cloud provider security docs & controls (IAM, VPCs, logging).  
  2. Cloud audit logging and detection (CloudTrail/Azure Monitor).  
  3. Container security and serverless security.  
  4. Cloud-native incident response and threat modelling.  
- Timeline: 6–12 months (strong DevOps background helps).
- Portfolio:
  - Cloud security posture report + IaC remediation PRs.

### Threat Intelligence Analyst
- Milestones:
  1. TTP mapping (MITRE ATT&CK), indicator collection.  
  2. Open-source intel (OSINT) pipelines and enrichment.  
  3. Threat modeling & reporting to stakeholders.  
  4. Automation: enrichment via APIs (VirusTotal, abuse.ch).  
- Timeline: 6–12 months to junior role.
- Portfolio:
  - TI report on a known campaign using ATT&CK mapping.

### Application Security Engineer (SAST/DAST)
- (See Vulnerability Assessor) plus:
  - Secure design reviews, threat modeling, SCA (software composition analysis).  
- Portfolio:
  - Threat model + remediation plan for a real app.

### Security Architect / CISO track
- Milestones:
  1. Broad technical competency (networks, cloud, appsec, infra).  
  2. Risk management frameworks (NIST CSF) and governance.  
  3. Program building: policies, vendor assessments, budgets.  
  4. Leadership and communication skills.  
- Timeline: multi-year (3–7 years) with cross-team experience and leadership roles.
- Portfolio:
  - Security program blueprint, risk register sample, security policy set.

---

## Learning path and resources (Beginner / Intermediate / Advanced)

### Beginner (0 → 3 months)
- Courses (free + paid):
  - TryHackMe: Intro to Cyber and free learning paths. :contentReference[oaicite:0]{index=0}  
  - PortSwigger Web Security Academy (free web-app labs). :contentReference[oaicite:1]{index=1}  
  - Coursera / IBM Cybersecurity Analyst (for structured foundations).  
- Books:
  - “The Web Application Hacker’s Handbook” — classic for websec.  
  - “Practical Malware Analysis” (intro chapters).
- Labs & practice:
  - TryHackMe beginner rooms and Bootcamps. :contentReference[oaicite:2]{index=2}
  - PortSwigger labs for XSS/SQLi basics. :contentReference[oaicite:3]{index=3}
- Certifications:
  - CompTIA Security+ (entry-level, vendor-neutral). :contentReference[oaicite:4]{index=4}
- Why these: they teach practical, safe labs and fundamentals.

### Intermediate (3 → 12 months)
- Courses:
  - OffSec PEN-200 (OSCP) prep (when ready for hands-on pentest). :contentReference[oaicite:5]{index=5}  
  - eLearnSecurity / INE eJPT (entry-level pentest cert). :contentReference[oaicite:6]{index=6}  
  - SANS short courses (targeted, expensive — employer-subsidized). :contentReference[oaicite:7]{index=7}
- Books:
  - “The Hacker Playbook” series  
  - “Practical Unix & Internet Security” (selected chapters)
- Labs:
  - Hack The Box labs (increasingly difficult). :contentReference[oaicite:8]{index=8}
  - HTB Academy / Pro labs for real-case simulations.
- Certifications:
  - eJPT, then move toward OSCP or equivalent hands-on cert.

### Advanced (12+ months)
- Courses & certs:
  - OSCP (OffSec PEN-200), CREST/OSCE for advanced pentesting. :contentReference[oaicite:9]{index=9}  
  - Specialized cloud certs: AWS Certified Security Specialty / Microsoft SC-100/SC-200 (after cloud experience).
- Books:
  - In-depth reverse-engineering and malware analysis texts.
- Advanced labs:
  - Red Team exercises, Purple Team engagements, capture-the-flag hard boxes.

---

## Tooling list (top categories + 1–2 docs)
> Use tools responsibly and in authorized environments only.

- **Network analysis / packet capture**
  - Wireshark — sample captures & docs. :contentReference[oaicite:10]{index=10}
- **Web app testing**
  - Burp Suite (PortSwigger) — Web Security Academy & Burp docs. :contentReference[oaicite:11]{index=11}
- **Vulnerability scanning**
  - OpenVAS / Nessus (vendor docs).
- **Malware & Threat Intel**
  - MalwareBazaar (abuse.ch) — sample exchange & API. :contentReference[oaicite:12]{index=12}
- **SIEM / logging**
  - Elastic Stack (ELK), Splunk (official docs).
- **Forensics**
  - Volatility framework (memory forensics docs).
- **Cloud security**
  - AWS Security docs, Azure Security docs.
- **Reverse engineering**
  - Ghidra, IDA Pro docs.

(Full tool links and doc pointers live in `RESOURCES/tools.md`.)

---

## Datasets & public collections
- CSE-CIC-IDS2018 network captures (UNB/CIC dataset) — good for detection model training. :contentReference[oaicite:13]{index=13}  
- MalwareBazaar (abuse.ch) — sample metadata for TI research. :contentReference[oaicite:14]{index=14}  
- Wireshark sample captures — packet examples for analysis. :contentReference[oaicite:15]{index=15}

---

## Hands-on projects & portfolio (8–12 ideas)
Short notes on deliverables and recruiter-facing outputs.

1. **Mini pentest report (micro-pentest)** — target: intentionally vulnerable VM. Deliverable: executive summary, technical findings, PoC screenshots, remediation list.  
2. **SIEM demo (ELK)** — ingest sample logs, create dashboards, produce detection rules and one runbook. Deliverable: GitHub repo + screenshots + sample dashboards.  
3. **Web-app secure pipeline** — GitHub Action runs SAST + DAST against a demo app and creates a PR with fixes. Deliverable: demo repo, CI logs.  
4. **Threat intel brief** — map a recent campaign to MITRE ATT&CK with indicators-of-compromise. Deliverable: PDF + timeline + scripts for enrichment.  
5. **Cloud posture scan** — IaC scanning (Terraform), produce remediation PRs. Deliverable: repo + scanned results and fix patches.  
6. **DFIR case study** — simulated incident, evidence handling, timeline, artifacts. Deliverable: full report, Jupyter timelines.  
7. **CTF writeups collection** — clean, teachable writeups for 6–10 boxes. Deliverable: markdown writeups with learning points.  
8. **Secure architecture blueprint** — threat model, risk register, policy templates. Deliverable: diagrams (draw.io) + policy md.  
9. **Malware analysis sandbox** — safe, documented static analysis of a sample (high-level, non-actionable). Deliverable: writeup and YARA rules.  
10. **Automation toolkit** — small Python tool to fetch and enrich indicators from public TI APIs. Deliverable: pip-installable script + README.  
11. **SCA dashboard** — scan open-source dependencies for vulnerabilities and produce PR remediation. Deliverable: demo repo and screenshots.  
12. **Red/Blue lab** — design a small lab with simulated attack path and detection playbook.

---

## CTF / practice plan — 3 months to intermediate (weekly schedule)
Goal: build core skills and complete 12–20 beginner/intermediate rooms.

- **Week 1–2:** Linux + networking basics; TryHackMe "Complete Beginner" path. Goals: basic shell, SSH, file permissions. :contentReference[oaicite:16]{index=16}  
- **Week 3–4:** Web fundamentals & OWASP Top 10 labs (PortSwigger). Goals: find and exploit XSS/SQLi. :contentReference[oaicite:17]{index=17}  
- **Week 5–6:** Basic pentest workflow; HTB easy boxes; write 3 sanitized writeups. :contentReference[oaicite:18]{index=18}  
- **Week 7–8:** Intro to forensics & memory (Volatility), packet capture practice (Wireshark sample captures). :contentReference[oaicite:19]{index=19}  
- **Week 9–10:** Cloud basics (AWS free tier labs), IAM misconfigurations.  
- **Week 11–12:** Red-team chaining and report. Final: complete 2 medium CTF boxes and produce 2 portfolio writeups.

Rooms and labs referenced above are free or freemium; use authorized labs only.

---

## Study-plan template (copyable)
- **Daily (1–2 hours)**: theory + one hands-on exercise. E.g., read 1 chapter/article + complete 1 TryHackMe room.  
- **Weekly (6–12 hours)**: 1 focused topic (web, cloud, DFIR), one project task (add to GitHub), one writeup.  
- **Checkpoints (every 4 weeks)**: demo a deliverable on GitHub, update resume/LinkedIn with new project.  
- **Portfolio tasks**: aim for 3 polished projects in first 6 months (one SIEM, one pentest writeup, one cloud/infrastructure project).

---

## How to contribute
See `CONTRIBUTING.md` for contribution steps. Short version:
- Fork, add a resource or update, open PR with source links.
- Keep items high-quality (official docs, university pages, reputable training platforms).
- Use issue templates to request new content.

---

## Quick links (official pages)
- TryHackMe — hands-on beginner→intermediate labs. :contentReference[oaicite:20]{index=20}  
- Hack The Box — advanced labs & certs. :contentReference[oaicite:21]{index=21}  
- PortSwigger Web Security Academy — free web-app labs. :contentReference[oaicite:22]{index=22}  
- MITRE ATT&CK — adversary TTP knowledge base. :contentReference[oaicite:23]{index=23}  
- NIST Cybersecurity Framework — risk & governance. :contentReference[oaicite:24]{index=24}

---

## License
Pick an OSI-approved license (MIT recommended). Add `LICENSE.md`.

---

## Want this in your inbox or as a starter repo?
If you found this helpful, star the repo, open issues for missing resources, and send PRs with vetted links and small summaries.

