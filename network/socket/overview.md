# What is socket?

Sockets allow communication between two different processes on the same or different machines.In Unix, any I/O action is doing by reading or writing a file descriptor. A file descriptor is an integer accosiate with an open file and it can be a network communication, a text file, a terminal or something else.

To a programmer, a socket looks like a low-level file descriptor.

# Where is socket used?

A Unix socket is used in a client-server application framework.

# Socket types

- Stream sockets: Delivery in a network environment is guaranteed.
  Example: TCP
- Datagram sockets: Delivery in a network environment is not guaranteed.
  Example: UDP
- Raw sockets: 
- Sequenced packet sockets