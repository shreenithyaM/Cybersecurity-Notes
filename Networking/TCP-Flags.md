# TCP Flags & Three-way Handshake
TCP uses flags to control communication.

## 1. SYN (Synchronize)
Used to initiate a connection. 
```
Client → Server
"Can I connect?"
```

## 2. ACK (Acknowledgment)
Confirms receipt of data.
```
Server → Client
"Yes, I received it."
```

## 3. PSH (Push)
Requests immediate delivery of data to the application.
Example:
```
100 MB Data
60 MB received
PSH → Deliver immediately
Remaining data can continue arriving
```
Useful for:
- Chat messages
- Interactive applications

## 4. URG (Urgent)
Marks urgent data that should be processed first.
Example:
```
A | B | C
Normal order:A → B → C
If C is urgent:
URG → Process C immediately
```

## 5. FIN (Finish)
Used to terminate a connection.
```
Client → Server
"I have finished sending data."
```

## 6. RST (Reset)
Immediately aborts a connection.
```Connection terminated instantly```

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

## TCP Four-Way Handshake
**TCP Four-Way Handshake** is the process used to **properly close a TCP connection** between a client and server, so no data is lost.
### Steps:


| Step | Sender          | Message | Meaning                          |
| ---- | --------------- | ------- | -------------------------------- |
| 1    | Client → Server | FIN     | “I want to close my connection.” |
| 2    | Server → Client | ACK     | “Okay, I received your request.” |
| 3    | Server → Client | FIN     | “I am also ready to close.”      |
| 4    | Client → Server | ACK     | “Okay, connection closed.”       |
