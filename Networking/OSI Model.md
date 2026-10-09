# OSI Model

- The **OSI(Open Systems Interconnection) model** is a **7-layer conceptual framework** developed by the **International Organization for Standardization (ISO)**.  
- It explains how data is transmitted between two or more devices over a network in a structured way.
- It is a **reference model**, not a physical implementation.

> What is open systems?
> A system that interacts and exchanges information with other systems and external environments using standardized communication rules.

> Which is the first layer of the OSI model?
>- Sender starts from: **Application layer (Layer 7)**
>- Receiver starts from: **Physical layer (Layer 1)**
>- Data flow:
>   - Sender: **Top → Bottom**
>   - Receiver: **Bottom → Top**


<img width="1400" height="1333" alt="image" src="https://github.com/user-attachments/assets/cd9c9906-1352-4df9-b84c-f3470bc306a6" />


**Communication Architecture:**
It is the **structured design of a communication system** that defines how data is transmitted, managed, and received between devices or systems.

---
## The 7 layers of the OSI model
A common mnemonic: **"Please Do Not Throw Sausage Pizza Away"**
1. Application Layer - [[7 Application Layer]]
2. Presentation Layer - [[6 Presentation Layer]]
3. Session Layer - [[5 Session Layer]]
4. Transport Layer - [[4 Transport Layer]]
5. Network Layer - [[3 Network Layer]]
6. Data Link Layer - [[2 Data Link Layer]]
7. Physical Layer - [[1 Physical Layer]]

---
## **Software-Based Layers (OSI Model Upper Layers)**
- **Layer 7 – Application Layer**
- **Layer 6 – Presentation Layer**
- **Layer 5 – Session Layer**
## **Core/Heart Layers (OSI Model Lower Layers)**
- **Layer 4 - Transport Layer**
## **Hardware-Based Layers (OSI Model Lower Layers)**
- **Layer 3 – Network Layer**
- **Layer 2 – Data Link Layer**
- **Layer 1 – Physical Layer**
---

| Layer | Name         | Function                         | Common Devices/Protocols                                                   | Cybersecurity Relevance                                                      |
| ----- | ------------ | -------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| 7     | Application  | User-facing network services     | HTTP, HTTPS, FTP, DNS, SMTP, SSH, IRC, POP3, IMAP, DHCP, Telnet, SNMP, NTP | Phishing, web attacks, malware, SQL Injection,<br>Cross-Site Scripting (XSS) |
| 6     | Presentation | Data formatting, encryption      | SSL/TLS, JPEG, ASCII, IMAP, SSH                                            | Encryption, certificate security, SSL Stripping                              |
| 5     | Session      | Establishes and manages sessions | NetBIOS, RPC, SOCKETS, API'S                                               | Session hijacking                                                            |
| 4     | Transport    | End-to-end communication         | TCP, UDP, SCTP, DCCP, ECN                                                  | Port scanning, DoS attacks                                                   |
| 3     | Network      | Routing and logical addressing   | IP, ICMP, Routers, IGMP, IPSec                                             | IP spoofing, routing attacks                                                 |
| 2     | Data Link    | MAC addressing, local delivery   | Ethernet, Switches, ARP, PPP, FDDI, SLIP                                   | ARP poisoning, MAC flooding                                                  |
| 1     | Physical     | Hardware and signal transmission | Cables, Hubs, Fiber, Wireless                                              | Physical tampering, cable tapping                                            |

---
### Encapsulation and De-encapsulation in the OSI Model

**Encapsulation** is the process of **adding protocol information (headers and sometimes trailers)** to data as it moves **from the sender's Application Layer (Layer 7) down to the Physical Layer (Layer 1)**.

**De-encapsulation** is the reverse process. The receiver **removes those headers and trailers** as data moves **from the Physical Layer (Layer 1) up to the Application Layer (Layer 7)** until the original message is obtained.


<img width="1042" height="745" alt="OSI-Model" src="https://github.com/user-attachments/assets/aec9009d-5ccd-4e95-a1ab-e5dfbb7541b0" />


