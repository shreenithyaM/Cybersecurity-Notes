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
- Packets
- Network Protocols
- OSI Model
- TCP/IP Model

📄 [Introduction](./Introduction)

---

### 2. IP Addressing

Understanding how devices are identified and communicate using IP addresses.

Topics include:

- IPv4
- IPv6
- Public IP
- Private IP
- Loopback Address
- Network Address
- Broadcast Address
- Subnet Mask
- Default Gateway
- CIDR Notation

📄 [IP Addressing](./IP-Addressing)

---

### 3. MAC Addresses

Understanding MAC addresses and their role in local network communication.

Topics include:

- What is a MAC Address?
- MAC Address Format
- MAC vs IP Address
- ARP
- Viewing MAC Addresses
- Network Interfaces

📄 [MAC Addresses](./MAC-Addresses)

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

### 5. Networking Commands

Common Linux commands used for networking and troubleshooting.

Topics include:

```text
ip
ping
ss
ip route
ip neigh
traceroute
tracepath
nslookup
dig
host
curl
wget
hostname
resolvectl

📄 Networking Commands - 1

📄 Networking Commands - 2

📄 Networking Commands - 3

6. DNS
Understanding how domain names are translated into IP addresses.

Topics include:

What is DNS?

DNS Resolution

DNS Records

A Record

AAAA Record

CNAME

MX

NS

TXT

DNS Cache

Example:

nslookup example.com
dig example.com
host example.com

📄 DNS

7. DHCP
Understanding how devices automatically receive network configuration.

Topics include:

What is DHCP?

DHCP Client & Server

IP Address Assignment

Subnet Mask

Default Gateway

DNS Server

DHCP Lease

DHCP Process

📄 DHCP

8. Routing
Understanding how packets move between different networks.

Topics include:

Routing

Routing Tables

Default Routes

Gateways

Static Routes

Network Interfaces

Example:

ip route
ip route show

📄 Routing

9. Network Troubleshooting
Learning how to identify and troubleshoot common networking problems.

Topics include:

Checking Network Interfaces

Checking IP Configuration

Testing Connectivity

Checking Routes

Testing DNS

Checking Open Ports

Tracing Network Paths

Example workflow:

ip addr
ip route
ping 8.8.8.8
ping google.com
nslookup google.com
ss -tuln

📄 Network Troubleshooting

10. OSI Model
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

11. TCP/IP Model
Understanding the TCP/IP model and how it relates to real-world networking.

Topics include:

Application

Transport

Internet

Network Access

TCP

UDP

IP

ICMP

📄 TCP/IP Model

12. Network Security Basics
Introduction to networking concepts commonly used in Cybersecurity.

Topics include:

Firewalls

NAT

VPN

Proxy

Network Segmentation

IDS

IPS

Network Monitoring

Secure Protocols

📄 Network Security Basics

13. Packet Analysis
Learning how network traffic can be captured and analyzed.

Topics include:

Packets

Frames

Headers

TCP Three-Way Handshake

DNS Queries

HTTP/HTTPS Traffic

ICMP Traffic

Packet Capture

Tools:

Wireshark

tcpdump

📄 Packet Analysis

14. Network Scanning
Learning the fundamentals of identifying hosts, ports, and services in an authorized lab environment.

Topics include:

Host Discovery

Port Scanning

Service Detection

Network Enumeration

Understanding Scan Results

Tools:

Nmap

Example:

nmap <target-ip>

📄 Network Scanning

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
