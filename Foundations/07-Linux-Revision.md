# 🔐 Linux Fundamentals – Part 7

## Linux Complete Revision (Security-Focused)

---

## 1. Linux & UNIX Overview

- UNIX is the parent operating system concept.
- Linux is an open-source, UNIX-like operating system.
- Linux is widely used in:
  - Servers
  - Cloud infrastructure
  - Cybersecurity tools
  - Networking devices

Why Linux matters in cybersecurity:

- Most servers run Linux
- Most security tools are Linux-native
- Fine-grained control over system resources

---

## 2. Linux Architecture

Linux follows a layered architecture:

User → Shell → Kernel → Hardware

### Components

- Kernel: core, manages CPU, memory, hardware
- Shell: interface between user and kernel
- File System: everything treated as a file
- Applications: user-level programs

Security relevance:

- Kernel vulnerabilities = full system compromise
- Shell access = command execution

---

## 3. Linux File System Hierarchy

Linux uses a single root directory `/`.

Important directories:

| Directory | Purpose             |
| --------- | ------------------- |
| /         | Root                |
| /home     | User data           |
| /root     | Root user home      |
| /etc      | Configuration files |
| /bin      | Essential commands  |
| /sbin     | System binaries     |
| /var      | Logs, variable data |
| /tmp      | Temporary files     |
| /usr      | User programs       |

Security-critical paths:

- `/etc/passwd` → user list
- `/etc/shadow` → password hashes
- `/var/log` → authentication & system logs

---

## 4. Users, Root & Privileges

- Root user:
  - UID = 0
  - Full system control
- Normal users:
  - Limited permissions

Privilege escalation:

- Process of gaining higher privileges than assigned
- Common attack objective

---

## 5. Linux Commands (Core)

### Navigation

- `pwd` → current directory
- `ls` → list files
- `cd` → change directory

### File & Directory Management

- `touch` → create file
- `mkdir` → create directory
- `cp` → copy
- `mv` → move/rename
- `rm` → delete (permanent)

### Viewing & Searching

- `cat`, `less` → read files
- `head`, `tail` → partial view
- `grep` → search text
- `|` → combine commands

Security relevance:

- Used for enumeration
- Used for log analysis
- Used for credential discovery

---

## 6. Linux Permissions

Permission types:

- r (read)
- w (write)
- x (execute)

User categories:

- User (u)
- Group (g)
- Others (o)

Permission example:

-rwxr-xr--

Numeric permissions:

- r = 4
- w = 2
- x = 1

Examples:

- 755 → rwx r-x r-x
- 644 → rw- r-- r--

---

## 7. Permission Management

### chmod

Change permissions:

chmod 755 file.sh

chmod u+x file.sh

### chown / chgrp

Change ownership:

chown user file.txt

chgrp admin file.txt

Security risk:

- World-writable files (777)
- Misconfigured ownership

---

## 8. sudo & Root Access

- `sudo` allows temporary root execution
- Controlled via:

/etc/sudoers

Security relevance:

- Misconfigured sudo rules can give full root access
- One of the most common privilege escalation vectors

---

## 9. Processes

- Process = running instance of a program
- Identified by PID

Process lifecycle:
Created → Running → Waiting → Terminated

### Process Commands

- `ps`, `ps aux` → list processes
- `top` → real-time monitoring
- `kill`, `kill -9` → terminate process

Security relevance:

- Malware runs as a process
- Abnormal CPU/memory usage indicates compromise

---

## 10. Services & Daemons

- Services are long-running background processes
- Often end with `d` (daemon)

Examples:

- sshd
- httpd
- cron

### systemctl

Manage services:

systemctl start service

systemctl stop service

systemctl enable service

systemctl status service

Security relevance:

- Attackers create malicious services for persistence

---

## 11. Persistence Mechanisms

Common persistence methods:

- systemd services
- cron jobs
- startup scripts

Example cron job:

/malware.sh

Purpose:

- Maintain access after reboot

---

## 12. Key Security Takeaways

- Linux security depends heavily on correct permissions
- Misconfigurations are more dangerous than vulnerabilities
- Visibility (processes, logs, services) is critical
- Privilege escalation is the attacker’s main goal

---

## FINAL SUMMARY (ONE-GLANCE)

- Linux = core OS for cybersecurity
- Everything is a file
- Permissions control access
- Processes show what is running
- Services provide persistence
- Misconfigurations create security holes
