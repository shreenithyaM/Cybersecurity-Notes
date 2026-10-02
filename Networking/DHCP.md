# How a Device Joins the Network?

Have you ever wondered what happens when you connect your phone or laptop to a Wi-Fi network?

Within a few seconds, your device is connected and can access the internet. You didn’t manually configure an IP address, subnet mask, gateway, or DNS server — everything happened automatically.

This is possible because of DHCP (Dynamic Host Configuration Protocol).

---

## What is DHCP?

DHCP (Dynamic Host Configuration Protocol) is a network protocol that automatically assigns an IP address and other network configuration settings to devices when they join a network.

Instead of manually configuring every device, DHCP does the work automatically.

### In simple words
When your phone, laptop, or computer connects to a Wi-Fi network or an Ethernet (LAN) cable, DHCP automatically provides the information required to communicate with other devices and access the internet.

---

## What Does DHCP Provide?

When a device joins a network, DHCP assigns:
- **IP Address**
- **Subnet Mask**
- **Default Gateway**
- **DNS Server Information**

Without these settings, the device cannot communicate properly on the network.

### Example Network
Let’s use the following home network throughout this article.

| Device | IP Address |
|---------|--------------|
| Router (DHCP Server) | 192.168.1.1 |
| DHCP Scope | 192.168.1.2 – 192.168.1.100 |
| Laptop | No IP address yet |

---

# How DHCP Works (DORA Process)

DHCP follows a four-step process known as **DORA**:

- **D** — Discover
- **O** — Offer
- **R** — Request
- **A** — Acknowledgement

Let’s go through each step.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/264f66cd-e0cd-48f8-8e14-58aa1b172b47" />


---

## Step 1: Device Joins the Network
Suppose your laptop connects to your home Wi-Fi.

At this moment, the laptop knows:

- It is connected through Wi-Fi (or Ethernet if using a cable).
- It does not have an IP address yet.

Since the laptop doesn’t have an IP address, it uses a special source IP: `Source IP: 0.0.0.0`

`0.0.0.0` is called the *unspecified address*, which simply means:
> "I don’t have an IP address yet."

Now the laptop needs to find a DHCP server.

Our goal is for the laptop to receive an IP address automatically.

---

## Step 2: DHCP Discover (Client → Network)

The laptop doesn’t know the DHCP server’s IP address.

So instead of sending the request to a specific device, it sends a broadcast through its active Wi-Fi or Ethernet interface.

**The DHCP Discover packet looks like this:**

| Field | Value |
|---|---|
| Source IP | 0.0.0.0 |
| Destination IP | 255.255.255.255 |

**Note:** 255.255.255.255 is called the *limited broadcast address*.

It means:
> "Send this packet to every device on my local network."

The Wi-Fi access point or Ethernet switch forwards this broadcast throughout the local network (LAN).
Every device receives the broadcast, but only the DHCP server (our router at 192.168.1.1) responds.

The message is essentially:
> "Is there a DHCP server on this network? I need an IP address."

### Key Points
- Uses UDP
- Sent as a broadcast
- Broadcast is sent through Wi-Fi or Ethernet
- Routers do not forward 255.255.255.255, so the packet never leaves the local network

> Routers don’t forward it → they don’t send it to other networks.

---

## Step 3: DHCP Offer (Server → Client)

The router receives the Discover message.

It checks its DHCP scope: `192.168.1.2 – 192.168.1.100`

Suppose **192.168.1.10** is available.

The router sends a DHCP Offer containing:

| Setting | Value |
|---------|--------|
| IP Address | 192.168.1.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.1.1 |
| DNS Server | 8.8.8.8 |
| Lease | Time24 Hours |

The router is saying:

> "You can use IP address 192.168.1.10." 

---

## Step 4: DHCP Request (Client → Server)

The laptop accepts the offer.

It sends a DHCP Request back to the router saying:

> "I would like to use 192.168.1.10." 

This lets the DHCP server know which offered IP address the client has chosen.

---

## Step 5: DHCP Acknowledgement (ACK)

The router confirms the assignment by sending a DHCP ACK.

The message is essentially:

> "The IP address 192.168.1.10 is now assigned to you."

The laptop is now configured with:

| Setting          | Value           |
|------------------|-----------------|
| IP Address       | 192.168.1.10    |
| Subnet Mask      | 255.255.255.0   |
| Default Gateway  | 192.168.1.1     |
| DNS Server       | 8.8.8.8         |

*DHCP gives DNS IP → PC always asks that DNS server for websites.*

---

## Complete DORA Flow

```
Laptop joins Wi-Fi
        │
        ▼
DHCP Discover
Source IP      : 0.0.0.0
Destination IP : 255.255.255.255
        │
        ▼
Router (192.168.1.1)
Offers IP: 192.168.1.10
        │
        ▼
Laptop requests
192.168.1.10
        │
        ▼
Router sends DHCP ACK
        │
        ▼
Laptop Configuration
```

```
IP Address      : 192.168.1.10
Subnet Mask     : 255.255.255.0
Gateway         : 192.168.1.1
DNS Server      : 8.8.8.8
```

The laptop can now communicate with other devices and access the internet.

---

## DHCP Lease Time

- DHCP does not assign IP addresses permanently.
- Instead, each IP address is assigned for a limited period called a lease.
- When the lease expires:
  - The same IP address may be renewed.
  - Or a different IP address may be assigned.

---

## DHCP Lease Renewal
To avoid losing network connectivity, the device attempts to renew its lease before it expires.

Typically, at around 50% of the lease time, the client sends a renewal request. (DHCP lease renewal happens automatically.)
- If approved, it continues using the same IP address.
- Otherwise, a new IP address may be assigned.

---

## DHCP Release
When a device disconnects from the network, it can send a DHCP Release message.

This informs the DHCP server that the IP address is no longer needed, allowing it to be assigned to another device.

---

## DHCP Server

A DHCP Server is responsible for assigning IP addresses and network settings.

It can be:

- A home router (most common)
- A dedicated DHCP server in enterprise networks

---

## DHCP Ports

DHCP uses the User Datagram Protocol (UDP).

| Device | Port |
| --- | --- |
| DHCP Server | UDP Port 67 |
| DHCP Client | UDP Port 68 |

---

## Important IP Addresses in DHCP

- **0.0.0.0**
  - Called the *unspecified address*
  - Means the device does not have an IP address yet
  - Used as the source IP in the DHCP Discover message

- **255.255.255.255**
  - Called the *limited broadcast address*
  - Means “send this packet to every device on the local network”
  - Sent through the device’s Wi-Fi or Ethernet interface
  - Used as the destination IP in the DHCP Discover message
  - Routers do not forward this broadcast, so it remains inside the local network

---

## Why is DHCP Important?

### Without DHCP:
- Every device would need manual configuration.
- IP conflicts would occur more frequently.
- Managing large networks would be difficult.

### With DHCP:
- IP addresses are assigned automatically.
- Network configuration becomes simple.
- IP conflicts are minimized.
- Large networks become easier to manage.
