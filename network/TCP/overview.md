# Connection-oriented

Connection-oriented describes a transmitting data in which the devices at the end points use a preliminary protocol to establish an end-to-end connection before any data is send. It's also called a _reliable_ service.

# Connection establishment
To establish a connection, TCP uses a three-way handshake. 
1. SYN: The active open is performed by the client sending a SYN request to the server. The client sets the segement's sequence number to a random value A. 
2. SYN-ACK: In response, the server replies with a SYN-ACK. The acknowledgment number is set to one more than the received sequence number i.e. A+1, and the sequence number that the server chooses for the packet is another random number, B.
3. ACK: Finally, the client sends an ACK back to the server. The sequence number is set to the received acknowledgement value i.e. A+1, and the acknowledgement number is set to one more than the received sequence number i.e. B+1.

# Connection termination
The connection termination phase uses a four-way handshake, with each side of the connection terminating independently.

# Data transfer
## Reliable transmission
TCP uses a sequence number to identify each byte of data. 

## Dupack-based retransmission
This duplicate acknowledgement is used as a signal for packet loss.

## Flow control
TCP uses an end-to-end flow control protocol to avoid having the sender send data too fast for the TCP receiver to receive and process it reliably. TCP uses a sliding window flow control protocol. 

## Congestion control
TCP uses a number of mechanisms to achieve high performance and avoid congestion collapse, where network performance can fall by several orders of magnitude. These mechanisms control the rate of data entering the network, keeping the data flow below a rate that would trigger collapse.

# Vulnerabilities
## Denial of service
* SYN-Flood
* Sockstress

## Connection hijacking

# TCP ports
TCP and UDP use port numbers to identify sending and receiving application end-points on a host, often called Internet sockets. 

# Development
* iTCP: A research effort into TCP extensions that allows applications to subscribe to TCP events and register handler components that can launch applications for various purposes.
* MPTCP: Aims at allowing a TCP connection to use multiple paths to maximize resource usage and increase redundancy.
* TCP Cookies Transcations:
* tcpcrypt:
* TCP Fast Open
