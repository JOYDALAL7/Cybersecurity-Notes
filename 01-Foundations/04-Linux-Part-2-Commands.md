# 🔐 Linux Fundamentals – Part 2

## Linux Commands (Core Concepts)

---

## 1. What is a Linux Command?

A Linux command is a small program that performs a specific task.
Commands are usually stored in `/bin` or `/usr/bin`.

When a command is executed, the flow is:

User → Shell → Kernel → Hardware

Linux commands are powerful because they are:

- Fast
- Scriptable
- Precise
- Text-based

---

## 2. Command Structure

General syntax:

command [options] [arguments]

Example:

ls -la /home

- `ls` → command
- `-la` → options
- `/home` → argument

---

## 3. Navigation Commands

pwd

---

### ls

## Lists files and directories.

### pwd

Displays the current working directory.

- `-l` → long listing
- `-a` → show hidden files

Hidden files start with a dot (`.`).

---

### cd

Changes the current directory.

cd /etc

cd ..

cd ~

- `/` → root directory
- `..` → previous directory
- `~` → home directory

---

## 4. File and Directory Management

### mkdir

Creates a new directory.

mkdir test

---

### touch

## Creates an empty file.

touch file.txt

---

### cp

## Copies files or directories.

cp a.txt b.txt

cp -r dir1 dir2

---

### mv

## Moves or renames files.

mv old.txt new.txt

---

### rm

## Deletes files or directories permanently.

rm file.txt

rm -r folder

⚠️ Deleted files cannot be recovered.

---

## 5. Viewing Files

### cat

Displays the entire content of a file.

cat file.txt

---

### less

## Views file content page by page.

less file.txt

---

### head

## Displays the first lines of a file.

head file.txt

---

### tail

## Displays the last lines of a file.

tail file.txt

tail -f log.txt

`tail -f` is used for live log monitoring.

---

## 6. Searching and Filtering

### grep

Searches for specific text patterns.

grep "root" /etc/passwd

grep -i "error" log.txt

- `-i` → ignore case
- `-r` → recursive search

---

### Pipes

Used to combine multiple commands.

cat users.txt | grep admin | sort

---

## 7. Process Monitoring

### ps

Displays running processes.

ps

ps aux

---

### top

## Shows real-time system usage.

top

Used to monitor CPU, memory, and suspicious processes.

---

## 8. Network Visibility Commands

### netstat

Displays open ports and listening services.

netstat -tuln

---

### ss

## Modern replacement for netstat.

ss -tuln

Open ports represent potential attack surfaces.

---

## 9. Key Summary

- `pwd` → current location
- `ls` → list files
- `cd` → change directory
- `touch` / `mkdir` → create
- `cp` / `mv` → copy and move
- `rm` → delete
- `cat` / `less` → read files
- `grep` → search
- `ps` / `top` → processes
- `netstat` / `ss` → ports

Linux commands provide full system visibility and control, making them essential for cybersecurity.

<pre class="overflow-visible! px-0!" data-start="2221" data-end="2295"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(--spacing(9)+var(--header-height))] @w-xl/main:top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"></div></div></pre>
