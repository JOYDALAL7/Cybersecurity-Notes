# 🔀 Conditional Statements in Python (Lesson 03)

> This lesson teaches **decision‑making logic** — the backbone of all security scripts. Save as `03-conditional-statements.md`.

---

## 📌 What are Conditional Statements?

Conditional statements allow a program to **make decisions** based on conditions.

In cybersecurity, they are used to:

- Allow or deny access
- Validate input
- Detect suspicious activity
- Control script flow

---

## 1️⃣ The `if` Statement

Syntax:

```python
if condition:
    code
```

Example:

```python
user = "admin"

if user == "admin":
    print("Admin access")
```

🔐 Used in:

- authentication checks
- privilege validation

---

## 2️⃣ The `else` Statement

Used when the `if` condition is False.

Syntax:

```python
if condition:
    code
else:
    code
```

Example:

```python
password = "1234"

if password == "admin123":
    print("Access granted")
else:
    print("Access denied")
```

---

## 3️⃣ The `elif` Statement

Used to check **multiple conditions** .

Syntax:

```python
if condition1:
    code
elif condition2:
    code
else:
    code
```

Example:

```python
role = "user"

if role == "admin":
    print("Full access")
elif role == "moderator":
    print("Limited access")
else:
    print("Guest access")
```

---

## 4️⃣ Combining Conditions (Security Logic)

Using logical operators.

Example:

```python
username = "admin"
password = "admin123"

if username == "admin" and password == "admin123":
    print("Login successful")
else:
    print("Login failed")
```

---

## 5️⃣ Nested Conditions

Conditions inside conditions.

Example:

```python
user = "admin"
is_active = True

if user == "admin":
    if is_active:
        print("Admin is active")
    else:
        print("Admin is disabled")
```

🔐 Used in:

- role + status checks
- layered security logic

---

## 6️⃣ Common Mistakes (IMPORTANT)

❌ Wrong indentation:

```python
if user == "admin":
print("Admin")
```

✅ Correct:

```python
if user == "admin":
    print("Admin")
```

⚠️ Python uses **indentation** , not braces `{}`.

---

## 🧪 Mini Security Script

```python
username = input("Username: ")
password = input("Password: ")

if username == "admin" and password == "admin123":
    print("Access granted")
elif username == "admin":
    print("Wrong password")
else:
    print("Unknown user")
```

---

## 🧠 Key Takeaways

- `if` checks conditions
- `elif` checks alternatives
- `else` handles default case
- Indentation is mandatory

---

## ✅ Practice Tasks

1️⃣ Write a condition to check if port is 80 or 443

2️⃣ Detect if user is NOT admin

3️⃣ Print message based on login success or failure
