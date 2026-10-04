# ARP (Address Resolution Protocol)

The Address Resolution Protocol (ARP) is a fundamental networking protocol used to map a dynamic, logical IP address (32-bit, IPv4) to a fixed, physical Machine Access Control (MAC) address (48-bit) on a local area network (LAN).

---
## How ARP Works?

Your laptop (Device A) wants to send data to a printer (Device B) in the same Wi-Fi network.
- Laptop IP: `192.168.1.10`
- Printer IP: `192.168.1.20`
- Printer MAC: `AA:BB:CC:11:22:33` (unknown to laptop initially)
### Step 1: Check ARP Cache
- Laptop first checks its **ARP cache (memory table)**
- It asks: _“Do I already know the MAC for 192.168.1.20?”_
 If YES → directly sends data (fast)  
 If NO → go to next step
 In this case: **MAC not found**
###  Step 2: ARP Request (Broadcast)
- Laptop sends a message to ALL devices:
“Who has IP 192.168.1.20? Tell me your MAC address.”
- This is sent to broadcast address: `FF:FF:FF:FF:FF:FF`
Meaning: _“Everyone listen!”_
### Step 3: ARP Reply
- All devices receive the request
- Only the printer recognizes its IP
Printer responds:
- “I have 192.168.1.20”
- “My MAC address is AA:BB:CC:11:22:33”
###  Step 4: Store in ARP Cache
- Laptop stores this mapping: `192.168.1.20 → AA:BB:CC:11:22:33`
 Now it remembers it for future use
### Final Step: Data Transfer
- Laptop now sends data directly to printer using MAC address
- No need to repeat ARP again (for some time)
---

> [!important]
> Why IPs appear in airplane mode?
> - Entries were saved **before** turning on airplane mode
> -  Cache is **not cleared immediately**
> - So old IP addresses are still displayed

---

## 1. Understanding `arp -a`
- **What it is:** A temporary "Recent Calls" log for your local network (Wi-Fi).
- **What it means:** It proves your computer recently had a basic network handshake with nearby devices.
- **What it does NOT mean:** It does not mean files or private data are being shared or stolen.
- **Life span:** The entries are temporary and automatically disappear within 2 to 20 minutes of no activity.

## 2. File Sharing over Local Network
- **Wi-Fi Transfer:** Apps like LocalSend, Quick Share, or Snapdrop talk directly over Wi-Fi. Using them will make the device show up in `arp -a`.
- **Cloud Transfer:** Sending via email, Google Drive, or WhatsApp Web goes through the internet. The devices never talk directly, so they will not show up in `arp -a`.

## 3. Is LocalSend Safe?
- **Yes:** It is open-source, fully encrypted (HTTPS/TLS), and works offline.
- **Privacy:** Your files never touch the internet or cloud servers, and no user data is collected.
- **Safety Tip:** Turn off "Quick Save" on public Wi-Fi so strangers cannot send you unwanted files.

## 4. Why the MAC Address looks different
- **MAC Randomization:** Modern phones and laptops automatically use a fake, temporary MAC address for each Wi-Fi network.
- **Purpose:** This is a built-in privacy feature that prevents public routers and advertisers from tracking your physical movements.

---

# Frequently Asked Questions (FAQs)

## Question 1: Does the `arp -a` list show devices that I have already shared data with?
- **Answer:** No. The `arp -a` command simply displays a temporary cache of devices on your local network (Wi-Fi/LAN) that your computer has recently discovered or had basic network communication with. It does not mean you have shared files, transferred data, or exposed private folders to them.

## Question 2: Why does the device list still appear even after I change my network settings or switch networks?
- **Answer:** This is normal behavior. The moment your computer connects to any network, it automatically sends out background signals to discover the router and nearby equipment. Active devices (like phones, smart TVs, and printers) instantly reply to introduce themselves, causing your computer to rebuild the ARP list within seconds.

## Question 3: Is the ARP table a historical log of past communications?
- **Answer:** Yes, but only for the very recent past. The ARP table is a local, short-term network cache. It only tracks devices on your immediate physical network (not websites on the internet), and it automatically clears out entries that have been inactive for more than 2 to 20 minutes.

## Question 4: If I transfer data from my mobile phone to my laptop, will the phone appear in the ARP list?
- **Answer:** Yes, but only if you use a local Wi-Fi transfer method.
  - If you use a local app (like LocalSend) over Wi-Fi, the devices talk directly, and the phone will appear in the list.
  - If you use a cloud method (like Email, WhatsApp, or Google Drive), the data goes through the internet instead of directly between devices, so the phone will not appear.

## Question 5: How can I transfer files directly between my devices using only the local network?
- **Answer:** You can use free local file-sharing applications that bypass the internet entirely. The best options are:
  - **LocalSend** (works across all platforms offline)
  - **Google Quick Share** (built into Android for Windows/Android transfers)
  - **Snapdrop.net** (works directly inside any web browser without installation)

## Question 6: Is the LocalSend application safe and secure to use?
- **Answer:** Yes, it is highly secure. LocalSend operates entirely offline over your local Wi-Fi router, meaning your files are never uploaded to the internet or external cloud servers. It uses strong end-to-end encryption (HTTPS/TLS), features no tracking or ads, and is fully open-source, allowing global security experts to audit its safety.

## Question 7: Why does my device's MAC address appear differently in network tools compared to its actual hardware settings?
- **Answer:** This is due to a built-in privacy feature called MAC Randomization. Modern smartphones and laptops automatically generate a fake, temporary MAC address for each Wi-Fi network they join. This prevents public network routers and advertisers from tracking your device's physical movements across different locations.
