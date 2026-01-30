# 🧠 Operators in Python for Cybersecurity (Lesson 02)

> This lesson explains **operators from absolute scratch** , with **security‑focused logic** . Save as `02-operators-in-python.md`.

---

## 📌 What are Operators?

Operators are **symbols that perform actions** on data.

In security scripts, operators are used to:

- Compare passwords
- Validate inputs
- Apply logic (allow / deny)
- Control flow of execution

---

## 1️⃣ Arithmetic Operators

Used for **mathematical operations** .

| Operator | Meaning             | Example  |
| -------- | ------------------- | -------- |
| +        | Addition            | 5 + 3    |
| -        | Subtraction         | 5 - 3    |
| \*       | Multiplication      | 5 \* 3   |
| /        | Division            | 10 / 2   |
| %        | Modulus (remainder) | 10 % 3   |
| \*\*     | Power               | 2 \*\* 3 |

### Example

```python
attempts = 5
remaining = 10 - attempts
print(remaining)
```

🔐 Used in:

- retry counters
- rate limiting
- timing calculations

---

## 2️⃣ Assignment Operators

Used to **update variables** .

| Operator | Meaning             |
| -------- | ------------------- |
| =        | Assign              |
| +=       | Add and assign      |
| -=       | Subtract and assign |
| \*=      | Multiply and assign |
| /=       | Divide and assign   |

### Example

```python
attempts = 0
attempts += 1
print(attempts)
```

---

## 3️⃣ Comparison Operators (VERY IMPORTANT)

Used to **compare values** and return `True` or `False`.

| Operator | Meaning          |
| -------- | ---------------- |
| ==       | Equal            |
| !=       | Not equal        |
| >        | Greater than     |
| <        | Less than        |
| >=       | Greater or equal |
| <=       | Less or equal    |

### Example

```python
password = "admin123"

password == "admin123"   # True
password != "root"       # True
```

🔐 Used in:

- authentication
- access checks
- filtering results

---

## 4️⃣ Logical Operators (THINK LIKE A HACKER)

Used to combine conditions.

| Operator | Meaning                     |
| -------- | --------------------------- |
| and      | All conditions must be True |
| or       | Any condition True          |
| not      | Reverse condition           |

### Example

```python
is_admin = True
has_token = False

is_admin and has_token   # False
is_admin or has_token    # True
not is_admin             # False
```

🔐 Used in:

- permission systems
- multi‑factor logic
- firewall rules

---

## 5️⃣ Membership Operators

Used to check **presence inside data** .

| Operator | Meaning        |
| -------- | -------------- |
| in       | Exists inside  |
| not in   | Does not exist |

### Example

```python
payload = "root@localhost"

"root" in payload
"admin" not in payload
```

🔐 Used in:

- payload detection
- keyword filtering
- log scanning

---

## 6️⃣ Identity Operators (Advanced)

Used to compare **memory location** , not value.

| Operator | Meaning          |
| -------- | ---------------- |
| is       | Same object      |
| is not   | Different object |

Example:

```python
x = None

x is None
```

🔐 Used in:

- checking empty values
- error handling

---

## 🧪 Mini Security Script Example

```python
password = input("Enter password: ")

if password == "admin123":
    print("Access granted")
else:
    print("Access denied")
```

---

## 🧠 Common Mistakes (IMPORTANT)

❌ Wrong:

```python
if password = "admin":
```

✅ Correct:

```python
if password == "admin":
```

---

## ✅ Practice Tasks

1️⃣ What is output?

```python
print(10 % 4)
```

2️⃣ Is this True or False?

```python
"root" in "root@127.0.0.1"
```

3️⃣ Write a condition to check:

- user is admin AND password is correct

---

📌 **Next Lesson:**

### `03-Conditional-Statements-if-else.md`

(Real decision‑making logic for automation & security tools)

Say **"next"** when ready.
