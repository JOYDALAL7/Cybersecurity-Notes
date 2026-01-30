# 🧩 Functions in Python for Security (Lesson 05)

> Functions let you write **clean, reusable, professional code** . Every real security tool uses functions. Save as `05-functions.md`.

---

## 📌 What is a Function?

A function is a **block of reusable code** that performs a specific task.

Why functions matter in security:

- Avoid repeating code
- Organize large scripts
- Make tools readable & maintainable

---

## 1️⃣ Defining a Function

### Syntax

```python
def function_name():
    code
```

### Example

```python
def banner():
    print("Security Script Started")

banner()
```

---

## 2️⃣ Functions with Parameters

Parameters allow you to **pass data** into a function.

```python
def scan_port(port):
    print("Scanning port", port)

scan_port(22)
scan_port(80)
```

🔐 Used in:

- scanning different ports
- processing different targets

---

## 3️⃣ Functions with Return Values

`return` sends data back from a function.

```python
def is_admin(user):
    if user == "admin":
        return True
    else:
        return False
```

Usage:

```python
if is_admin("admin"):
    print("Admin detected")
```

---

## 4️⃣ Multiple Parameters

```python
def login(user, password):
    if user == "admin" and password == "admin123":
        return "Access granted"
    else:
        return "Access denied"

print(login("admin", "admin123"))
```

---

## 5️⃣ Default Parameters

```python
def connect(port=80):
    print("Connecting to port", port)

connect()
connect(443)
```

---

## 6️⃣ Local vs Global Variables

```python
x = 10  # global

def test():
    x = 5   # local
    print(x)

test()
print(x)
```

⚠️ Local variables exist **only inside functions** .

---

## 7️⃣ Why Functions are Critical in Security Tools

Without functions ❌:

```python
print("Scanning 22")
print("Scanning 80")
```

With functions ✅:

```python
def scan(port):
    print("Scanning", port)

scan(22)
scan(80)
```

---

## 🧪 Mini Security Tool Example

```python
def check_password(password):
    if password == "admin123":
        return True
    return False

user_input = input("Enter password: ")

if check_password(user_input):
    print("Access granted")
else:
    print("Access denied")
```

---

## 🧠 Key Takeaways

- Functions make code reusable
- Parameters make them flexible
- `return` gives results
- Every professional script uses functions

---

## ✅ Practice Tasks

1️⃣ Write a function to print "Scan started"

2️⃣ Write a function that checks if port is 22

3️⃣ Return True if username is admin
