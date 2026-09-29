# Introduction to Computer Networks

## **What is a computer network?**
A computer network is the interconnection of two or more devices(node or host) that communicate with each other to share information, data, and resources through wired or wireless connections.

Example: In a typical home, devices like smartphones, laptops, and smart TVs connect to a Wi-Fi router. The router acts as a central hub, allowing the devices to access the internet and share data. For example, you could download a movie on your laptop and stream it to your smart TV over the network. This is a simple example of a computer network in everyday life.

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/c93ec191-d155-40cc-ae5c-118c91708c5a" />


---

## What is Internet?
The **Internet** is a global network of connected computers and devices that communicate with each other using standard protocols.

### ISP (Internet Service Provider)
An **ISP** is a company that gives you access to the Internet.
They connect your home, mobile, or office to the global network.
**Examples in India:**
- Reliance Jio
- Airtel
- BSNL

## Tier System (Internet Backbone Levels)

### Tier 1 ISP
Top-level networks that form the **backbone of the Internet**  
They don’t pay anyone for internet access (peer with each other)

**What they do:**
- Carry global internet traffic
- Connect continents and countries

**Examples (global):**
- AT&T
- Verizon
- NTT Communications
- Tata Group

### Tier 2 ISP
Medium-level providers  
Buy internet from Tier 1 and also connect to other networks

**What they do:**
- Provide internet to businesses and smaller ISPs
- Mix of buying + peering

**Examples in India:**
- Tata Communications
- Bharti Airtel
- Reliance Jio

### Tier 3 ISP

**What they do:**
- Deliver internet directly to homes and small businesses
- Buy bandwidth from Tier 2

**Examples in India:**
- ACT Fibernet
- Hathway
- Local cable operators in cities

> [!note]
> 
>  **Is there any owner of the Internet?**
> 
> No, the Internet has no single owner; it is a global network managed by many organizations and companies.

> [!note]
>
>  **Why do we pay for the Internet?**
>
> We pay ISP providers for **access, data usage, speed, and the network infrastructure** that connects us to the Internet.

---
### Difference between Wi-Fi, Router and Internet.
- **Wi-Fi:** The wireless signal that lets your devices connect to the router.
- **Router:** The physical device that connects your devices to the internet and manages data traffic.
- **Internet:** The global network of servers and data that your router gives you access to.

> [!tip]
> 
> You **can have Wi-Fi without internet** (devices talk to each other locally) and you **can have internet without Wi-Fi** (wired connection through a router or modem or ethernet).
>
> For a deeper explanation, refer to this blog post: [Blog](https://medium.com/@br10xe.cy/wi-fi-without-internet-a-simple-experiment-that-changed-my-understanding-of-networking-3c4aeb4f75b5)

> [!NOTE]
>
> Broadband vs. Wi-Fi
> 
> | Broadband | Wi-Fi |
> |---|---|
> | Internet connection provided by an ISP. | Wireless connection between devices and a router. |
> | Uses fiber, cable, DSL, etc. | Uses radio waves. |
> | Brings internet to the router. | Connects devices to the router. |
>
> **Example:**
> 
> - Broadband = the main water pipe into your home.
>
> - Wi-Fi = how water is distributed around the house.
> 
> **Key point:**
>
> You can have broadband without Wi-Fi (Ethernet), and Wi-Fi can work without internet for local device communication.

> [!IMPORTANT]
> 
> Bandwidth is how much data a connection can carry per second, not how fast the signal physically travels.
> 
> 100 Mbps → 100 million bits/second
> 
> 1 Gbps → 1 billion bits/second


---
## Types of Networks

### PAN (Personal Area Network)
- **Range:** A few meters (very small)
- **Use:** Connects personal devices like phones, tablets, laptops, and wearables.
- **Example:** Bluetooth connection between **mobile phone and wireless headphones**.

### LAN (Local Area Network)
- **Range:** Limited to a **single building or campus**
- **Use:** Share resources like files, printers, and internet within a small area.
- **Example:** Office network at **Tata Consultancy Services office** or home Wi-Fi network.
#### Topologies Used:
- Ring topology
- Star topology
- Bus topology
### CAN (Campus Area Network)
- **Range:** Medium-sized area — usually within a **campus, university, corporate park, military base, or industrial area**
- **Use:** Connects multiple **LANs** within a limited geographic area under a single organization.
- **Example:** A university network connecting the library, hostels, departments, and administration buildings; or a company campus network.

### MAN (Metropolitan Area Network)
- **Range:** Covers a **city or town**
- **Use:** Connects multiple LANs in a city to provide network services.
- **Example:** **City internet network in Bangalore** connecting government offices or schools.

### WAN (Wide Area Network)
- **Range:** Large area — **across cities, countries, or continents**
- **Use:** Connects LANs and MANs over long distances; can be global.
- **Example:** The **Internet**, or **Reliance Jio’s national network connecting across India**.

### WLAN (Wireless LAN)
- **Range:** Similar to LAN but **wireless**
- **Use:** Provides wireless internet access in a home, office, or campus.
- **Example:** Wi-Fi network at **home using JioFiber or Airtel Xstream**.

---
## Internet VS Intranet VS Extranet

| Internet                | Intranet                      | Extranet                                          |
| ----------------------- | ----------------------------- | ------------------------------------------------- |
| Public network.         | Private network.              | Private network with external access.             |
| Accessible to everyone. | Accessible only to employees. | Accessible to employees and authorized outsiders. |
| Example: Google.        | Employee portal.              | Supplier/Customer portal.                         |

---
## Client–Server Architecture
- A network model where **clients** request services and **servers** provide services.
- The **client** sends a request to the server.
- The **server** processes the request and sends back a response.
- Centralized management of data and resources.
- Commonly used in web applications, email systems, and databases.

**Example:**
- **Client:** Web browser (Chrome, Firefox)
- **Server:** Web server hosting a website

**Flow:**  
Client → Request → Server → Response → Client.

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/a6622b6e-5918-4c0d-a7ce-8826616b35df" />

- **File Server:** A computer that stores and manages files for multiple users on a network.
- **Web Server:** A computer dedicated to responding to requests (from the browser client) for web pages.
---
## Peer-to-Peer (P2P) Network
- A network model where all computers (**peers**) have equal status.
- Each computer can act as both a **client** and a **server**.
- Resources are shared directly between computers without a central server.
- Easy to set up and suitable for small networks.
- Less secure and harder to manage than client-server networks.

**Example:** File sharing between computers on the same network.

**Flow:**  
Peer ↔ Peer (direct communication and resource sharing).

<img width="241" height="209" alt="image" src="https://github.com/user-attachments/assets/6afea58f-5e2c-4320-af1e-d399d346dc4e" />

---
## Advantages of Computer Networking
1. **Resource Sharing** – Share printers, files, and software.    
2. **Communication** – Easy exchange of emails and messages.
3. **Data Sharing** – Quick access to shared data.
4. **Cost Saving** – Reduces hardware and software costs.
5. **Centralized Management** – Easier administration and backup.
6. **Remote Access** – Access resources from different locations.

## Disadvantages of Computer Networking
1. **Security Risks** – Vulnerable to hacking and malware.
2. **High Setup Cost** – Initial installation can be expensive.
3. **Network Failure** – Failure of network devices can disrupt work.
4. **Maintenance Required** – Needs regular monitoring and updates.
5. **Data Privacy Issues** – Unauthorized access may occur.
6. **Virus Spread** – Malware can spread quickly across the network.
