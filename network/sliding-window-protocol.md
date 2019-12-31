# 
Sliding window protocols are used where reliable in-order delivery of packets is required. The term "window" on the transmitter side represents the logical boundary of the total number of packets yet to be acknowledged by the receiver. The receiver informs the transmitter in each acknowledgment packet the current maximum receiver buffer size.

## Protocol operation
The transmitter and receiver each have a current sequence number nt and nr, respectively. They each also have a window size wt and wr. As typically implemented, nt is the next packet to be transmitted, i.e. the sequence number of the first packet not yet transmitted. Likewise, nr is the first packet not yet received. 

### Transmitter operation
Whenever the transmitter has data to send, it may transmit up to wt packets ahead of the latest acknowledgment na. That is, it may transmit packet number nt as long as nt < na+wt.

### Receiver operation
Every time a packet numbered x is received, the receiver checks to see if it falls in the receive window, nr ≤ x < nr+wr.If it falls within the window, the receiver accepts it. If it is numbered nr, the receive sequence number is increased by 1, and possibly more if further consecutive packets were previously received and stored. Whether the packet was accepted or not, the receiver transmits an acknowledgment containing the current nr.
