## **How is data (or a file) transmitted from one device to another over a network?** (Wireless/Ethernet)

### i) File → Binary:
- When you send a file over a network, the file (for example, a photo) is first converted into a **binary format** — a long sequence of 0s and 1s.
- Computers communicate using binary because digital devices understand these two states (on/off).
- Example: A small piece of data might look like this in binary:  
    `01001101 10101010 11100011 00011100 10101010`
- This represents 5 bytes of data (since 1 byte = 8 bits).

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/1b6cc5f4-1ed9-47c3-bf4a-339414315324" />


### ii) Dividing into Packets:
- Networks don’t send the whole file as one big chunk. Instead, data is **divided into smaller pieces called packets**.
- For simplicity, your example divides data into packets of 2 bytes each, but in real networks, packets are usually larger.
- Each packet contains:
	- **Data**: A portion of the binary file (e.g., `01001101 10101010`)
	- **Sender info**: MAC or IP address of the device sending the data
	- **Receiver info**: MAC or IP address of the destination device
	- **Error check**: Extra information to ensure the data wasn’t corrupted during transmission
- Multiple packets (Packet 1, Packet 2, Packet 3, etc.) are sent separately and reassembled at the receiving end.

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/6596d3fc-d31b-4301-ba35-f23588911710" />


### iii) Network Interface Card (NIC):
- Every device connected to a network has a **Network Interface Card (NIC)**.
- The NIC is responsible for sending and receiving data.
- It **converts digital data into signals** that can travel through cables or wirelessly:
- For sending: digital data → electrical or light signals
- For receiving: electrical or light signals → digital data
- This conversion allows devices to physically communicate over the network medium (like Ethernet cables or Wi-Fi).

<img width="299" height="168" alt="image" src="https://github.com/user-attachments/assets/7a513d6d-adb5-41f7-8d2a-6d618a1479bf" />

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/38f62463-271c-4a66-b5b7-631d6f3380c4" />


### v) Packet Reception and Reassembly:
- When packets reach the destination device, the NIC receives the incoming signals and converts them back into digital data.
- The network software then checks each packet for errors using the error-check information included earlier.
- All packets are then **reassembled in the correct order** to recreate the original file exactly as it was sent.
- If any packets are missing or corrupted, the receiver can request those packets to be resent.

### iv) Transmission Over the Network:
- Once converted into signals by the NIC, the packets travel through the network’s physical medium — this could be Ethernet cables, fiber optics, or wireless signals (Wi-Fi).
- Along the way, network devices like **switches** and **routers** help forward each packet toward its destination by reading the packet’s address information.
- Packets may take different routes, depending on network traffic and path availability.
  
> [!note]
> 
> A NIC is used for Ethernet and Wi-Fi communication, while a USB controller manages communication with USB devices. Both act as hardware controllers that manage data transfer, but they serve different types of connections.
