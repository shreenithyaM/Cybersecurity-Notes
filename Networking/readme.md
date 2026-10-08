<img width="1024" height="318" alt="57f3e09a-066c-46f8-9d0f-85f440543b9d" src="https://github.com/user-attachments/assets/09cc3d66-7d46-4525-89bd-1f9327ee2186" />


# 🌐 Networking

This folder contains my **Networking notes, concepts, and practical commands** that I am learning as part of my Cybersecurity journey.

The goal is not just to memorize commands or protocols, but to understand **how computer networks work** and practice networking concepts directly in a Linux environment such as **Kali Linux**.

---

## 📚 Topics Covered

### 1. Introduction

Basic introduction to computer networking and why networking is important in Cybersecurity.

Topics include:
- What is Networking?
- LAN, WAN, MAN
- Client and Server
- Network Devices


📄 [Introduction](./Introduction.md)

📄 [Topologies](./Network%20Topologies.md)

📄 [Bonus Information](./Bonus%20Information.md)

📄 [Devices](./Networking%20Devices.md)


---

### 2. IP Addressing

Understanding how devices are identified and communicate using IP addresses.

Topics include:
- IPv4
- IPv6
- Public IP
- Private IP
- Subnet Mask
- Default Gateway
- CIDR Notation

📄 [IP Addressing 1](./IP%20Addresses_1.md)

📄 [IP Addressing 2](./IP%20Addresses_2.md)


---

### 3. MAC Addresses

Understanding MAC addresses and their role in local network communication.

Topics include:
- What is a MAC Address?
- MAC Address Format
- ARP
- Viewing MAC Addresses
- Network Interfaces

📄 [MAC Addresses](./MAC.md)

---

### 4. Ports & Protocols

Understanding ports and commonly used network protocols.

Topics include:
- TCP
- UDP
- TCP vs UDP
- Ports
- Sockets
- Well-Known Ports
- Common Network Protocols

| Protocol | Port | Purpose |
|---|---:|---|
| SSH | 22 | Secure Remote Access |
| FTP | 21 | File Transfer |
| DNS | 53 | Domain Name Resolution |
| HTTP | 80 | Web Traffic |
| HTTPS | 443 | Secure Web Traffic |
| SMTP | 25 | Email Transfer |

📄 [Ports & Protocols](./Ports-and-Protocols)

---

### 5. DHCP
Understanding how devices automatically receive network configuration.

Topics include:
- What is DHCP?
- DHCP Client & Server
- IP Address Assignment
- Subnet Mask
- Default Gateway
- DNS Server
- DHCP Lease
- DHCP Process

📄 [DHCP](./DHCP.md)

---

### 6. DNS
Understanding how domain names are translated into IP addresses.

Topics include:
- What is DNS?
- DNS Resolution
- DNS Records
- A Record
- AAAA Record
- CNAME
- MX
- NS
- TXT
- DNS Cache
Example:

nslookup example.com
dig example.com
host example.com

📄 [DNS](./DNS.md)

---

### 7. OSI Model
Understanding the seven layers of the OSI model.

Layer	Name
7	Application
6	Presentation
5	Session
4	Transport
3	Network
2	Data Link
1	Physical

📄 OSI Model

---

### 8. TCP/IP Model
Understanding the TCP/IP model and how it relates to real-world networking.

Topics include:
- Application
- Transport
- Internet
- Network Access
- TCP
- UDP
- IP
- ICMP

📄 TCP/IP Model

---

### 9. Network Security Basics
Introduction to networking concepts commonly used in Cybersecurity.

Topics include:
- Firewalls
- NAT
- VPN
- Proxy
- Network Segmentation
- IDS
- IPS
- Network Monitoring
- Secure Protocols

📄 Network Security Basics

---

🧠 Learning Approach
For each networking concept or command, I try to understand:

What is it?

Why is it used?

What problem does it solve?

What is the syntax?

What do the options/flags mean?

How does it work?

What happens with different inputs?

How can I observe it in practice?

How can I troubleshoot it?

Where is it useful in Cybersecurity?

🧪 Practice
These notes are meant to be practiced, not just read.

I use a Linux environment such as Kali Linux and isolated lab environments to run commands, observe network behavior, and understand how different protocols work.

Example:

ip addr
ip route
ping 8.8.8.8
ping google.com
nslookup google.com
ss -tuln

I also practice using tools such as:

Nmap
Wireshark
tcpdump

The goal is to understand what is happening behind each command, instead of simply memorizing commands.
