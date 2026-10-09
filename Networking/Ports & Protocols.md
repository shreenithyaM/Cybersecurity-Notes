# Ports & Protocols

## What is a Protocol?
A **protocol** is a set of rules that defines how devices communicate over a network.
Examples:
- **HTTP** – Used for web communication.
- **HTTPS** – Secure web communication.
- **FTP** – File transfer.
- **TCP** – Reliable data transmission.
- **UDP** – Fast, connectionless data transmission.
---
## What is a Socket?
A socket is a software endpoint used for network communication. It combines an IP address and a port number, allowing applications to send and receive data over a network.
IP Address + Port = 192.168.1.10:5000

---
## What is a Port Number?
A **port number** is a logical endpoint used by protocols to identify specific services on a device.
It helps the system know _which application_ should receive the data.
- Range: **0 – 65535**
- Example: Web traffic usually goes through port **80**
### Port Ranges

| Range         | Type             | Description                             | Example                              |
| ------------- | ---------------- | --------------------------------------- | ------------------------------------ |
| 0 – 1023      | Well-known ports | Reserved for common services            | HTTP → 80<br>HTTPS → 443<br>FTP → 21 |
| 1024 – 49151  | Registered ports | Assigned to specific applications       | MySQL → 3306                         |
| 49152 – 65535 | Dynamic/Private  | Used temporarily by client applications | 49152 - 65535                        |

---

## 1. Web & Internet Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---|---|---|---|---|---|
| HTTP | 80 | TCP | Transfers web pages and data | Simple, widely supported | No built-in encryption | Websites |
| HTTPS | 443 | TCP | Secure web communication using TLS | Encryption, integrity, server authentication | TLS adds overhead; configuration matters | Banking, shopping, secure websites |
| HTTP/3 | 443 | UDP (QUIC) | Modern version of HTTP | Faster connection setup, improved performance on changing networks | Requires QUIC support | Modern browsers and websites |
| DNS | 53 | TCP/UDP | Resolves domain names to IP addresses | Makes websites easier to access | Traditional DNS queries are often unencrypted and can be spoofed | Browsing websites, domain resolution |

---

## 2. Email Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---:|---|---|---|---|---|
| SMTP | 25 | TCP | Transfers email between mail servers | Standard email delivery protocol | Plain SMTP alone is not encrypted | Mail server-to-server delivery |
| SMTP Submission | 587 | TCP | Sends email from a client to a mail server | Supports authentication and STARTTLS | Requires correct authentication and TLS configuration | Sending emails from email applications |
| SMTPS | 465 | TCP | Email submission with implicit TLS | Encrypted connection from the start | Requires compatible configuration | Secure email submission |
| POP3 | 110 | TCP | Retrieves emails from a mail server | Simple email retrieval | Limited synchronization; messages may be downloaded locally | Basic email clients |
| POP3S | 995 | TCP | Retrieves email over TLS | Protects email retrieval in transit | Requires TLS support | Secure POP3 connections |
| IMAP | 143 | TCP | Accesses and synchronizes email on a server | Folders and messages stay synchronized across devices | Requires server storage and network access | Email clients on phones and computers |
| IMAPS | 993 | TCP | Secure IMAP communication | Encrypts email access in transit | Requires TLS configuration | Secure email synchronization |

### Remember
- **SMTP:** Sends email.
- **POP3:** Retrieves email, often by downloading messages locally.
- **IMAP:** Accesses and synchronizes email across devices.
- **TLS:** Protects email communication in transit.

Use TLS-enabled configurations wherever possible.

---

## 3. Remote Access & Administration Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---:|---|---|---|---|---|
| SSH | 22 | TCP | Secure remote login and command execution | Encryption, authentication, secure administration | Exposed services or weak credentials can be attacked | Linux servers, Kali Linux, cloud servers |
| Telnet | 23 | TCP | Remote command-line access | Simple and easy to use | Transmits credentials and data without encryption | Legacy systems and isolated labs |
| RDP | 3389 | TCP/UDP | Remote graphical access to Windows | Full desktop access; UDP can improve responsiveness | Exposed services and weak credentials create security risks | Windows administration and remote support |
| VNC | Commonly 5900+ | Usually TCP | Remote graphical desktop sharing | Works across different operating systems | Security depends on encryption and authentication configuration | Remote desktop support |

### Remember
- **SSH (22):** Secure remote command-line access.
- **Telnet (23):** Unencrypted remote command-line access.
- **RDP (3389):** Remote graphical access, commonly for Windows.
- **VNC (5900+):** Remote desktop sharing across operating systems.

**Security tip:** Prefer SSH over Telnet, and protect RDP and VNC using strong authentication, encryption, firewalls, and VPNs where appropriate.

---

## 4. File Sharing & Transfer Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---|---|---|---|---|---|
| FTP | 21 (control); 20 (data in traditional active mode) | TCP | Transfers files between clients and servers | Widely supported | Standard FTP does not encrypt credentials or data | File transfer servers and legacy systems |
| SMB | 445 | TCP | Shares files, folders, and printers | Integrates with Windows networks and access controls | Misconfiguration or vulnerabilities can expose shared resources | Windows file sharing and Active Directory environments |
| NFS | 2049 | TCP/UDP, depending on version and configuration | Shares files between networked systems | Convenient shared storage for Unix/Linux systems | Incorrect permissions or exposure can compromise data | Linux servers, shared storage, virtualized environments |

### Remember
- **FTP:** Transfers files between systems.
- **SMB:** Shares files and printers, commonly in Windows networks.
- **NFS:** Shares files, commonly in Unix/Linux environments.

**Security tip:** Prefer encrypted file-transfer alternatives such as SFTP or FTPS over standard FTP when transferring sensitive data.

---

## 5. Network Configuration & Management Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---|---|---|---|---|---|
| DHCP | UDP 67 (server), 68 (client) | UDP | Automatically assigns IP addresses and network settings | Reduces manual configuration and address errors | Rogue DHCP servers can provide malicious settings | Home routers, enterprise networks |
| NTP | 123 | UDP | Synchronizes system clocks | Provides consistent timestamps for logs and security investigations | Misconfigured or untrusted time sources can cause problems | Servers, routers, security monitoring |
| SNMP | UDP 161 (queries), 162 (traps) | UDP | Monitors and manages network devices | Centralized monitoring and alerting | SNMPv1/v2c community strings are not encrypted | Routers, switches, printers, monitoring systems |
| LDAP | 389 | TCP/UDP, depending on operation and implementation | Queries and manages directory information | Centralized identity management and directory lookup | Unencrypted connections and weak access controls can expose information | Directory services, enterprise identity systems |
| LDAPS | 636 | TCP | Provides LDAP communication over TLS | Protects directory traffic in transit | Requires correct certificate and TLS configuration | Secure directory connections |

### Remember
- **DHCP:** Automatically assigns IP addresses.
- **NTP:** Synchronizes system clocks.
- **SNMP:** Monitors and manages network devices.
- **LDAP:** Accesses and manages directory information.
- **LDAPS:** Protects LDAP communication using TLS.

**Security tip:** Prefer SNMPv3 with authentication and encryption, and use TLS-protected directory connections wherever possible.

---

## 6. Routing & Database Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---:|---|---|---|---|---|
| BGP | 179 | TCP | Exchanges routing information between autonomous systems | Enables Internet-scale routing and policy control | Misconfiguration and route hijacking can affect connectivity | ISPs, large enterprise networks, Internet routing |
| MySQL | 3306 | TCP | Connects applications to MySQL database servers | Widely supported relational database connectivity | Exposed databases and weak credentials create security risks | Web applications, backend APIs, database servers |

### Remember
- **BGP (179):** Exchanges routing information between autonomous systems on the Internet.
- **MySQL (3306):** Enables applications to communicate with MySQL database servers.

**Security tip:** Restrict database access to trusted systems, use strong authentication, and avoid exposing database ports directly to the public Internet.

---

## 7. Windows Networking Protocols

| Protocol | Port | TCP/UDP | Functionality | Advantages | Disadvantages | Where do we use it? |
|---|---:|---|---|---|---|---|
| NetBIOS Name Service (NBNS) | 137 | UDP | Resolves NetBIOS names | Supports legacy Windows name resolution | Can expose host information; susceptible to spoofing | Legacy Windows LANs |
| NetBIOS Datagram Service | 138 | UDP | Provides connectionless messaging | Supports broadcast-based communication | No guaranteed delivery or ordering | Legacy Windows networks |
| NetBIOS Session Service | 139 | TCP | Provides session-based communication | Supports older SMB communication | Legacy service may increase the attack surface | Older Windows file-sharing environments |

### Remember
- **Port 137:** NetBIOS name resolution.
- **Port 138:** NetBIOS datagram messaging.
- **Port 139:** NetBIOS session-based communication.

**Security tip:** Modern Windows networks generally use SMB directly over TCP port 445. Disable legacy NetBIOS services when they are not required.
