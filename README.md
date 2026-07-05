<div align="center">

# 🐧 Linux 101 — A Practitioner's Field Guide

### From "what even is Linux" to writing your first automation script

*A hands-on, terminal-first Linux series for aspiring Cybersecurity, Cloud, DevOps, and SysAdmin professionals.*

## 📖 About This Series

Most Linux tutorials either drown you in theory or throw 200 commands at you with no context. This series does neither.

**Linux 101** is built the way you actually learn a system: sitting at a terminal, running real commands, and understanding *why* each one matters in a production, cloud, or security context. Every lesson uses live terminal output, real-world scenarios (checking Apache logs because your SOC manager asked, backing up `/var/log/auth.log`, hunting failed SSH logins), and a memory trick so the concept sticks.

> **The philosophy:** Linux isn't about memorizing commands. It's about understanding concepts. Once the mental model clicks, the commands follow.

By the end, you'll have a genuine working foundation for **cybersecurity, cloud, networking, and DevOps** — not a certificate of completion, but skills you can use on a real box on day one.

---

## 🎯 Who This Is For

| If you're aiming for... | This series gives you... |
|---|---|
| 🔐 **Cybersecurity Analyst / SOC** | Log analysis, auth investigation, permissions, process hunting |
| ☁️ **Cloud Engineer** | The Linux fluency every AWS/Azure/GCP instance demands |
| 🔧 **DevOps / SRE** | Services, package management, and Bash automation |
| 🖥️ **System / Network Administrator** | File systems, users, networking, and daily troubleshooting |
| 🎓 **Students & career switchers** | A structured, no-fluff path from zero to competent |

No prior Linux experience required. If you can open a terminal, you can follow along.

---

## 🗺️ Curriculum

The series is designed to be read in order — each lesson builds on the last.

| # | Topic | What You'll Master |
|:---:|---|---|
| **01** | [What Is Linux & Why Learn It](#01--what-is-linux) | Operating system fundamentals, distros, where Linux runs the world |
| **02** | [The Linux File System](#02--the-linux-file-system) | The root tree — `/home`, `/etc`, `/usr`, `/var`, `/tmp`, `/root` |
| **03** | [Navigating Like a Pro](#03--navigating-like-a-pro) | `pwd`, `ls`, `cd`, hidden files, `tree` |
| **04** | [Files & Directories](#04--files--directories) | `mkdir`, `touch`, `cp`, `mv`, `rm` — create, copy, move, delete |
| **05** | [Users & Groups](#05--users--groups) | Identity, `/etc/passwd`, `useradd`, `usermod`, the root account |
| **06** | [Permissions & Ownership](#06--permissions--ownership) | `rwx`, numeric modes (755/644/600), `chmod`, `chown`, least privilege |
| **07** | [Processes & Services](#07--processes--services) | `ps`, `top`, `kill`, `systemctl`, managing background services |
| **08** | [Package Management](#08--package-management) | `apt` update/upgrade/install/search/remove, repositories |
| **09** | [Networking Commands](#09--networking-commands) | 20 essential tools — `ip`, `ping`, `dig`, `ss`, `tcpdump`, `nmap`, `nc` |
| **10** | [Log Analysis](#10--log-analysis) | `/var/log`, `tail -f`, `grep`, `journalctl`, security investigations |
| **11** | [Bash Scripting](#11--bash-scripting) | Variables, conditionals, loops, functions — your first automation |

---

## 📚 What's Inside Each Part

### 01 · What Is Linux
The big picture: what an operating system actually does, why Linux powers the majority of web servers, cloud platforms, supercomputers, and Android devices — and why "hackers staring at green text" is a myth. Covers the major distributions (Ubuntu, Debian, RHEL, Rocky, Kali) and why Linux fluency is non-negotiable for modern IT careers.

### 02 · The Linux File System
Everything in Linux branches from a single root: `/`. This lesson walks the tree directory by directory, explaining the six folders that account for ~80% of your daily interaction:

```
/home → Users        /var  → Logs & changing data
/etc  → Configuration /tmp  → Temporary files
/usr  → Programs      /root → Administrator
```

### 03 · Navigating Like a Pro
Movement fundamentals. If Linux were a city: `pwd` is your GPS, `ls` looks around, `cd` walks somewhere, `cd ..` goes back, and `tree` shows the map. Ends with a real SOC scenario — navigating straight to `/var/log/apache2` when asked to check the logs.

### 04 · Files & Directories
The file lifecycle: create (`mkdir`, `touch`), read (`cat`), copy (`cp`, `cp -r`), move/rename (`mv`), and delete (`rm`, `rm -r`). Includes the crucial warning every beginner needs — **Linux has no Recycle Bin**, and `rm -r` means it.

### 05 · Users & Groups
The foundation of Linux access control. Every action belongs to a user and a group. Covers UID/GID, `/etc/passwd` and `/etc/group`, creating and managing accounts (`useradd`, `passwd`, `usermod -aG`), why groups make permissions *scale*, and the power of the root account.

### 06 · Permissions & Ownership
Why Linux is secure by design. Read the cryptic `-rwxr-xr--` string fluently, understand numeric modes (`755`, `644`, `600`), and use `chmod` / `chown` / `chgrp` with intent. Reinforces the **principle of least privilege** and why `chmod 777` is a production red flag.

### 07 · Processes & Services
What Linux is doing behind the scenes. Inspect live activity with `ps aux` and `top`, find and terminate processes (`pgrep`, `kill`, `kill -9`), and manage long-running services with `systemd` (`systemctl start/stop/restart/enable`). Framed around the question every incident starts with: *"Is the process running?"*

### 08 · Package Management
Linux's "app store." Master `apt` on Debian/Ubuntu — update the index, upgrade packages, install and remove software, search repositories, and understand dependency management. The skill behind installing every tool you'll ever use: Nmap, Wireshark, Docker, Nginx, and more.

### 09 · Networking Commands
**The Top 20 networking commands every IT professional should know.** Organized by troubleshooting workflow — check the interface → verify IP → confirm gateway → test connectivity → verify DNS → check ports:

`ip addr` · `ip link` · `ip route` · `ping` · `traceroute` · `mtr` · `nslookup` · `dig` · `ss` · `netstat` · `curl` · `wget` · `tcpdump` · `nmap` · `ip neigh` · `ethtool` · `nc` — and more.

### 10 · Log Analysis
*"If you're not checking the logs, you're troubleshooting blind."* Where logs live (`/var/log`), how to read them (`tail`, `less`, `tail -f`), how to search them (`grep`, `wc -l`), and modern `journalctl` usage. Includes security use cases: detecting failed logins, tracking sudo activity, and root-causing service failures.

### 11 · Bash Scripting
Stop typing the same commands over and over. From the shebang line to a real, working backup script that combines variables, conditionals, loops, and functions. Learn to make the shell do the work — then schedule it with `cron` and never think about it again.

---

## ⚡ Quick Command Reference

<details>
<summary><b>Click to expand the full cheat sheet</b></summary>

### Navigation
```bash
pwd                 # Where am I?
ls                  # List files
ls -l               # Long format (permissions, owner, size, date)
ls -a               # Include hidden files
cd <dir>            # Change directory
cd ..               # Up one level
cd                  # Return home
tree -L 2           # Visual directory tree
```

### Files & Directories
```bash
mkdir <dir>         # Create directory
touch <file>        # Create empty file
echo "text" > file  # Write to file
cat <file>          # View contents
cp src dst          # Copy file
cp -r src dst       # Copy directory
mv old new          # Move or rename
rm <file>           # Delete file (no undo!)
rm -r <dir>         # Delete directory (careful!)
```

### Users & Groups
```bash
whoami              # Current user
id                  # UID, GID, groups
groups              # Group memberships
sudo useradd -m x   # Create user with home dir
sudo passwd x       # Set password
sudo usermod -aG g x# Add user x to group g
cat /etc/passwd     # User accounts
```

### Permissions
```bash
chmod 755 file      # rwxr-xr-x
chmod 644 file      # rw-r--r--
chmod 600 file      # rw------- (SSH keys)
chmod +x script.sh  # Make executable
chown user:grp file # Change ownership
# 4=read  2=write  1=execute
```

### Processes & Services
```bash
ps aux              # All processes
top                 # Live monitor
pgrep <name>        # Find PID by name
kill <pid>          # Terminate
kill -9 <pid>       # Force kill
sudo systemctl status|start|stop|restart|enable <svc>
```

### Package Management (APT)
```bash
sudo apt update           # Refresh package index
sudo apt upgrade -y       # Upgrade installed packages
sudo apt install <pkg> -y # Install
apt search <term>         # Search
apt show <pkg>            # Package details
sudo apt remove <pkg>     # Remove
sudo apt purge <pkg>      # Remove + config files
```

### Networking
```bash
ip addr             # Interfaces & IPs
ip route            # Routing table
ping <host>         # Test reachability
dig <host>          # DNS lookup (detailed)
ss -tulnp           # Listening ports
tcpdump -i eth0     # Capture packets
nmap 192.168.1.0/24 # Scan network
nc -zv host 443     # Test a specific port
```

### Log Analysis
```bash
tail -f /var/log/syslog              # Follow live
grep "Failed password" /var/log/auth.log
grep -i error /var/log/syslog
journalctl -u nginx                  # Service logs
journalctl -f                        # Follow journal
journalctl -p err                    # Errors only
```

</details>

---

## 🧠 Skills Demonstrated

This series maps directly to competencies hiring managers screen for:

- **Blue-team fundamentals** — log analysis, authentication investigation, process inspection
- **System administration** — user/permission management, service control, package management
- **Network troubleshooting** — the full interface-to-DNS diagnostic workflow
- **Automation** — Bash scripting for repeatable, scheduled operations
- **Security mindset** — least privilege, secure file modes, and OPSEC-aware thinking throughout

---

## 🚀 How to Use This Repo

1. **Read in order** — each part assumes the previous one.
2. **Type every command yourself** — don't copy-paste. Muscle memory matters.
3. **Break things in a lab** — spin up a free Ubuntu VM (VirtualBox, WSL, or a cloud instance) and experiment. A home lab is the fastest way to learn.
4. **Reference the [cheat sheet](#-quick-command-reference)** whenever you're stuck.

> 💡 **Tip:** The best way to learn Linux is to *use* Linux. Make it your daily driver for a week and you'll learn more than any tutorial can teach.

---

## 👤 About the Author

**Ace (Ashish Ghimire)** — Senior Network & Security Engineer

Cybersecurity practitioner focused on network security, cloud, and offensive/defensive operations, on a path toward Cloud Security Architecture and DevSecOps.

**Certifications:** OSCP · CCNP · RHCSA · AWS SAA · AZ-500 · CISSP *(in progress)*
**Education:** M.S. Cybersecurity
**Writes about:** Cybersecurity, Linux, Cloud, and DevOps — the learn-build-blog way.

📬 *Connect:* `[LinkedIn]` · `[Hashnode]` · `[GitHub]`
> *Replace the placeholders above with your actual profile links before publishing.*

---

<div align="center">

### ⭐ If this series helped you, drop a star and share it.

`#Linux` `#CyberSecurity` `#CloudComputing` `#DevOps` `#SysAdmin` `#LearnLinux` `#Homelab`

</div>
