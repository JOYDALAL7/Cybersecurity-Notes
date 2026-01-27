# Computer Basics — Foundation for Cybersecurity

> Goal: Understand computer fundamentals from a security perspective.

---

## 1. What is a Computer?

A computer is a programmable electronic device that:

- Processes data
- Stores information
- Executes instructions
- Communicates with other systems

**Security perspective:**
Every component can be a target for attacks.

---

## 2. Core Components

### 2.1 CPU (Central Processing Unit)

The CPU:

- Executes instructions
- Performs calculations
- Controls system operations

**Security relevance:**

- Hardware vulnerabilities (Spectre, Meltdown)
- Instruction-level exploits
- Side-channel attacks

---

### 2.2 RAM (Random Access Memory)

RAM is:

- Temporary storage
- Fast access memory
- Volatile (data lost when power off)

**Security relevance:**

- Memory dumps can reveal secrets
- Buffer overflow attacks
- RAM forensics

---

### 2.3 Storage (Hard Drive / SSD)

Storage:

- Permanent data storage
- Survives power loss
- Contains OS, files, applications

**Security relevance:**

- Data recovery after deletion
- Encryption at rest
- Forensic analysis

---

## 3. How Computers Communicate

### 3.1 Binary (0s and 1s)

Computers understand only:

- 0 = off
- 1 = on

Everything translates to binary:

- Text
- Images
- Programs
- Network traffic

**Hacker mindset:**
Understanding binary helps in reverse engineering and exploit development.

---

### 3.2 Bits and Bytes

- 1 bit = 0 or 1
- 8 bits = 1 byte
- 1024 bytes = 1 KB
- 1024 KB = 1 MB

**Why this matters:**

- Buffer sizes in exploits
- Understanding memory layouts
- Network packet analysis

---

## 4. Software vs Hardware

### Hardware

Physical components you can touch

### Software

Programs and instructions that run on hardware

**Security truth:**
Both can be attacked. Hardware attacks are harder but more powerful.

---

## 5. Input/Output (I/O)

Input devices:

- Keyboard
- Mouse
- Network interface

Output devices:

- Monitor
- Printer
- Network interface

**Attack vectors:**

- Keyloggers
- Screen capture
- Network sniffing

---

## 6. Networking Basics

Computers communicate via:

- LANs (Local Area Networks)
- WANs (Wide Area Networks)
- The Internet

**Security reality:**
Most attacks happen over networks.

---

## 7. The Boot Process

When a computer starts:

1. BIOS/UEFI initializes hardware
2. Bootloader starts
3. Operating System loads
4. User programs run

**Attack opportunities:**

- BIOS rootkits
- Bootloader manipulation
- OS kernel exploits

---

## 8. Common Misconceptions

- "Closing my laptop = shutting down"
- "Deleting a file = it's gone forever"
- "My computer is too old to be hacked"

All false.

---

## 9. Why Understanding This Matters for Hacking

To attack systems, you must understand:

- How data flows
- Where secrets are stored
- What controls what
- Where vulnerabilities hide

---
## 10. My Understanding (Personal Notes)

### **1. What are the main computer components?**

The main components of a computer are the **CPU, RAM, storage, input devices, and output devices** .

The **CPU** acts as the brain and processes instructions, **RAM** temporarily stores data that the CPU is actively using, and **storage** permanently stores files and programs.

Input devices allow users to give instructions, while output devices display the results.

---

### **2. How does RAM differ from storage?**

**RAM** is temporary memory used to store data that the computer is currently working on, and it is cleared when the system is turned off.

**Storage** is permanent memory that keeps data even after the system is powered off.

RAM is much faster than storage, which is why active programs are loaded into RAM instead of running directly from storage.

---

### **3. Why is binary important for cybersecurity?**

Binary is important for cybersecurity because **all data, programs, and instructions are ultimately represented as 0s and 1s** .

Understanding binary helps in analyzing malware, network traffic, and system behavior at a low level.

Many security vulnerabilities and exploits operate by manipulating binary data directly.
