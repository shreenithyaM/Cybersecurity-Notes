# Classes of IP Addresses

<img width="700" height="258" alt="image" src="https://github.com/user-attachments/assets/de8b97e1-7b42-49f6-9cc7-8893ee7a8334" />

## 1. What is IPv4?

**IPv4 (Internet Protocol version 4)** is a system used to identify devices on a network.

An IPv4 address has 32 bits, usually written as four decimal numbers separated by dots.

### Example:

`192.168.1.10`

Each number is called an *octet* and ranges from 0 to 255.

So:

`192 . 168 . 1 . 10`

`8     8     8    8 = **32 bits**`

Every device on an IPv4 network can have an IP address, such as:

- Laptop: `192.168.1.10`
- Phone: `192.168.1.11`
- Printer: `192.168.1.20`
- Router: `192.168.1.1`

### Why do we need IP addresses?
They allow devices to identify where data should go.

Think of an IP address like a house address:

> "Send this packet to house 192.168.1.10."

---

## 2. What is IPv6?

IPv6 is the newer version of the Internet Protocol, designed largely because IPv4 has a limited number of addresses.

- IPv4: `192.168.1.10`
- IPv6: `2001:db8:1234:5678:abcd:ef01:2345:6789`

IPv6 uses 128 bits, compared with IPv4's 32 bits.

That means IPv6 can provide an enormous number of addresses.

> For learning networking, it's useful to master IPv4 and subnetting first, because the concepts are easier to visualize.

---

## 3. What is a Default Gateway?

Suppose your computer has:

- **IP address:** 192.168.1.10
- **Subnet mask:** 255.255.255.0
- **Default gateway:** 192.168.1.1

Your computer can communicate directly with devices on its local network.

Example: **PC → 192.168.1.20**

> But what if you want to access Google?

Google's server isn't on your local network.

Your PC sends the traffic to the default gateway, usually your router:

```
PC (192.168.1.10)
      |
      ↓
Router (192.168.1.1)
      |
      ↓
Internet
      |
      ↓
Google
```

So you can think of the <mark>default gateway as the door out of your local network.</mark>

### Typical Home Network Configuration:
- PC → `192.168.1.10`
- Phone → `192.168.1.11`
- Printer → `192.168.1.20`
- Router → `192.168.1.1`

The router's address `192.168.1.1` is commonly configured as the default gateway.

---

## 4. What is a Subnet Mask?

This is one of the most important concepts.

A subnet mask tells a device which portion of an IPv4 address represents the network and which portion represents the host/device.

### Example:

- **IP address:** 192.168.1.10
- **Subnet mask:** 255.255.255.0

### Conceptually:

```
192.168.1 | 10
  NETWORK | HOST
```

The first three octets identify the network, while the last octet identifies the device within that network.

### Examples of devices on the same network:
- 192.168.1.10
- 192.168.1.20
- 192.168.1.50
- 192.168.1.100

because they all have:
- **Network:** 192.168.1
- **Subnet mask:** 255.255.255.0

---

## 5. What is Subnetting?

Subnetting means dividing one network into smaller networks.

Imagine you have one large network:

```
192.168.1.0/24
```

A `/24` network normally has 256 addresses:
- `192.168.1.0`
- `192.168.1.255`

You could divide it into smaller networks.

For example, divide it into four `/26` networks:
`256 ÷ 4 = 64`

- **Network 1:** `192.168.1.0` - `192.168.1.63`
- **Network 2:** `192.168.1.64` - `192.168.1.127`
- **Network 3:** `192.168.1.128` - `192.168.1.191`
- **Network 4:** `192.168.1.192` - `192.168..1..255`

This is useful when you want different groups of devices to have separate networks.

For example:

| Network Address | Purpose       |
|-------------------|---------------|
| 192..168..1..0/26 | Employees     |
| 192..168..1..64/26 | Guests        |
| 192..168..1..128/26 | Servers      |
| 192..168..1..192/26 | IoT devices   |


---

## 6. What does /24 mean?

You'll frequently see IP addresses written like:

`192.168.1.10/24`

The `/24` is called **CIDR notation**.

> **CIDR - Classless Inter-Domain Routing**

### Common CIDR Notation Examples and Their Subnet Masks

<img width="826" height="1136" alt="image" src="https://github.com/user-attachments/assets/35d26a89-047f-4f9e-9327-a48194b0f9fb" />


### Notes on Usable Host Addresses in IPv4 Networks
For typical IPv4 networks, usable host addresses are usually **2 fewer** than the total addresses because:
- One address identifies the network.
- One address is used for broadcast.

---

## 7. How do they all work together?

Consider this computer:

- **IP address:** 192.168.1.10
- **Subnet mask:** 255.255.255.0
- **Default gateway:** 192.168.1.1

The computer determines:

**My network:** 192.168.1.0/24

## Communication Scenarios

### Talking to a local device:
Suppose it wants to talk to:
- **Another local device:** 192.168.1.20

The computer sees:
- **Destination IP:** 192.168.1.20
- It checks the network:
  - **Same network?** Yes.
- So it communicates directly.

### Talking to a device on another network:
Suppose it wants:
- **8.8.8.8**

The computer sees:
- **Destination IP:** 8.8.8.8
- It checks the network:
  - **Different network?** Yes.
- It sends the packet to the default gateway (router):
  - **Default gateway IP:** 192.168.1.1
- The router forwards it to the internet.

### Relationship Overview
| Concept             | Question                                              |
|---------------------|--------------------------------------------------------|
| IP address          | "Who am I?"                                           |
| Subnet mask         | "What network am I on?"                                |
| Subnetting          | "How can I divide networks into smaller networks?"   |
| Default gateway     | "Where do I send traffic destined for other networks?"|
| IPv4 / IPv6       | "Which addressing protocol am I using?"               |

