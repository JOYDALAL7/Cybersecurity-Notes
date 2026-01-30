# 🌐 Networking Fundamentals – Part 3

## IP Addressing & Subnetting

---

## 1. What is an IP Address?

An IP address is a unique numerical identifier assigned to a device on a network.
It allows devices to locate and communicate with each other.

---

## 2. IPv4 Address Format

IPv4 addresses consist of four octets separated by dots.

Example:

192.168.1.10

Each octet ranges from 0 to 255.

---

## 3. Binary Representation

IP addresses are stored in binary but represented in decimal for readability.

Example:

192.168.1.1 = 11000000.10101000.00000001.00000001

---



## 4. Public vs Private IP Addresses

### Public IP

- Globally unique
- Used on the Internet
- Assigned by ISP

### Private IP

- Used in local networks
- Not routable on the Internet

Private IP ranges:

10.0.0.0 – 10.255.255.255

172.16.0.0 – 172.31.255.255

192.168.0.0 – 192.168.255.255

---


## 5. Subnetting

Subnetting divides a large network into smaller logical networks.

Benefits:

- Better performance
- Improved security
- Easier management

---



## 6. Subnet Mask

A subnet mask separates the network portion and host portion of an IP address.

Example:
IP Address: 192.168.1.10
Subnet Mask: 255.255.255.0

---



## 7. CIDR Notation

CIDR uses a suffix to represent the network portion.

Example:
192.168.1.0/24

Common CIDR values:

- /24 → 256 IPs
- /25 → 128 IPs
- /26 → 64 IPs

---

## 8. Network ID and Broadcast Address

For a subnet:

- Network ID → first address
- Broadcast Address → last address

Example:

192.168.1.0/24

- Network ID: 192.168.1.0
- Broadcast: 192.168.1.255
- Usable hosts: 192.168.1.1 – 192.168.1.254

---

## 9. Security Relevance

IP addressing and subnetting define network boundaries.

Used in:

- Network scanning
- Firewall rules
- Intrusion detection systems

Understanding IP ranges is essential for cybersecurity.
