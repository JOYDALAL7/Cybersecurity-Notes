# Operating System — Hacker Perspective

> Goal: Understand how the OS controls power, permissions, and isolation — and where attacks begin.

---

## 1. What an Operating System Really Is

An Operating System (OS) is the **master controller** of a computer.
It sits between:

- Hardware
- Applications
- Users

The OS decides:

- Who can run what
- Who can access which files
- Which process gets CPU time
- Which memory belongs to whom

**Hacker mindset:**
If the OS enforces rules, hacking is about bypassing those rules.

---

## 2. Kernel vs User Space (MOST IMPORTANT CONCEPT)

Modern operating systems are split into two worlds.

---

### 2.1 Kernel Space

Kernel space is the **most powerful zone** of the system.

The kernel:

- Controls CPU
- Manages memory
- Talks directly to hardware
- Enforces permissions

Anything running in kernel space has **total control**.

**Security truth:**
If an attacker controls the kernel → the system is fully owned.

Examples:

- Kernel exploits
- Rootkits
- Low-level malware

---

### 2.2 User Space

User space is where:

- Applications run
- Users interact
- Most programs live

Programs in user space:

- Cannot access hardware directly
- Must request services from the kernel

**Security truth:**
Most attacks start in user space and try to reach kernel space.

---

## 3. Users and Privileges

The OS separates users to prevent total system compromise.

---

### 3.1 Normal User

A normal user:

- Has limited permissions
- Cannot modify system-critical files
- Cannot control other users

This is where attackers usually land first.

---

### 3.2 Root / Administrator

Root (Linux/macOS) or Administrator (Windows):

- Has unrestricted access
- Can read, write, execute anything
- Can change system behavior

**Core hacking goal:**
Privilege escalation — moving from normal user to root/admin.

---

## 4. Files, Ownership, and Permissions

Every file has:

- An owner
- A group
- Permissions

Permissions control:

- Read (r)
- Write (w)
- Execute (x)

Applied to:

- Owner
- Group
- Others

**Security reality:**
One wrong permission can break system security.

Examples:

- World-readable config files
- Executable files writable by users
- Sensitive scripts with weak permissions

---

## 5. Processes

A process is a **running program**.

Each process has:

- A Process ID (PID)
- A user identity
- Its own memory space

**Why attackers care:**

- Stealing secrets from process memory
- Injecting malicious code
- Escalating privileges via vulnerable services

---

## 6. How the OS Enforces Security

The OS enforces security using:

- User separation
- File permissions
- Process isolation
- System calls

Applications must ask the kernel before:

- Reading files
- Writing data
- Accessing network
- Performing privileged actions

**Hacker mindset:**
Find ways to abuse or bypass these checks.

---

## 7. macOS vs Linux vs Windows (Attacker View)

### macOS

- UNIX-based
- Strong default protections
- Harder to exploit casually
- Mostly targeted via user-space bugs

### Linux

- Open-source
- Very common on servers
- Frequent misconfigurations
- Primary target in real-world attacks

### Windows

- Complex permission model
- Heavy enterprise usage
- Active Directory increases attack surface

**Reality:**
Most real-world hacks involve Linux servers or Windows domains.

---

## 8. Common Misconceptions

- “The OS will protect me automatically”
- “Antivirus equals security”
- “If I’m not root, I’m safe”

All false.

---

## 9. Attacker Mindset (Core)

The OS is a set of rules.
Security exists because of these rules.

Hacking means:

- Breaking assumptions
- Abusing trust
- Escalating privileges
- Gaining control over execution

---

### My Understanding (Personal Notes)

**What is kernel vs user space?**
Kernel space is the most powerful part of the operating system where the kernel runs and has full control over hardware, memory, and system resources.
User space is where applications and users operate with limited permissions and must request access from the kernel.
Most attacks start in user space and try to reach kernel space.

**Why privilege escalation matters**
Privilege escalation matters because having access as a normal user is limited and not enough to fully control a system.
If an attacker escalates privileges to root or administrator, they can read any file, modify the system, install malware, and maintain persistence.
Without privilege escalation, most attacks remain incomplete.

**Which OS seems most interesting to attack and why?**
Linux seems the most interesting to attack because it is widely used on servers and often misconfigured.
Many real-world systems run Linux, and small permission or configuration mistakes can lead to full system compromise.
