# 🧩 Challenges — Learn by Doing

Welcome to the **CHALLENGES** folder — a collection of short, focused, mentor-style exercises that force you to use tools and think like a security practitioner.

Each challenge is designed to be completed in 2–6 hours. Do them in order (Week 1 → Week 4) or pick a theme that matches what you want to learn. The goal is depth over breadth: complete a challenge, write a short deliverable, and push it to your GitHub portfolio.

---

## How to use these challenges

1. **Read the challenge goal** and make sure you understand the expected deliverable.
2. **Set up a safe lab**: use an isolated VM, offline VulnHub box, or TryHackMe/HTB environment. Never run attacks on systems you don't own or have permission to test.
3. **Follow the hints** when you’re stuck but try to solve problems before peeking.
4. **Document your work**: notes, commands, screenshots, and a short conclusion (`findings.md`).
5. **Publish a sanitized writeup** to your GitHub portfolio under `CTF-WRITEUPS/` (remove sensitive info).

---

## Challenge structure (what each file contains)

Each weekly challenge file follows a template:

```
# Week X — <Title>

## Goal
One line description of what you will learn and build.

## Duration
Estimated hours (2–6h)

## Tools
List of suggested tools and links.

## Tasks
1. Step-by-step tasks (high-level; no exploitation commands for live systems)
2. Hints

## Deliverables
- Short writeup (README or Markdown)
- Screenshots or exported files (sanitized)
- Optional: script or config files

## Resources
Curated links to labs, docs, and reference material.
```

---

## Progress template (copy into your own repo)

Use this to track and show progress in your GitHub profile (add to each challenge folder or your personal notes):

```md
# 4-Week Challenge Progress — @your-github
- [x] Week 1 — Linux Fundamentals (notes/links)
- [ ] Week 2 — Networking & Recon
- [ ] Week 3 — Web Exploitation
- [ ] Week 4 — Incident Response

Notes:
- Lab used: TryHackMe - Room X
- Time spent: 3 hours
- Key learning: How to triage suspicious auth logs
```

---

## Safety & Ethics (short)

* Use isolated environments only.
* Never target public IPs or services you don’t own.
* If you document a vulnerability from a public program, redact sensitive details and follow responsible disclosure.

---

## Included challenges

* `week1-linux-fundamentals.md` — terminal fluency, file forensics, permissions
* `week2-networking-and-recon.md` — nmap, netcat, basic packet capture
* `week3-web-exploitation.md` — OWASP Top 10 micro-labs (use PortSwigger/juice-shop)
* `week4-incident-response.md` — triage logs, timeline, and containment

Want more challenges? Open an issue or submit a PR with your idea — we’ll add it and credit you.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
