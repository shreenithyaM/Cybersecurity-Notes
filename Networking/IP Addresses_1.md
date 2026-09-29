# IP Addresses

## 1. What is an IP Address?
An **IP Address (Internet Protocol Address)** is a unique numerical label assigned to every device connected to a network.

Purpose:
- Locate a device on a network
- Helps in sending and receiving data
- Acts like an “address” on the internet
## Example:
- IPv4 → `192.168.1.1`
- IPv6 → `2001:db8::1`
---
## 2. Types of IP Addresses

<img width="700" height="265" alt="image" src="https://github.com/user-attachments/assets/64fad8c1-b990-4d18-aaeb-e7eb3c94d7d1" />


### A. Private IP Address
A **private IP address** is assigned to devices within a local network (LAN).
### Characteristics:
- Used for **internal communication**
- Private IPs are assigned either by a **DHCP server (usually the router)** or manually configured as **static IPs**.
- Not accessible directly from the internet
- Can be reused in different networks
### Example: Same Private IP in Different Networks
#### Network A (Your Home)
- Laptop → `192.168.1.10`
- Router → Public IP: `49.x.x.x`
#### Network B (Friend’s House)
- Friend’s Laptop → `192.168.1.10`
- Router → Public IP: `103.x.x.x`

> [!note]
> 
> Both devices have the **same private IP (192.168.1.10)**
> 
> This is possible because private IPs are **reusable across networks**.

## What Happens When Both Use the Internet?
### Scenario 1: You Open a Website
- Your router uses **NAT (Network Address Translation)**  
- Converts:  
  `192.168.1.10 → 49.x.x.x`
### Scenario 2: Your Friend Opens a Website
- Their router also uses **NAT**
- Converts:  
  `192.168.1.10 → 103.x.x.x`

> [!important]
>
> Even though both devices have the **same private IP**, their **public IPs are different**, so:
>
> On the internet, they appear as **completely different devices**
### Key Concept
- Private IP → Used **inside** a network  
- Public IP → Used **on the internet**  
- NAT → Translates private IP → public IP  
### Ranges:
- `10.0.0.0 – 10.255.255.255`
- `172.16.0.0 – 172.31.255.255`
- `192.168.0.0 – 192.168.255.255`
### Example:
- Phone → 192.168.1.2
- Laptop → 192.168.1.3

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/ba1ce8f1-5712-4433-95e3-d9a8efc5fed7" />


---
### B. Public IP Address
A **public IP address** is assigned to a network so it can communicate over the internet.
### Characteristics:
- Assigned by **ISP (Internet Service Provider)**
- **Globally unique**
- Visible to websites and servers
- Usually assigned to the **router**, not individual devices
### Example:
- Router → `49.xxx.xxx.xxx`
---
### C. Static IP Address
- A static IP is an IP address that **never changes**
- It is fixed for a device or internet connection
- Assigned by ISP or manually set
- Static IP is a Layer 3 (Network Layer) address configuration, where the IP address remains fixed.
### Example:
- Your IP = `49.36.120.55`
- Today, tomorrow, next month → same IP stays
### Uses:
- Web servers
- CCTV cameras
- Remote access
---
### D. Dynamic IP Address
- A dynamic IP is an IP address that **keeps changing**
- Assigned automatically by ISP using DHCP
### Example:
- Today IP = `49.36.120.55`
- After restart = `103.25.88.14`
- Next day = `117.201.33.9`
### Uses:
- Home internet
- Mobile data users
- Normal browsing

---
## 3. Key Concept: One Public IP, Many Private IPs

### In a typical home network:

| Device   | Private IP  | Public IP |
| -------- | ----------- | --------- |
| Phone    | 192.168.1.2 | 49.x.x.x  |
| Laptop   | 192.168.1.3 | 49.x.x.x  |
| Smart TV | 192.168.1.4 | 49.x.x.x  |

> [!note]
> 
> All devices share the **same public IP address** but have **different private IP addresses** inside the network.

---
## 4. Common Misconceptions

❌ Each device has its own public IP (in WiFi) 

✔ Actually: All devices share one public IP

❌ Private IP is globally unique  

✔ Actually: It is reusable
---
## 5. IPv4 vs IPv6

| Feature               | IPv4                                   | IPv6                                        |
| --------------------- | -------------------------------------- | ------------------------------------------- |
| Address Length        | 32-bit(4 bytes)                        | 128-bit(16 bytes)                           |
| Format                | Decimal                                | Hexadecimal                                 |
| Separator             | Dot (.)                                | Colon (:)                                   |
| Address Capacity      | ~4 Billion                             | ~340 Undecillion                            |
| Example               | 192.168.1.1                            | 2001:db8::1                                 |
| Address Configuration | Supports manual/<br>DHCP configuration | Supports auto-configuration/<br>renumbering |
| Addressing Scheme     | Class division(A, B, C, D, E)          | Achieved by subnetting                      |
| Security features     | dependent on application               | IPSEC is inbuilt in the IPv6 protocol       |
| Header length         | Variable, 20-60 bytes                  | Fixed, 40 bytes                             |

---
