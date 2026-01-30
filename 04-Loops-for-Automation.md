# 🔁 Loops in Python for Automation (Lesson 04)

> Loops allow you to **repeat actions automatically** . This is where Python becomes powerful for cybersecurity. Save as `04-loops-for-automation.md`.

---

## 📌 What are Loops?

Loops execute a block of code **multiple times** .

In cybersecurity, loops are used to:

- Scan multiple ports
- Try multiple inputs
- Process large log files
- Automate repetitive tasks

---

## 1️⃣ `for` Loop

Used when you know **how many times** to repeat.

### Syntax

```python
for variable in sequence:
    code
```

### Example

```python
for i in range(5):
    print(i)
```

Output:

```
0
1
2
3
4
```

🔐 Security use:

- port scanning ranges
- iterating IPs

---

## 2️⃣ `range()` Function

Used to generate numbers.

```python
range(start, stop, step)
```

Examples:

```python
range(5)          # 0 to 4
range(1, 6)       # 1 to 5
range(1, 10, 2)   # 1,3,5,7,9
```

---

## 3️⃣ Looping Through Data

```python
users = ["admin", "root", "guest"]

for user in users:
    print(user)
```

🔐 Used in:

- username lists
- payload lists

---

## 4️⃣ `while` Loop

Used when you **don’t know how many times** to repeat.

### Syntax

```python
while condition:
    code
```

### Example

```python
attempts = 0

while attempts < 3:
    print("Trying password")
    attempts += 1
```

🔐 Used in:

- retry logic
- brute‑force simulations (labs only)

---

## 5️⃣ `break` Statement

Stops the loop completely.

```python
for port in range(1, 100):
    if port == 22:
        print("SSH found")
        break
```

---

## 6️⃣ `continue` Statement

Skips current iteration and moves on.

```python
for port in range(20, 26):
    if port == 23:
        continue
    print(port)
```

---

## 7️⃣ Nested Loops

Loop inside another loop.

```python
for ip in range(1, 3):
    for port in range(80, 83):
        print(ip, port)
```

🔐 Used in:

- IP + port combinations

---

## 🧪 Mini Security Script

```python
ports = [21, 22, 80, 443]

for port in ports:
    if port == 22:
        print("SSH detected")
    else:
        print("Port", port)
```

---

## 🧠 Common Mistakes

❌ Infinite loop:

```python
while True:
    print("Running")
```

⚠️ Always control your loop exit.

---

## ✅ Practice Tasks

1️⃣ Print numbers from 1 to 10

2️⃣ Loop through ports 20–25

3️⃣ Stop loop when port is 22
