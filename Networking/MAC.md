# How Does a **MAC** Address Work?

Have you ever wondered how devices on the same Wi-Fi network know which device should receive the data?

For example, when your laptop sends a file to another laptop on the same network, how does the network know exactly which device should receive it?

This is where a **MAC** address is used.

A **MAC** address identifies a network interface at the Data Link Layer (Layer 2) and helps devices communicate within the local network.

---

## 1. What is a MAC Address?
A **MAC Address (Media Access Control Address)** is a **unique physical address** assigned to a device’s network interface.

It is used to identify devices **within a local network (LAN)**.
- Works at **Data Link Layer (Layer 2)** of OSI model
- Stored in **Network Interface Card (NIC)**
- Also called **Physical Address or Hardware Address**
---
## 2. Format
- Length: **48 bits (6 bytes)**
- Written in **Hexadecimal (0–9, A–F)**
- Example: `90-78-41-01-02-A1`

### Structure:

| Part          | Bits                                     | Meaning           | Example  |
| ------------- | ---------------------------------------- | ----------------- | -------- |
| First 24 bits | OUI (Organizationally Unique Identifier) | Manufacturer ID   | 90-78-41 |
| Last 24 bits  | Device ID                                | Unique per device | 01-02-A1 |

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/53c027a6-ca38-4924-9024-d177c2a12673" />


---
## 3. Key Features
- Unique for each device
- Assigned by **manufacturer/vendor**
- Used for **local communication (inside network only)**
- Helps switches deliver data correctly
- Used to Identify a device
- Usually **permanent**, but can be changed (called MAC spoofing)
---
## 4. OUI (Organizationally Unique Identifier)
- First **3 bytes (24 bits)**
- Assigned by **IEEE Registration Authority**
- Identifies the **vendor/company**

Example:  
`90-78-41` → Vendor  
`01-02-A1` → Device

---
## 5. MAC vs IP Address

| Feature     | MAC Address     | IP Address           |
| ----------- | --------------- | -------------------- |
| Layer       | Data Link Layer | Network Layer        |
| Type        | Physical        | Logical              |
| Assigned by | Manufacturer    | Network (DHCP/Admin) |
| Scope       | Local network   | Global (Internet)    |

---
## 6. MAC Address Formats
1. Windows: 00-10-A1-22-55-21
2. Linux/Unix/Apple/Android: 00:10:A1:22:55:21
3. Cisco: 0010.A122.5521
4. Programming/low-level configs: 0010A1225521
---
## 7. Main Purposes
**1. Device Identification**
- Every device has a **unique MAC address**
- Helps distinguish one device from another in the same network

**2. Data Delivery within LAN**
- MAC address ensures that **data frames are delivered to the correct device**
- Used by switches to forward data properly

**3. Communication at Data Link Layer**
- Works at **Layer 2 (Data Link Layer)** of the OSI model
- Handles **physical addressing** of devices

**4. Mapping IP to MAC (ARP)**
- When a device knows the IP but not the MAC, it uses **ARP (Address Resolution Protocol)**
- ARP finds the correct MAC address to send data

**5. Network Security (MAC Filtering)**
- Routers can allow/block devices using MAC addresses
- Helps in **basic network security**

>[!note]
>
>If MAC address is used to identify devices, then what is the purpose of IP address?
>
>IP is used to reach the **correct network (via routers)**
>
> **IP = Where the device is (locate a device)**
>
> MAC is used to reach the **exact device inside that network**
>
> **MAC = Who the device is (identify a device)**

---
## 8. Multiple MAC Addresses
- One device can have **multiple MAC addresses**
    - Wi-Fi adapter
    - Ethernet adapter
    - Bluetooth adapter

---

## Example 1: Two Computers on the Same Network

Imagine your home network:

<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/e0719c4b-74fa-4a46-a0be-47821f24fcf1" />


Computer A wants to send a file to Computer B.

### Step 1: Computer A Checks Computer B's IP
- **Computer A:** 192.168.1.10
- **Computer B:** 192.168.1.20

They are in the same local network (`192.168.1.x`).

**Conclusion:**
> "Computer B is on my local network." 

### Step 2: Computer A Needs Computer B's MAC Address
- **Known:** B's IP address `192.168.1.20`
- **Unknown:** B's MAC address 

**Action:**
- Sends an ARP broadcast:
```plaintext
"Who has 192.168.1.20?"
```
- Every device on the local network receives it.
- **Computer B responds:**
```plaintext
"192.168.1.20 is my IP.
My MAC address is BB-BB-BB-BB-BB-02."
```

### Step 3: Sending the Data
Now, Computer A knows:
- **IP address:** `192.168.1.20`
- **MAC address:** `BB-BB-BB-BB-BB-02`

**Communication flow:**
```
Computer A --> (MAC → BB-BB-BB-BB-BB-02) --> Computer B
```
This illustrates how, within the same network, a computer finds another device's MAC address using ARP.


---

## Example 2: Your Computer Goes to Google

Now imagine:
<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/5405adf0-0d85-4f00-9eb0-b0d21da7e777" />

```
**Computer A**
 IP: 192.168.1.10
 MAC: AA-AA-AA-AA-AA-01

    |
    |
  **Router**
- IP: 192.168.1.1
- MAC: CC-CC-CC-CC-CC-01

You type: `google.com`
```

### 1. DNS Finds Google's IP
Your computer asks DNS:
```
`google.com`
     ↓
`142.250.x.x`
```
Your computer now knows Google's IP address.

### 2. Computer Checks Whether Google is Local
Your computer has:
- My IP: 192.168.1.10
- Google IP: 142.250.x.x

These are different networks.

So, Computer A realizes:
> "Google isn't on my local network. I need to send the data to my router." 

### 3. Computer A Needs the Router's MAC Address
Computer A already knows the router's IP:
`192.168.1.1`
But it needs the router's MAC.
So it sends an ARP broadcast:
> "Who has 192.168.1.1?"
>
> The router responds:
> "192.168.1.1 is me.
> My MAC is CC-CC-CC-CC-CC-01." 

### 4. Computer Sends Data to the Router
Now, Computer A sends:
- Source MAC: AA-AA-AA-AA-AA-01
- Destination MAC: CC-CC-CC-CC-CC-01 
 - Source IP: 192.168.1.10 
 - Destination IP: 142.250.x.x 
 
**Notice this carefully:**
> Destination IP = Google's server
> 
> Destination MAC = Your router 

### 5. Router Forwards Data to Next Router
The router looks at Google's IP and decides:
> "I need to forward this toward Google." 
sends the data to the next router.

### Network Path Example:
```
Computer
   |
   | MAC
   ↓
Router 1
   |
   | MAC
   ↓
Router 2
   |
   | MAC
   ↓
Router 3
   |
   | MAC
   ↓
Google Server

```
