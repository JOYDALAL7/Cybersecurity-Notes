# 📂 File Handling in Python for Security (Lesson 07)

> File handling lets your scripts **read and write data** — wordlists, logs, configs, reports. Save as `07-file-handling.md`.

---

## 📌 Why File Handling Matters in Security

Security scripts often need to:

- Read password/username wordlists
- Parse log files
- Save scan results
- Generate reports

---

## 1️⃣ Opening a File

### Syntax

```python
file = open("filename.txt", "mode")
```

### Common Modes

| Mode | Meaning           |
| ---- | ----------------- |
| r    | Read              |
| w    | Write (overwrite) |
| a    | Append            |
| rb   | Read binary       |
| wb   | Write binary      |

---

## 2️⃣ Reading a File

### Read Entire File

```python
file = open("wordlist.txt", "r")
content = file.read()
print(content)
file.close()
```

### Read Line by Line (BEST PRACTICE)

```python
file = open("wordlist.txt", "r")

for line in file:
    print(line.strip())

file.close()
```

🔐 Used in:

- iterating password lists
- processing logs

---

## 3️⃣ Writing to a File

```python
file = open("results.txt", "w")
file.write("Scan started\n")
file.write("Port 22 open\n")
file.close()
```

⚠️ `w` mode **overwrites** existing content.

---

## 4️⃣ Appending to a File

```python
file = open("results.txt", "a")
file.write("Port 80 open\n")
file.close()
```

---

## 5️⃣ Using `with` (RECOMMENDED)

Automatically closes the file.

```python
with open("wordlist.txt", "r") as file:
    for line in file:
        print(line.strip())
```

This is **professional style** .

---

## 6️⃣ Reading Files into Data Structures

```python
ports = []

with open("ports.txt", "r") as file:
    for line in file:
        ports.append(int(line.strip()))

print(ports)
```

🔐 Used in:

- loading configs
- dynamic scanning

---

## 7️⃣ Writing Structured Results

```python
results = {22: "open", 80: "open"}

with open("scan_report.txt", "w") as file:
    for port, status in results.items():
        file.write(f"Port {port}: {status}\n")
```

---

## 🧪 Mini Security Script

```python
with open("passwords.txt", "r") as file:
    for pwd in file:
        pwd = pwd.strip()
        if pwd == "admin123":
            print("Password found!")
            break
```

---

## 🧠 Common Mistakes

❌ Forgetting to close files
❌ Overwriting important files
❌ Not stripping `\n`

---

## ✅ Practice Tasks

1️⃣ Read a file line by line

2️⃣ Write scan results to a file

3️⃣ Append new findings safely
