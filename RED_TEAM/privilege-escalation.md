# 🔓 Privilege Escalation — Post-Exploitation Techniques (Lab-Only)

> Mentor-style guide. Practice **only** in authorized lab environments (TryHackMe, HackTheBox, VulnHub) or on systems you own and have explicit written permission to test. Never run these techniques against production or third-party systems.

---

## 🎯 Purpose

Privilege escalation is the step after initial access where you attempt to gain higher privileges (local admin or SYSTEM on Windows, root on Linux). This guide teaches safe enumeration, common escalation vectors, and how to document findings responsibly.

**Outcome:** You’ll be able to: enumerate a compromised host, identify likely privilege escalation paths, validate a lab-safe escalation technique, and provide clear remediation guidance.

---

## ⚖️ Legal & Safety Reminder

* Use isolated VMs and snapshots; revert to clean snapshots after tests.
* Do not exfiltrate any sensitive data from lab machines.
* Record all commands, timestamps, and authorization details for your reports.

---

## 🧰 Tools & Resources

* **LinPEAS / WinPEAS** — Linux/Windows privilege escalation enumeration. [https://github.com/carlospolop/PEASS-ng](https://github.com/carlospolop/PEASS-ng)
* **GTFOBins** — living repo of Unix binaries for privilege escalation. [https://gtfobins.github.io](https://gtfobins.github.io)
* **Linux Exploit Suggester** — kernel exploit detection. [https://github.com/mzet-/linux-exploit-suggester](https://github.com/mzet-/linux-exploit-suggester)
* **BloodHound** — Active Directory attack path discovery. [https://github.com/BloodHoundAD/BloodHound](https://github.com/BloodHoundAD/BloodHound)
* **Mimikatz** — credential extraction (lab-only; Windows). [https://github.com/gentilkiwi/mimikatz](https://github.com/gentilkiwi/mimikatz)
* **PowerUp / PowerSploit** — PowerShell post-exploitation toolset (lab-only). [https://github.com/PowerShellMafia/PowerSploit](https://github.com/PowerShellMafia/PowerSploit)

---

## 🧭 General PrivEsc Workflow

1. **Stabilize your shell** — upgrade to an interactive TTY where needed (`python -c 'import pty; pty.spawn("/bin/bash")'`).
2. **Enumerate thoroughly** — run automated enumeration (LinPEAS/WinPEAS) then manual follow-ups.
3. **Identify misconfigurations & SUIDs** — look for writable files, credentials in scripts, scheduled tasks, and misconfigured services.
4. **Validate in lab** — use non-destructive proofs where possible.
5. **Document & remediate** — produce a report that includes the root cause and exact remediation steps.

---

## 🐧 Linux Privilege Escalation (Common Vectors)

### Enumeration checks (manual)

* Kernel & distro info: `uname -a; cat /etc/os-release`
* SUID/SGID binaries: `find / -perm -4000 -type f 2>/dev/null`
* World-writable files and folders: `find / -writable -type d 2>/dev/null`
* Services and listening ports: `ss -tulpn` or `netstat -tulpn`
* Scheduled cron jobs & scripts: `crontab -l`, check `/etc/cron.*`
* Config files with credentials: search `grep -R "password\|passwd\|secret" / 2>/dev/null`

### Typical Escalation Paths

* **SUID binaries** abused to spawn shells or escalate.
* **Writable scripts in cron** that run as root — modify to execute your payload.
* **Exposed credentials** in config files — use them to switch user via `su` or `ssh`.
* **Kernel exploits** — only on outdated kernels and in controlled lab environments.

### Lab-safe validation examples

* Show a writable cron script and explain how it could be abused; do not deploy a real root shell on shared infra.
* Use `ls -la` and `file` to show the SUID binary details and reference GTFOBins for potential abuse methods.

---

## 🪟 Windows Privilege Escalation (Common Vectors)

### Enumeration checks (manual)

* System details: `systeminfo`
* Local users & groups: `net user` / `net localgroup administrators`
* Services & binary paths: `sc query` and check for unquoted service paths
* Scheduled tasks: `schtasks /query /fo LIST /v`
* Registry autoruns: check `HKLM\Software\Microsoft\Windows\CurrentVersion\Run`
* Installed patches & vulnerable software versions

### Typical Escalation Paths

* **Unquoted service paths** allowing DLL hijacking.
* **Weak service permissions** allowing replacement of executable.
* **Credential exposure** via config files or plaintext scripts.
* **Token impersonation / abuse** after extracting credentials with Mimikatz (lab-only).

### Lab-safe validation examples

* Demonstrate discovery of an unquoted service path and propose exact remediation (quote the path).
* Use BloodHound to map attack paths in a test Active Directory deployment and show potential privilege chains (do not run Mimikatz on shared environments unless isolated).

---

## 🧪 Hands-on Lab Tasks (Lab-Only)

1. **Stabilize shell & environment** — spawn a proper TTY, gather baseline system info.
2. **Run LinPEAS/WinPEAS** — collect enumeration output and parse results.
3. **Identify at least two potential privilege escalation vectors** (SUID, writable cron, unquoted service, stored credentials).
4. **Validate one vector safely** — e.g., modify a writable script to echo a string (not to spawn a root shell) or create a harmless file via cron to demonstrate control.
5. **Produce a `privesc-report.md`** describing findings, evidence, and remediation steps.

---

## 📦 Deliverables

* `privesc-report.md` including:

  * Host info and snapshot timestamp
  * Enumeration outputs (sanitized)
  * Identified vectors with risk rating
  * Safe validation steps and remediation
* Optional: short demo GIF showing a non-destructive validation (e.g., cron-created file)

---

## 🔐 Remediation Best Practices

* Remove SUID bit from binaries that don’t require it: `chmod u-s /path/to/binary`
* Fix file and directory permissions — adhere to least privilege.
* Harden cron jobs and ensure scripts are owned by root and not world-writable.
* Quote service paths on Windows and apply least privilege to service accounts.
* Rotate credentials and enforce MFA where possible.

---

## 📚 Further Reading & Labs

* LinPEAS & WinPEAS — [https://github.com/carlospolop/PEASS-ng](https://github.com/carlospolop/PEASS-ng)
* GTFOBins — [https://gtfobins.github.io](https://gtfobins.github.io)
* BloodHound AD edition — [https://github.com/BloodHoundAD/BloodHound](https://github.com/BloodHoundAD/BloodHound)
* TryHackMe Privilege Escalation rooms — [https://tryhackme.com](https://tryhackme.com)
* Kali Privilege Escalation resources — [https://www.kali.org/tools/](https://www.kali.org/tools/)

---

> Privilege escalation is about careful observation. If you can’t explain the path clearly, document it — the story is as valuable as the exploit.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
