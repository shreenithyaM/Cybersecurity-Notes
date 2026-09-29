# Networking Devices

## 1. Router 
- Connects different networks together.
- Operates at the **Network Layer (Layer 3)**.
- Uses IP addresses to route packets.
- Chooses the best path for data.
- Can connect a LAN to the Internet.
- Often provides security features like NAT and firewall functions.
### Example
**Home Wi-Fi Network**
- A router connects home devices to the Internet.
- It directs traffic between smartphones, laptops, and the ISP network.

<img width="299" height="168" alt="image" src="https://github.com/user-attachments/assets/c40e2aa4-057f-489f-b275-8b744d27341f" />

---
## 2. Switch 
- Connects multiple devices in a LAN.
- Operates mainly at the **Data Link Layer (Layer 2)**.
- Uses MAC addresses to forward data.
- Sends data only to the intended device.
- Reduces network congestion.
- More efficient than a hub.
### Example
**Company Office**
- 30 computers are connected to a switch.
- When Employee A sends a file to Employee B, the switch sends the data only to Employee B's computer.

<img width="600" height="283" alt="image" src="https://github.com/user-attachments/assets/aedfffb2-1245-4cb2-959b-c6c5673d91b2" />

---
## 3. Hub
- A hub is a basic networking device that connects multiple computers.
- Operates at the **Physical Layer (Layer 1)** of the OSI model.
- Does not examine data packets.
- Broadcasts incoming data to **all connected devices**.
- No traffic management or filtering.
- Less secure and less efficient than switches.
### Example
**School Computer Lab**
- 10 computers are connected through a hub.
- When Computer A sends data to Computer B, the hub sends that data to all 10 computers.
- Only Computer B accepts the data; others ignore it.

<img width="322" height="156" alt="image" src="https://github.com/user-attachments/assets/ad60c71d-0846-4b99-8cbd-7d5427e0f9ed" />


---
## 4. Bridge 
- A **network device** that connects **two similar LAN networks**.
- It filters and forwards data based on **MAC addresses**.
- Reduces network traffic by sending data only to the required network.
- Works at the **Data Link Layer (Layer 2)** of the OSI model.
### Example:
- Connecting two office LANs to act as a single network.

<img width="318" height="159" alt="image" src="https://github.com/user-attachments/assets/52500476-6f6f-4762-b70e-25998949f833" />


---
## 5. Repeater
- Used to extend the distance of a network.
- Regenerates and amplifies weak signals.
- Operates at the **Physical Layer (Layer 1)**.
- Does not understand data content.
- Helps reduce signal loss.
### Example
**Large Office Building**
- Network cable runs for 150 meters.
- Signal becomes weak after 100 meters.
- A repeater is installed midway to strengthen the signal.

---
## 6. Gateway
- Connects networks that use different protocols.
- Acts as a protocol converter.
- Operates across multiple OSI layers.
- Enables communication between dissimilar systems.
- Considered the "door" between different networks.
- Operates at the **Multiple Layers**.
### Example
**Banking System**
- A bank's internal network uses one protocol.
- An external payment network uses another protocol.
- A gateway translates data so both networks can communicate.
<img width="318" height="159" alt="image" src="https://github.com/user-attachments/assets/692b70d1-f1c4-4880-9197-8eab3ff54d51" />

---
## 7. Modem
- Modem stands for **Modulator-Demodulator**.
- Converts digital signals to analog signals and vice versa.
- Connects a home or office network to the Internet.
- Common types: DSL, Cable, Fiber modem.
- Usually provided by an Internet Service Provider (ISP).
- Operates at the **Physical Layer & Datalink Layer**.
### Example
**Home Internet Connection**
- A laptop sends digital data.
- The modem converts it into a form suitable for transmission through the ISP network.
- Internet access becomes possible.
![[Pasted image 20260601213351.png]]
---
## 8. Firewall
- A **security device/software** that monitors and controls incoming and outgoing network traffic.
- It **allows or blocks data packets** based on predefined security rules.
- Protects networks and computers from **unauthorized access, hackers, and malware**.
- Can be **hardware-based**, **software-based**, or both.
### Example:
- A firewall blocks suspicious connections from the Internet while allowing safe traffic.
---
## 9. Wireless Access Point (WAP)
- Provides wireless connectivity to a wired network.
- Allows Wi-Fi devices to join a LAN.
- Extends wireless coverage.
- Commonly connected to a switch or router.
- Supports multiple wireless devices simultaneously.
- Operates at the **Datalink Layer (Layer 2)**.
### Example
**College Campus**
- A WAP is installed in a library.
- Students connect laptops and phones through Wi-Fi.
- The WAP links these wireless devices to the college network.
---
## 10. Server
- A **server** is a computer or device that provides services, data, or resources to other computers (**clients**) on a network.
- It receives requests from clients and sends back responses.
- Can store files, host websites, manage emails, or run applications.
- Usually has higher processing power and storage than client computers.
### Example:
- A web server stores and delivers web pages to users' browsers.
---
## 11. NIC (Network Interface Card)
- Hardware that allows a device to connect to a network.
- Every NIC has a unique **MAC Address**.
- Can be wired (Ethernet) or wireless (Wi-Fi).
- Operates at **Physical and Data Link layers**.
- Essential for network communication.
### Example
**Desktop Computer Connection**
- A desktop has an Ethernet NIC.
- The LAN cable is plugged into the NIC.
- The computer can now communicate with other devices on the network.
<img width="299" height="168" alt="image" src="https://github.com/user-attachments/assets/31e2c573-b6bb-4eb7-ba01-359c05a50b21" />

