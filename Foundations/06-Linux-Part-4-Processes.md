# 🔐 Linux Fundamentals – Part 4

## Processes, Services & System Control

---

## 1. What is a Process?

A process is a running instance of a program stored in memory.
Each process has a unique Process ID (PID).

---

## 2. Process Lifecycle

A process goes through the following states:

Created → Running → Waiting → Terminated

---

## 3. Parent and Child Processes

Linux uses a hierarchical process structure.
Every process is created by a parent process.

Abnormal parent-child relationships can indicate malicious activity.

---

## 4. Viewing Processes

### ps

Displays running processes.

ps

ps aux

Important columns:

- USER
- PID
- %CPU
- %MEM
- COMMAND

---

## 5. Real-Time Monitoring

### top

Displays real-time system usage.

top

Used to detect CPU or memory abuse.

---

## 6. Killing Processes

### kill

Stops a process.

kill PID

### Force kill

kill -9 PID

---

## 7. Background and Foreground Processes

Run command in background:

command &

List background jobs:

jobs

Bring job to foreground:

fg

---

## 8. Processes vs Services

| Process            | Service           |
| ------------------ | ----------------- |
| Temporary          | Long-running      |
| User-initiated     | Starts at boot    |
| Ends automatically | Runs continuously |

Services are also called daemons.

---

## 9. Managing Services

### systemctl

systemctl start service

systemctl stop service

systemctl enable service

systemctl status service

## 10. Persistence Mechanisms

Attackers use:

- Malicious services
- Cron jobs
- Startup scripts

Example cron job:

/script.sh

---

## Key Takeaway

Monitoring processes and services is critical for detecting and preventing malicious activity on Linux systems.

<pre class="overflow-visible! px-0!" data-start="4608" data-end="4631"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(--spacing(9)+var(--header-height))] @w-xl/main:top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"></div></div></pre>
