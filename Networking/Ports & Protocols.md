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

---

# High-Priority Protocol Security Risks

## 1. FTP — Cleartext Credential Theft
- **Port:** 21/TCP (control)
- **Risk:** Username, password, and transferred data can be exposed because standard FTP does not encrypt them.
- **Example:** Imagine you log in to an FTP server using your username and password while connected to an untrusted network. Someone monitoring that traffic may be able to read your credentials.
- **Impact:** An attacker could access files using the stolen credentials.
- **Prevention:** Use SFTP over SSH or properly configured FTPS.

## 2. SSH — Brute-Force Attacks
- **Port:** 22/TCP
- **Risk:** An attacker repeatedly tries different passwords to gain access to a remote server.
- **Example:** You manage a Linux server using SSH with a weak password such as `admin123`. An attacker repeatedly attempts to log in until they guess the password.
- **Impact:** The attacker may gain remote access and execute commands with the compromised account's privileges.
- **Prevention:** Use SSH keys, disable password authentication where appropriate, restrict access, and use rate limiting.

## 3. Telnet — Credential Sniffing
- **Port:** 23/TCP
- **Risk:** Telnet sends login credentials and session data without encryption.
- **Example:** A network administrator logs into a router using Telnet on a shared network. Someone capturing network traffic may read the username and password.
- **Impact:** Unauthorized access to the router or other systems using the same credentials.
- **Prevention:** Replace Telnet with SSH.

## 4. SMTP — Email Spoofing

- **Port:** 25/TCP
- **Risk:** An attacker forges email sender information to make a message appear to come from a trusted person or organization.
- **Example:** You receive an email that appears to come from your company's IT department asking you to reset your password through a fake website.
- **Impact:** Phishing, credential theft, fraud, or malware delivery.
- **Prevention:** Configure SPF, DKIM, and DMARC, and train users to identify suspicious messages.

> [!Important]
>  SMTP itself is not inherently vulnerable to spoofing in every configuration. Email authentication controls such as SPF, DKIM, and DMARC help reduce sender impersonation.

## 5. DNS — DNS Spoofing
- **Port:** 53/TCP/UDP
- **Risk:** An attacker manipulates DNS responses so a domain name resolves to the wrong IP address.
- **Example:** You type your bank's website address, but manipulated DNS information directs your browser to a fake website designed to steal your login credentials.
- **Impact:** Credential theft, phishing, and traffic redirection.
- **Prevention:** Use secure DNS infrastructure, DNSSEC validation where supported, and trusted network configurations.

## 6. HTTP — Traffic Sniffing
- **Port:** 80/TCP
- **Risk:** HTTP does not encrypt web traffic.
- **Example:** You submit a login form over HTTP on an untrusted Wi-Fi network. A person monitoring the connection may be able to read the transmitted information.
- **Impact:** Stolen credentials, exposed private information, and modified web content.
- **Prevention:** Use HTTPS and avoid submitting sensitive information over unencrypted connections.

## 7. HTTPS — Weak TLS Configuration

- **Port:** 443/TCP for HTTP/1.1 and HTTP/2
- **Risk:** Incorrect encryption settings or certificate validation problems can weaken the protection HTTPS is intended to provide.
- **Example:** A company server supports outdated TLS settings. An attacker may exploit a known weakness if the required conditions are present.
- **Impact:** Depending on the weakness, information could be exposed or the secure connection could be compromised.
- **Prevention:** Use current TLS configurations, valid certificates, secure cipher suites, and proper certificate validation.

> [!note]
> HTTPS is designed to protect traffic. Its mere presence does not mean the website is unsafe.

## 8. SMB — Unauthorized File Access

- **Port:** 445/TCP
- **Risk:** Improper permissions or vulnerable SMB services may allow unauthorized access to shared files or systems.
- **Example:** A company shares a folder containing employee records but accidentally grants access to every user on the network.
- **Impact:** Confidential data exposure, data modification, or malware spreading between systems.
- **Prevention:** Apply least-privilege permissions, patch SMB systems, restrict network exposure, and disable SMBv1 where it is not needed.

## 9. SNMP — Information Disclosure

- **Ports:** 161/UDP (queries), 162/UDP (traps)
- **Risk:** Weak SNMP community strings or insecure versions can expose information about network devices.
- **Example:** A router uses a default community string that an unauthorized person discovers. Depending on the permissions, they may retrieve device information or modify settings.
- **Impact:** Network mapping, device information disclosure, and potentially unauthorized configuration changes.
- **Prevention:** Prefer SNMPv3 with authentication and encryption, change defaults, and restrict access to trusted management hosts.

## 10. LDAP — Directory Enumeration

- **Port:** 389/TCP or UDP, depending on the operation and implementation
- **Risk:** Poorly restricted directory queries may reveal usernames, groups, computers, and other organizational information.
- **Example:** An attacker can query an improperly exposed company directory and discover employee usernames and administrative groups.
- **Impact:** The information may help the attacker target accounts or prepare further attacks.
- **Prevention:** Restrict directory access, enforce appropriate permissions, and protect connections with TLS.

## 11. DHCP — Rogue DHCP Server

- **Ports:** 67/UDP (server), 68/UDP (client)
- **Risk:** An unauthorized DHCP server provides clients with malicious network settings.
- **Example:** You connect your laptop to a compromised office network. A rogue DHCP server assigns your laptop an attacker-controlled default gateway.
- **Impact:** Traffic may be redirected, monitored, or disrupted, depending on the network and other security controls.
- **Prevention:** Enable DHCP snooping on supported switches, secure network access, and monitor unexpected DHCP servers.


## 12. RDP — Unauthorized Remote Access

- **Port:** 3389/TCP/UDP
- **Risk:** Exposed RDP services can be targeted using stolen credentials, password guessing, or vulnerabilities.
- **Example:** A Windows computer exposes RDP directly to the Internet and uses a weak password. An attacker obtains access and may operate the computer remotely.
- **Impact:** Data theft, unauthorized control, or ransomware deployment.
- **Prevention:** Use a VPN or secure gateway, enable MFA where supported, restrict access, and keep systems patched.


## 13. NFS — Insecure File Exports

- **Port:** Commonly 2049/TCP/UDP, depending on configuration
- **Risk:** Incorrect export rules or file permissions expose shared files to unauthorized clients.
- **Example:** A Linux server shares a sensitive directory with an overly broad set of network clients.
- **Impact:** Unauthorized reading or modification of files, depending on the permissions.
- **Prevention:** Restrict exports to trusted clients, apply least privilege, and use appropriate authentication and access controls.


## 14. BGP — Route Hijacking

- **Port:** 179/TCP
- **Risk:** Incorrect or malicious routing announcements can divert Internet traffic from its intended path.
- **Example:** A network announces a route for an IP address range that it does not legitimately control. Other networks may accept the announcement and send traffic along the wrong path.
- **Impact:** Traffic interception, service disruption, or misrouting.
- **Prevention:** Apply route filtering, prefix validation, RPKI-based Route Origin Validation, and appropriate routing policies.

## 15. MySQL — Unauthorized Database Access
- **Port:** 3306/TCP
- **Risk:** An exposed database, weak credentials, or excessive permissions can allow unauthorized access to stored data.
- **Example:** A developer leaves a database port accessible from the public Internet and uses a weak database password.
- **Impact:** Exposure, modification, or deletion of customer records.
- **Prevention:** Keep databases on private networks, restrict permitted clients, use strong authentication, and apply least-privilege database permissions.
