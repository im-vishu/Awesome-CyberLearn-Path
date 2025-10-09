# 🧮 Linux Commands Cheatsheet for Cybersecurity Learners

This is your quick reference for the most-used Linux commands in cybersecurity. Whether you’re working in a SOC lab, pentesting a target, or investigating logs — these will save you time and help you move confidently in the terminal.

---

## 🧭 Navigation & File Management

| Task                   | Command                             |
| ---------------------- | ----------------------------------- |
| Show current directory | `pwd`                               |
| List files (detailed)  | `ls -la`                            |
| Change directory       | `cd /path/to/dir`                   |
| Create directory       | `mkdir logs`                        |
| Remove file/folder     | `rm file.txt` / `rm -r folder`      |
| Copy/Move file         | `cp file /dest` / `mv file /dest`   |
| Search file content    | `grep 'keyword' filename`           |
| Count lines/words      | `wc -l file.txt` / `wc -w file.txt` |

---

## ⚙️ System Information & Monitoring

| Task                          | Command                        |
| ----------------------------- | ------------------------------ |
| Show system info              | `uname -a`                     |
| Display hostname              | `hostname`                     |
| Show active processes         | `ps aux`                       |
| Monitor processes (real-time) | `top` / `htop`                 |
| Check disk usage              | `df -h`                        |
| Check memory usage            | `free -m`                      |
| Network connections           | `netstat -tulnp` / `ss -tulnp` |
| Logged-in users               | `who` / `w`                    |

---

## 🧰 Permissions & Ownership

| Task               | Command                     |
| ------------------ | --------------------------- |
| View permissions   | `ls -l`                     |
| Change permissions | `chmod 755 file.sh`         |
| Change file owner  | `chown user:group file.txt` |
| Switch user        | `su - username`             |
| Execute as root    | `sudo command`              |

**Pro tip:** Permissions in numbers — `4=read`, `2=write`, `1=execute`.

---

## 🌐 Networking Commands

| Task             | Command                                    |
| ---------------- | ------------------------------------------ |
| Check IP address | `ip addr show` / `ifconfig`                |
| Ping a host      | `ping -c 4 example.com`                    |
| Trace route      | `traceroute example.com`                   |
| DNS lookup       | `dig example.com` / `nslookup example.com` |
| Check open ports | `netstat -tuln`                            |
| Capture packets  | `tcpdump -i eth0`                          |
| Download file    | `wget URL` / `curl -O URL`                 |

---

## 🔍 File & Log Analysis

| Task                    | Command                           |      |         |           |
| ----------------------- | --------------------------------- | ---- | ------- | --------- |
| View file               | `cat file.log`                    |      |         |           |
| Paginate output         | `less file.log`                   |      |         |           |
| Tail (follow logs)      | `tail -f /var/log/syslog`         |      |         |           |
| Search logs for keyword | `grep 'error' /var/log/syslog`    |      |         |           |
| Count specific entries  | `grep -c 'error' /var/log/syslog` |      |         |           |
| Filter unique IPs       | `awk '{print $1}' access.log      | sort | uniq -c | sort -nr` |

---

## 🔒 Security & Forensics Basics

| Task                   | Command                               |                |
| ---------------------- | ------------------------------------- | -------------- |
| Check open connections | `lsof -i`                             |                |
| Monitor failed logins  | `cat /var/log/auth.log                | grep 'Failed'` |
| Check running services | `systemctl list-units --type=service` |                |
| Find suspicious files  | `find / -perm -4000 2>/dev/null`      |                |
| Hash a file            | `sha256sum file.txt`                  |                |

---

## 💡 Tips for Security Learners

* Always run commands with **`--help`** to understand options.
* Keep a `notes.md` in your lab folder — document everything you learn.
* Use [ExplainShell](https://explainshell.com/) to decode command syntax.

> Practice daily — Linux isn’t something you memorize; it’s something you internalize.

---

**Maintained by [Vishant Chaudhary](https://github.com/im-vishu)**
💼 [LinkedIn](https://www.linkedin.com/in/vishant--chaudhary)
