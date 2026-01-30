# Linux Part 3 — File Permissions & Ownership

> Goal: Master Linux permissions for security and exploitation.

---

## 1. Why Permissions Matter

File permissions control:

- Who can read files
- Who can modify files
- Who can execute programs

**Security reality:**
One wrong permission = complete system compromise.

---

## 2. The Permission Model

Every file has three levels of access:

1. **Owner** (user who created it)
2. **Group** (users in the same group)
3. **Others** (everyone else)

Each level has three permissions:

- **Read (r)** - View file contents
- **Write (w)** - Modify file
- **Execute (x)** - Run as program

---

## 3. Reading Permissions

When you run `ls -l`, you see:

```
-rwxr-xr--  1 user group 4096 Jan 27 script.sh
```

Breaking it down:

```
-rwxr-xr--
│││││││││
││││││││└─ Others: read
│││││││└── Others: write (-)
││││││└─── Others: execute (-)
│││││└──── Group: read
││││└───── Group: write (-)
│││└────── Group: execute
││└─────── Owner: read
│└──────── Owner: write
└───────── Owner: execute
```

First character:

- `-` = Regular file
- `d` = Directory
- `l` = Link

---

## 4. Numeric (Octal) Permissions

Permissions can be represented as numbers:

- Read (r) = 4
- Write (w) = 2
- Execute (x) = 1

Add them up for each level:

| Permission | Calculation | Number |
| ---------- | ----------- | ------ |
| ---        | 0+0+0       | 0      |
| r--        | 4+0+0       | 4      |
| rw-        | 4+2+0       | 6      |
| rwx        | 4+2+1       | 7      |
| r-x        | 4+0+1       | 5      |

**Example:**
`chmod 755 file.sh`

- Owner: 7 (rwx)
- Group: 5 (r-x)
- Others: 5 (r-x)

---

## 5. Common Permission Patterns

### 644 (rw-r--r--)

Standard file permissions:

- Owner can read and write
- Others can only read

### 755 (rwxr-xr-x)

Standard executable/directory:

- Owner can do everything
- Others can read and execute

### 600 (rw-------)

Private file:

- Only owner can read and write
- No one else has access

### 777 (rwxrwxrwx)

**DANGEROUS:**

- Everyone can do everything
- Common misconfiguration

---

## 6. The chmod Command

Change file permissions:

### Symbolic method:

```bash
chmod u+x file.sh      # Add execute for owner
chmod g-w file.txt     # Remove write for group
chmod o+r file.log     # Add read for others
chmod a+x script.sh    # Add execute for all
```

### Numeric method:

```bash
chmod 644 file.txt
chmod 755 script.sh
chmod 600 private.key
```

**Hacker note:**
Finding world-writable files (`chmod 777`) is a common attack vector.

---

## 7. The chown Command

Change file ownership:

```bash
chown user file.txt           # Change owner
chown user:group file.txt     # Change owner and group
chown :group file.txt         # Change group only
```

**Security relevance:**
Only root can change ownership of files.

---

## 8. The chgrp Command

Change group ownership:

```bash
chgrp developers project.txt
```

---

## 9. Special Permissions

### 9.1 SUID (Set User ID)

Number: 4000

When set on an executable:

- Program runs with owner's privileges
- Not the user who executed it

**Visualization:**

```bash
-rwsr-xr-x  # Notice the 's' instead of 'x'
```

**Example:**

```bash
chmod 4755 program
# or
chmod u+s program
```

**Hacker goldmine:**
SUID root programs are prime targets for privilege escalation.

**Real example:**
`/usr/bin/passwd` has SUID so users can change their password (stored in root-only files).

---

### 9.2 SGID (Set Group ID)

Number: 2000

On files:

- Program runs with group's privileges

On directories:

- New files inherit directory's group

**Example:**

```bash
chmod 2755 directory
# or
chmod g+s directory
```

---

### 9.3 Sticky Bit

Number: 1000

On directories:

- Only owner can delete their files
- Even if directory is world-writable

**Visualization:**

```bash
drwxrwxrwt  # Notice the 't' at the end
```

**Example:**

```bash
chmod 1777 /tmp
# or
chmod +t /tmp
```

**Real-world use:**
`/tmp` directory has sticky bit so users can't delete each other's files.

---

## 10. Finding Dangerous Permissions

### Find world-writable files:

```bash
find / -type f -perm -002 2>/dev/null
```

### Find SUID files:

```bash
find / -perm -4000 2>/dev/null
```

### Find SGID files:

```bash
find / -perm -2000 2>/dev/null
```

**Hacker workflow:**
These commands are essential in privilege escalation.

---

## 11. Directory Permissions

Directories work differently:

- **Read (r)** - List files in directory
- **Write (w)** - Create/delete files
- **Execute (x)** - Enter directory

**Important:**
You need execute (x) to access a directory, even if you have read permission.

---

## 12. Default Permissions (umask)

`umask` controls default permissions for new files.

Common umask values:

- `022` = Files: 644, Directories: 755
- `027` = Files: 640, Directories: 750
- `077` = Files: 600, Directories: 700

**Security best practice:**
Restrictive umask prevents accidental exposure.

---

## 13. Real-World Security Scenarios

### Scenario 1: Exposed SSH Keys

```bash
-rw-r--r-- ~/.ssh/id_rsa
```

**Problem:** Private key readable by everyone  
**Fix:** `chmod 600 ~/.ssh/id_rsa`

---

### Scenario 2: Writable Config Files

```bash
-rw-rw-rw- /etc/passwd
```

**Problem:** Anyone can modify system passwords  
**Impact:** Complete system compromise

---

### Scenario 3: SUID Shell

```bash
-rwsr-xr-x /bin/bash
```

**Impact:** Instant root access for any user  
**Exploit:** Run `/bin/bash -p`

---

## 14. Permission Exploitation Strategy

As an attacker, look for:

1. World-writable files in sensitive locations
2. SUID/SGID binaries you can exploit
3. Writable scripts executed by cron/root
4. Misconfigured config files
5. Backup files with weak permissions

---

## 15. Common Mistakes

### Mistake 1: chmod 777

**Never do this.** It gives everyone full access.

### Mistake 2: Running everything as root

Defeats the entire security model.

### Mistake 3: Weak SSH key permissions

SSH will refuse to use keys with wrong permissions.

### Mistake 4: Not checking inherited permissions

Copying files may preserve dangerous permissions.

---

## 16. Best Practices

1. Use least privilege principle
2. Regularly audit SUID/SGID files
3. Never chmod 777 unless you understand the risk
4. Protect SSH keys with 600
5. Use umask for secure defaults

---

## 17. Quick Reference

| Task                | Command              |
| ------------------- | -------------------- |
| View permissions    | `ls -l file`         |
| Change permissions  | `chmod 644 file`     |
| Change owner        | `chown user file`    |
| Change group        | `chgrp group file`   |
| Find SUID files     | `find / -perm -4000` |
| Find writable files | `find / -perm -002`  |

---

## 18. My Understanding (Personal Notes)

_Write this in your own words:_

- What does the permission `755` mean?
- Why are SUID files dangerous?
- How would you secure a private SSH key?
- What command finds all world-writable files?
