# Linux Part 1 — Introduction & File System

> Goal: Master Linux fundamentals from a hacker's perspective.

---

## 1. Why Linux Matters for Cybersecurity

Linux is:

- The dominant server OS
- Open-source and customizable
- The foundation of most hacking tools
- Used in most cybersecurity certifications

**Reality:**
You cannot be a serious hacker without Linux mastery.

---

## 2. Linux Philosophy

Key principles:

- Everything is a file
- Small, focused tools
- Chain tools together
- Text-based configuration
- You have full control

**Hacker advantage:**
Complete transparency and control over the system.

---

## 3. Linux Distributions

Common distributions:

### Kali Linux

- Pre-loaded with hacking tools
- Based on Debian
- Industry standard for penetration testing

### Ubuntu

- User-friendly
- Large community
- Good for learning

### Parrot OS

- Security-focused
- Lightweight
- Privacy-oriented

**My choice for learning:**
Start with Kali Linux or Ubuntu.

---

## 4. The Linux File System Structure

Unlike Windows (C:, D:), Linux has a single tree structure starting at `/` (root).

### Key Directories:

```
/
├── bin/     # Essential user binaries
├── etc/     # Configuration files
├── home/    # User home directories
├── root/    # Root user's home
├── var/     # Variable data (logs)
├── tmp/     # Temporary files
├── usr/     # User programs
└── opt/     # Optional software
```

---

### 4.1 /bin and /usr/bin

Contains executable programs:

- `/bin` - Essential system binaries
- `/usr/bin` - User-installed programs

**Security relevance:**
Where legitimate and malicious executables live.

---

### 4.2 /etc

Configuration files for the entire system:

- Password files
- Network settings
- Service configurations

**Hacker interest:**
Misconfigurations often lead to vulnerabilities.

---

### 4.3 /home

User directories:

- `/home/username/` for each user
- Personal files and settings

**Attack target:**
User data, SSH keys, browser credentials.

---

### 4.4 /var

Variable data:

- `/var/log/` - System logs
- `/var/www/` - Web server files
- `/var/mail/` - Email storage

**Security use:**
Logs reveal attack patterns and system activity.

---

### 4.5 /tmp

Temporary files:

- World-writable
- Often cleared on reboot

**Security risk:**
Common place for malware and exploits to write files.

---

## 5. Absolute vs Relative Paths

### Absolute Path

Starts from root `/`

Example: `/home/user/Documents/file.txt`

### Relative Path

Starts from current directory

Example: `Documents/file.txt`

**Special symbols:**

- `.` = current directory
- `..` = parent directory
- `~` = home directory

---

## 6. Hidden Files

Files starting with `.` are hidden.

Examples:

- `.bashrc` - Bash configuration
- `.ssh/` - SSH keys
- `.bash_history` - Command history

**Hacker interest:**
Hidden files often contain sensitive data or attacker persistence mechanisms.

---

## 7. File Types in Linux

Everything is a file, but there are types:

- `-` Regular file
- `d` Directory
- `l` Symbolic link
- `c` Character device
- `b` Block device
- `s` Socket
- `p` Named pipe

**Why this matters:**
Understanding file types helps identify system components and attack surfaces.

---

## 8. The Root User

`root` is the superuser with unlimited privileges.

Root can:

- Access any file
- Kill any process
- Modify system settings
- Break the system

**Security truth:**
Gaining root access = game over for the defender.

---

## 9. Case Sensitivity

Linux is case-sensitive:

- `File.txt` ≠ `file.txt`
- `Documents` ≠ `documents`

**Why this matters:**
Precision is critical in commands and exploitation.

---

## 10. Getting Started with Terminal

The terminal is your primary interface.

Basic navigation (covered in Part 2):

- `pwd` - Print working directory
- `ls` - List files
- `cd` - Change directory

**Mindset shift:**
GUI is convenient. Terminal is powerful.

---

## 11. My Understanding (Personal Notes)

_Write this in your own words:_

- Why is Linux important for hacking?
- What is the `/etc` directory used for?
- What does it mean that "everything is a file"?
