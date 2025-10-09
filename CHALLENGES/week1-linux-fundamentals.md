# 🧩 Week 1 — Linux Fundamentals for Cybersecurity

## 🎯 Goal

Learn essential Linux operations used daily in cybersecurity: navigation, file handling, permissions, log analysis, and basic scripting.

**Outcome:** You’ll gain confidence in the terminal, understand how to investigate system activity, and prepare for real-world security labs.

---

## ⏱ Duration

3–5 hours (split over 2 sessions)

---

## 🧰 Tools & Setup

| Tool                | Purpose             | Link                                                                      |
| ------------------- | ------------------- | ------------------------------------------------------------------------- |
| Ubuntu / Kali Linux | Primary OS          | [kali.org](https://www.kali.org)                                          |
| VS Code or nano     | Text editing        | [code.visualstudio.com](https://code.visualstudio.com)                    |
| TryHackMe Room      | Guided practice     | [Linux Fundamentals 1–3](https://tryhackme.com/module/linux-fundamentals) |
| ExplainShell        | Command syntax help | [explainshell.com](https://explainshell.com)                              |

---

## 🧪 Tasks

1. **Navigation basics:** Use `pwd`, `cd`, `ls -la`, `find`, and `grep` to explore directories.
2. **Permissions lab:** Create files and change their permissions using `chmod`, `chown`, and `sudo`.
3. **System investigation:** View running processes (`ps aux`, `top`), logged-in users (`who`, `w`), and network connections (`netstat -tulnp`).
4. **Log analysis:** Inspect `/var/log/auth.log` and `/var/log/syslog` to identify login attempts.
5. **Scripting exercise:** Write a small bash script to list all SUID files and log the output.
6. **Bonus:** Identify a failed SSH login pattern and summarize how you’d alert on it.

---

## 💡 Hints

* Use `grep -i failed /var/log/auth.log` to find failed logins.
* Use `find / -perm -4000 2>/dev/null` to locate SUID binaries.
* Create your own `/home/student/lab-notes.md` — note every new command.

---

## 📦 Deliverables

* A short report (`findings.md`) with:

  * Commands used & purpose
  * Interesting findings from logs
  * Output of your script (sanitized)
* Optional: Screenshot of your terminal and bash script.

---

## 📚 Recommended Resources

* [TryHackMe — Linux Fundamentals 1–3](https://tryhackme.com/module/linux-fundamentals)
* [OverTheWire: Bandit Game](https://overthewire.org/wargames/bandit/)
* [Linux Command Library](https://linuxcommandlibrary.com/)
* [The Art of Command Line (GitHub)](https://github.com/jlevy/the-art-of-command-line)

---

## 🧠 Reflection

At the end of this week, you should be able to:

* Move comfortably through a Linux file system.
* Analyze authentication logs.
* Use shell scripting to automate small security tasks.

> Great security analysts are built on strong Linux fundamentals — this week builds your foundation.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)


