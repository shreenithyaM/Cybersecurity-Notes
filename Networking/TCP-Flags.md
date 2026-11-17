# TCP Flags & Three-way Handshake

## TCP Flags Explained Using YouTube 🎬

Imagine you are sitting at home using your computer. You open **YouTube.com** to watch a video.

Your computer needs to communicate with YouTube's server to get the video.

Let's understand the 6 main TCP flags with this simple example.

* * *

### 1\. SYN – Synchronize (Start a Connection)

You open YouTube on your computer.

Your computer sends a message to YouTube's server:

> "Hello YouTube server! I want to connect with you. Can we talk?"

Think of SYN as knocking on someone's door. 🚪

**Example:** Your computer requests a TCP connection with YouTube's server.

* * *

### 2\. ACK – Acknowledgment (I Received Your Message)

The YouTube server receives your request and replies:

> "Hello! I received your request."

ACK means acknowledgment.

**Example:** The server confirms that it received your computer's message.

* * *

### 3\. PSH – Push (Deliver the Data)

Now YouTube starts sending video data to your computer.

Your computer receives the data and passes it to the application.

PSH basically means:

> "Please deliver this data to the application as soon as possible."

**Example:** Video data is delivered to the YouTube application for processing.

* * *

### 4\. URG – Urgent (Important Data)

Imagine your computer sends some data marked as urgent.

URG tells the receiving device:

> "Pay attention to the urgent data indicated by the urgent pointer."

**Example:** TCP identifies certain data as urgent for the receiving application.

**Note:** URG is rarely used in modern everyday applications like YouTube.

* * *

### 5\. RST – Reset (Stop the Connection)

Imagine the YouTube server refuses a connection or needs to reset it.

The server sends an RST flag.

It means:

> "STOP! This connection needs to be reset immediately."

**Example:** Your computer receives a reset packet, and the TCP connection is terminated.

* * *

### 6\. FIN – Finish (Close the Connection)

You finish watching your YouTube video and close the connection.

Your computer sends FIN to the server.

It means:

> "I'm finished communicating. Let's close the connection."

**Example:** Your computer and YouTube server gracefully close their TCP connection.

---

## What is 3-Way Handshake?
It is the process used by **TCP** to **establish a connection** between client and server before sending data.

### Purpose
- Make sure both sides are ready
- Synchronize communication
- Ensure reliable connection

## 3 Steps (Very Simple)
### 1. SYN (Synchronize)
- Client → Server
- Says: **“Can we connect?”**
### 2. SYN-ACK (Synchronize + Acknowledge)
- Server → Client
- Says: **“Yes, I’m ready. Are you ready?”**
### 3. ACK (Acknowledge)
- Client → Server
- Says: **“Yes, let’s start!”**

## Easy Analogy (Phone Call 📞)
1. You: “Hello?” (SYN)
2. Friend: “Hi! Can you hear me?” (SYN-ACK)
3. You: “Yes, I can hear you.” (ACK)
Now conversation starts 

## Key Points to Remember
- Happens **before data transfer**
- Uses **3 messages → SYN, SYN-ACK, ACK**
- Ensures **reliable communication**
- Used in **TCP (not UDP)**
- If there is port is closed then  RST+ACK

---
