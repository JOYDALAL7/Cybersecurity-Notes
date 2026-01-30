# 🌐 Networking Fundamentals – Part 4

## Ports & Protocols

---

## 1. What is a Port?

A port identifies a specific service running on a device.
While an IP address identifies a system, a port identifies the application.

---

## 2. Port Number Ranges

Ports range from 0 to 65535 and are divided into:

### Well-Known Ports (0–1023)

Reserved for standard services.
Examples:

- 22 → SSH
- 80 → HTTP
- 443 → HTTPS

### Registered Ports (1024–49151)

Used by applications.
Examples:

- 3306 → MySQL
- 8080 → HTTP alternative

### Dynamic Ports (49152–65535)

Temporary client-side ports.

---

## 3. What is a Protocol?

A protocol defines rules for communication between systems, including data format and error handling.

---

## 4. TCP vs UDP

### TCP

- Connection-oriented
- Reliable
- Ordered delivery

Examples:

- HTTP
- HTTPS
- SSH

### UDP

- Connectionless
- Faster
- No delivery guarantee

Examples:

- DNS
- Streaming services

---

## 5. Common Protocols and Ports

| Protocol | Port | Purpose                |
| -------- | ---- | ---------------------- |
| HTTP     | 80   | Web traffic            |
| HTTPS    | 443  | Secure web             |
| FTP      | 21   | File transfer          |
| SSH      | 22   | Secure remote access   |
| Telnet   | 23   | Insecure remote access |
| SMTP     | 25   | Email                  |
| DNS      | 53   | Domain resolution      |
| MySQL    | 3306 | Database               |

---

## 6. Security Relevance

Open ports expose services to attackers.
Port scanning is often the first step in network attacks.

Firewalls reduce risk by limiting open ports.

---

## Key Takeaway

Ports and protocols define how services communicate.
Understanding them is essential for networking, QA testing, and cybersecurity.
