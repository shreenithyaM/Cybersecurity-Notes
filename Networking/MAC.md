How Does a MAC Address Work?
Have you ever wondered how devices on the same Wi-Fi network know which device should receive the data?

For example, when your laptop sends a file to another laptop on the same network, how does the network know exactly which device should receive it?

This is where a MAC Address is used.

A MAC address identifies a network interface at the Data Link Layer (Layer 2) and helps devices communicate within the local network.

What is a MAC Address?
A MAC Address (Media Access Control Address) is a unique hardware address used to identify a network interface on a local network.

In simple words:

MAC Address = identifies a network interface on the local network.

It is used mainly for communication within the LAN (Local Area Network).

A MAC address operates at:

OSI Layer: Layer 2 — Data Link Layer

Protocol: Ethernet / Wi-Fi

Also called: Physical Address, Hardware Address

Example MAC Address
A MAC address is usually written as:

90:78:41:01:02:A1

It can also be written in different formats:

90-78-41-01-02-A1

or:

9078.4101.02A1

The same MAC address can therefore appear differently depending on the operating system or networking equipment.

MAC Address Format
A traditional MAC address is 48 bits, which equals 6 bytes.

Example:

90:78:41:01:02:A1

Each hexadecimal pair represents 1 byte.

Part	Value
Byte 1	90
Byte 2	78
Byte 3	41
Byte 4	01
Byte 5	02
Byte 6	A1

Therefore:

6 bytes × 8 bits = 48 bits

So:

MAC Address = 48 bits = 6 bytes = 12 hexadecimal digits

MAC Address Structure
A traditional MAC address can be divided into two major parts:

90-78-41 | 01-02-A1
   │            │
   │            └── Device/interface-specific part
   │
   └── OUI

Part	Size	Purpose
OUI	24 bits	Identifies the organization/vendor
Remaining 24 bits	24 bits	Identifies the interface

Example
90-78-41-01-02-A1
└──────┘ └────────┘
   OUI    Interface-specific part

The first 24 bits are known as the OUI (Organizationally Unique Identifier).

What is OUI?
OUI = Organizationally Unique Identifier

The OUI is the first 24 bits (3 bytes) of a traditional MAC address.

It is allocated by the IEEE Registration Authority to organizations.

For example:

90-78-41-01-02-A1
└──────┘
   OUI

The OUI can identify the organization associated with the MAC address prefix.

Note: The OUI identifies the registered organization/vendor prefix; it does not necessarily identify the exact device model.

Why Does a Device Need a MAC Address?
Suppose you have this network:

             Wi-Fi Router
             192.168.1.1
                  │
        ┌─────────┴─────────┐
        │                   │
     Laptop               Phone
 192.168.1.10          192.168.1.20

The laptop and phone both have IP addresses.

But when they communicate over the local network, the actual Layer 2 frames use MAC addresses.

For example:

Laptop
IP: 192.168.1.10
MAC: AA:AA:AA:AA:AA:AA

        │
        │ Ethernet/Wi-Fi Frame
        ▼

Phone
IP: 192.168.1.20
MAC: BB:BB:BB:BB:BB:BB

The frame contains:

Source MAC      → AA:AA:AA:AA:AA:AA
Destination MAC → BB:BB:BB:BB:BB:BB

The network can therefore determine the Layer 2 destination interface.

MAC Address and Switches
MAC addresses are especially important for network switches.

Imagine three computers connected to a switch:

Computer A ─────┐
                │
Computer B ─────┤── Switch
                │
Computer C ─────┘

Each computer has a different MAC address.

The switch learns which MAC address is reachable through which port.

For example:

Switch Port	MAC Address
Port 1	AA:AA:AA:AA:AA:AA
Port 2	BB:BB:BB:BB:BB:BB
Port 3	CC:CC:CC:CC:CC:CC

Suppose Computer A wants to send data to Computer B.

The frame contains:

Source MAC:
AA:AA:AA:AA:AA:AA

Destination MAC:
BB:BB:BB:BB:BB:BB

The switch checks its MAC address table.

It knows:

BB:BB:BB:BB:BB:BB → Port 2

So it forwards the frame toward Port 2.

In simple words:

A switch uses MAC addresses to decide where to forward Layer 2 frames.

MAC Address and ARP
Now there is an important question:

What happens if a device knows the destination IP but doesn't know its MAC address?
For example:

Laptop:
IP = 192.168.1.10

Wants to communicate with:

Phone:
IP = 192.168.1.20

The laptop knows:

Destination IP = 192.168.1.20

But it needs the destination MAC address for local Layer 2 communication.

It uses ARP (Address Resolution Protocol).

The laptop essentially asks:

"Who has 192.168.1.20?"

The device with that IP responds with its MAC address.

For example:

192.168.1.20
       ↓
BB:BB:BB:BB:BB:BB

The laptop can now create the Ethernet frame:

Source MAC:
AA:AA:AA:AA:AA:AA

Destination MAC:
BB:BB:BB:BB:BB:BB

MAC Address vs IP Address
This is one of the most important networking concepts.

Feature	MAC Address	IP Address
OSI Layer	Layer 2	Layer 3
Type	Hardware/Link-layer address	Logical address
Used by	Switches / Layer 2 networks	Routers / Layer 3 networks
Scope	Local network	Can be used across networks
Example	AA:BB:CC:11:22:33	192.168.1.10
Assignment	Usually associated with network interface	DHCP or manually configured
Changes	Usually stable, but can be changed/spoofed	Can change between networks

Simple way to remember
Think about sending a package.

IP address = Where should the package go?

MAC address = Which network interface should receive the frame on the local network?

So:

IP helps with Layer 3 delivery.
MAC helps with Layer 2 delivery.

Does a MAC Address Work Across the Internet?
Not in the same way an IP address does.

Suppose your laptop wants to access a website:

Laptop
   │
   ▼
Home Router
   │
   ▼
Internet
   │
   ▼
Web Server

Your laptop's MAC address is used on the local link.

When the packet is forwarded through a router, the Layer 2 frame is removed and a new Layer 2 frame is created for the next link.

Conceptually:

Laptop
MAC A → Router MAC
        │
        ▼
     Router
        │
        ▼
Router MAC → Next-Hop MAC

The MAC addresses are therefore link-local.

The IP packet, however, continues toward its destination.

This is why saying:

"MAC address identifies a device on the internet"

is misleading.

A better statement is:

MAC addresses are used for Layer 2 communication on a local network/link.

Types of MAC Addresses
MAC addresses can also be categorized based on how they are used.

1. Unicast MAC Address
A unicast MAC address identifies a specific network interface.

Example:

AA:BB:CC:11:22:33

A frame sent to this address is intended for a specific destination.

2. Broadcast MAC Address
The Ethernet broadcast MAC address is:

FF:FF:FF:FF:FF:FF

It means:

"Send this frame to all devices on the local Layer 2 network."

For example, ARP requests use Ethernet broadcast when the sender does not yet know the destination MAC address.

3. Multicast MAC Address
A multicast MAC address is used to deliver frames to a group of devices rather than one specific device.

Conceptually:

One sender
    │
    ▼
Multicast group
 ┌──┼──┐
 ▼  ▼  ▼
A   B  C

Only devices that are interested in the multicast traffic process it.

Multiple MAC Addresses on One Device
A device does not necessarily have only one MAC address.

For example, a laptop may have:

Wi-Fi Adapter
MAC: AA:AA:AA:AA:AA:AA

Ethernet Adapter
MAC: BB:BB:BB:BB:BB:BB

A phone may have a MAC address associated with its Wi-Fi interface and other network interfaces.

So it is more accurate to say:

A MAC address identifies a network interface, not necessarily the entire physical device.

Can a MAC Address Change?
Yes.

Although a MAC address is generally associated with a network interface, the address presented to the network can sometimes be changed.

This is called MAC spoofing or MAC address randomization, depending on the purpose.

For example:

Original MAC
AA:AA:AA:AA:AA:AA

        ↓

Presented MAC
CC:CC:CC:CC:CC:CC

Modern Wi-Fi devices may also use randomized/private MAC addresses to reduce tracking across wireless networks.

MAC Address in Wi-Fi
MAC addresses are also important in Wi-Fi communication.

Suppose your laptop connects to a Wi-Fi access point:

Laptop
MAC: AA:AA:AA:AA:AA:AA
       │
       │ Wi-Fi
       ▼
Access Point
MAC: BB:BB:BB:BB:BB:BB

The Wi-Fi network uses MAC addressing as part of its Layer 2 communication.

The access point can use MAC addresses to identify wireless stations and handle Layer 2 traffic.

MAC Address vs Router
A common confusion is:

Does the router use MAC addresses?
Yes.

A router typically has network interfaces, and each interface has a MAC address when the underlying link technology uses MAC addressing.

For example:

             Router
        ┌──────────────┐
        │              │
LAN MAC ─┤              ├─ WAN interface
        │              │
        └──────────────┘

The router may therefore have different MAC addresses associated with different interfaces.

MAC Address Example
Let's consider a simple home network.

Router
IP: 192.168.1.1
MAC: 11:11:11:11:11:11

Laptop
IP: 192.168.1.10
MAC: AA:AA:AA:AA:AA:AA

Phone
IP: 192.168.1.20
MAC: BB:BB:BB:BB:BB:BB

The laptop wants to communicate with the phone.

First, the laptop knows:

Phone IP:
192.168.1.20

It needs the phone's MAC address.

ARP resolves:

192.168.1.20
       ↓
BB:BB:BB:BB:BB:BB

The laptop can then send a Layer 2 frame:

Source MAC:
AA:AA:AA:AA:AA:AA

Destination MAC:
BB:BB:BB:BB:BB:BB

The switch/access point uses the destination MAC to deliver the frame locally.

Complete Flow
The relationship between IP, ARP, MAC, and the switch can be visualized like this:

Laptop
IP: 192.168.1.10
MAC: AA:AA:AA:AA:AA:AA
        │
        │
        │ "I need 192.168.1.20's MAC"
        ▼
       ARP
        │
        │
        │ 192.168.1.20
        │        ↓
        │ BB:BB:BB:BB:BB:BB
        ▼
     Ethernet/Wi-Fi Frame
        │
        │ Destination MAC:
        │ BB:BB:BB:BB:BB:BB
        ▼
      Switch/AP
        │
        ▼
      Phone
IP: 192.168.1.20
MAC: BB:BB:BB:BB:BB:BB

Important MAC Addresses
Address	Meaning
AA:BB:CC:11:22:33	Example unicast MAC
FF:FF:FF:FF:FF:FF	Ethernet broadcast
00:00:00:00:00:00	All-zero MAC; commonly used as a special/placeholder value, not a normal assigned destination
01:00:5E:...	Common IPv4 multicast MAC range

Where Can I Find My MAC Address?
Windows
Open Command Prompt:

ipconfig /all

Look for:

Physical Address

Example:

Physical Address. . . . . : AA-BB-CC-11-22-33

Linux
You can use:

ip link

Look for:

link/ether aa:bb:cc:11:22:33

macOS
You can check the network interface information using:

ifconfig

Android / iPhone
The MAC address can generally be found in the device's network/Wi-Fi settings, though modern devices may use a private/randomized MAC address for Wi-Fi networks.

Why is a MAC Address Important?
Without Layer 2 addressing, devices on the same network would not have the addressing information required to deliver Ethernet/Wi-Fi frames to the correct local network interface.

MAC addresses help with:

Identifying network interfaces

Delivering Layer 2 frames

Switch forwarding

Wi-Fi communication

ARP-based IP-to-MAC resolution

Broadcast and multicast communication

Basic network access-control mechanisms

MAC Address: Simple Mental Model
Think of a large apartment building.

IP Address
    ↓
Which building/network?

MAC Address
    ↓
Which specific interface in that local network?

Or simply:

IP = Where
MAC = Which local interface

MAC Address vs IP Address vs Port
There are actually three different levels involved when communicating with an application.

MAC Address
     ↓
Which local network interface?

IP Address
     ↓
Which host/network?

Port Number
     ↓
Which application/service?

For example:

MAC
AA:BB:CC:11:22:33

        ↓

IP
192.168.1.10

        ↓

Port
443

You can think of it as:

MAC  → Local interface
IP   → Host/network
Port → Application/service

This distinction becomes very important when learning Ethernet, ARP, IP, TCP/UDP, and networking in general.


