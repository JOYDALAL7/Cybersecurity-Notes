# 🐍 Python Basics for Cybersecurity (Lesson 01)

> These notes are **beginner‑level** , **security‑oriented** , and **GitHub‑ready** . You can directly commit this file as `01-python-basics.md`.

---

## 📌 What is Python?

Python is a **high‑level, interpreted programming language** widely used in cybersecurity for:

- Automation
- Writing security tools
- Log analysis
- Scripting scans and checks

### Why Python is used in security

- Easy to read and write
- Massive security libraries
- Works on Linux, macOS, Windows

---

## 📌 How Python Runs (Important Concept)

Python is **interpreted** , meaning:

- Code runs line‑by‑line
- No compilation step like C/C++

Example:

```python
print("Python is running")
```

---

## 📌 Comments (Very Important for GitHub)

Comments are ignored by Python but help humans understand code.

```python
# This is a single‑line comment

"""
This is a
multi‑line comment
"""
```

Use comments to explain **what your security script is doing** .

---

## 📌 Variables

Variables store data in memory.

Syntax:

```python
variable_name = value
```

Examples:

```python
username = "admin"
port = 22
is_secure = True
```

Rules:

- No need to define data type
- Python auto‑detects type

---

## 📌 Data Types

### Common Data Types

| Type  | Example | Used For            |
| ----- | ------- | ------------------- |
| int   | 80      | ports, counts       |
| float | 0.25    | delays              |
| str   | "root"  | usernames, payloads |
| bool  | True    | checks              |

Check data type:

```python
type(username)
```

---

## 📌 Print Statement (Output)

Used to display output.

```python
print("Scan started")
print(port)
```

Used in:

- Status messages
- Debugging
- Results display

---

## 📌 Input Statement (User Interaction)

Used to take input from user.

```python
target = input("Enter target IP: ")
print(target)
```

⚠️ Input is always **string type** by default.

---

## 📌 Type Conversion

Convert data types manually when needed.

```python
port = int(input("Enter port: "))
```

Common conversions:

```python
int()
float()
str()
bool()
```

---

## 📌 Simple Security‑Style Script

```python
username = input("Enter username: ")

if username == "admin":
    print("Admin user detected")
else:
    print("Normal user")
```

This logic is the **base of authentication systems** .

## 🧠 Key Takeaways

- Python is interpreter‑based
- Variables hold data
- Data types matter in security scripts
- Input/output is the foundation of automation

---

## ✅ Practice (Do This)

1️⃣ What is the type of input()?

2️⃣ Convert user input to integer

3️⃣ Print a message saying:
`Target acquired`
