# TCP & UDP

## 1. Transport Layer – Introduction

-   The Transport Layer is Layer 4 of the OSI model.

-   It provides communication between applications running on different devices.

-   It uses two main protocols: TCP and UDP.

-   It handles data delivery, segmentation, and port numbers.

## 2. What is TCP?

TCP (Transmission Control Protocol) is a connection-oriented protocol that provides reliable data transmission.

Important points:

-   Establishes a connection before sending data.

-   Ensures data reaches the destination.

-   Maintains the correct order of data.

-   Retransmits lost data.

-   Uses acknowledgements (ACK).

Example: Web browsing, email, file transfer.

## 3. What is UDP?

UDP (User Datagram Protocol) is a connectionless protocol that sends data without establishing a connection.

Important points:

-   No connection establishment.

-   No guarantee of delivery.

-   No guarantee of data order.

-   No built-in retransmission.

-   Faster and has less overhead in many applications.

Example: Online gaming, video calls, live streaming.

## 4. TCP vs UDP

| TCP | UDP |
| --- | --- |
| Connection-oriented | Connectionless |
| Reliable | No delivery guarantee |
| Slower generally | Faster generally |
| Maintains data order | No ordering guarantee |
| Uses acknowledgements | No acknowledgements |
| Minimum header: 20 bytes | Header: 8 bytes |
| Example: HTTPS | Example: Online gaming |

## 5. TCP Data Transmission

TCP sends data from one device to another reliably.

Important points:

-   Data is divided into smaller segments.

-   Each segment has a sequence number.

-   The receiver sends an ACK (acknowledgement).

-   TCP ensures data arrives in the correct order.

-   Lost data is retransmitted.

Example: When downloading a file, TCP ensures all data is received correctly.

## 6. TCP Sequence Numbers & Acknowledgements (ACK)

Sequence Number:

-   Identifies the position of data bytes in a TCP connection.

-   Helps the receiver arrange data in the correct order.

Acknowledgement (ACK):

-   Confirms that data has been received.

-   The ACK number indicates the next byte expected.

Example:

-   Sender sends 100 bytes starting with sequence number 1.

-   Receiver sends ACK \= 101.

-   This means the receiver expects byte 101 next.



## 7. TCP Retransmission (Lost Packets)

TCP retransmission means sending data again when it is believed to be lost.

How it works:

1.  Sender sends a TCP segment.

2.  Receiver does not receive it.

3.  Sender does not receive the expected ACK.

4.  Sender retransmits the missing data.

5.  Receiver acknowledges the data.

Important terms:

-   Timeout: Sender waits for an ACK. If it doesn't arrive within the timeout, data may be retransmitted.

-   Fast Retransmit: TCP can retransmit data after receiving multiple duplicate ACKs, without waiting for a timeout.


## 8. TCP Connection Termination (FIN, ACK)

TCP uses a four-step process to close a connection gracefully.



Four steps:

1.  FIN: Client requests to close the connection.

2.  ACK: Server acknowledges the request.

3.  FIN: Server sends its own connection termination request.

4.  ACK: Client acknowledges it.

The TCP connection is now closed.

