# TCP/IP Model

The **TCP/IP model** is a 4-layer networking model used for communication over the internet.

## 1. Application Layer
- Topmost layer
- Combines **Application + Presentation + Session (OSI)**
- Provides services to user applications

### Functions:
- Data formatting
- Encryption & decryption
- Session management
- User interface for network services

### Protocols:
- HTTP / HTTPS (web)
- FTP (file transfer)
- SMTP (email)
- DNS (domain names)

---

## 2. Transport Layer
- Responsible for **end-to-end communication**

### Functions:
- Segmentation of data
- Error detection & correction
- Flow control
- Reliable / unreliable delivery

### Protocols:
- **TCP (Transmission Control Protocol)**
    - Reliable, connection-oriented
- **UDP (User Datagram Protocol)**
    - Fast, connectionless
---

## 3. Internet Layer
- Equivalent to **Network layer in OSI**

### Functions:
- Logical addressing (IP address)
- Routing (finding best path)
- Packet forwarding
### Protocols:
- IP (Internet Protocol)
- ICMP (error messages)
- ARP (address resolution)
---
## 4. Network Access Layer (Link Layer)
- Combines **Data Link + Physical (OSI)**
### Functions:
- Physical transmission of data
- MAC addressing
- Frame handling
- Error detection (basic)
### Examples:
- Ethernet
- Wi-Fi
---

# Relationship Between TCP/IP and OSI Model

| TCP/IP Model         | OSI Model Equivalent                 |
| -------------------- | ------------------------------------ |
| Application Layer    | Application + Presentation + Session |
| Transport Layer      | Transport                            |
| Internet Layer       | Network                              |
| Network Access Layer | Data Link + Physical                 |

---
## Key Differences
- OSI has **7 layers**, TCP/IP has **4 layers**
- OSI is a **reference model**, TCP/IP is **practical (used in real networks)**
- TCP/IP is simpler and widely implemented

<img width="816" height="547" alt="image" src="https://github.com/user-attachments/assets/d767cd19-d895-4b26-8c12-cc0fe891b738" />


| OSI Model                                                                      | TCP/IP Model                                                        |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| **Vertical approach**                                                          | **Horizontal approach**                                             |
| Focuses on layered architecture and interaction between layers within a system | Focuses on end-to-end communication using protocols between systems |
| More of a reference/modeling approach                                          | More of a practical communication approach                          |
| Used for understanding, design, and troubleshooting                            | Used for actual Internet communication                              |
| 7 layers                                                                       | 4 layers                                                            |

