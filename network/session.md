A session is a temporary and interactive information interchange between two or more communicating devices. An established communication session may involve more than one message in each direction. A session is typically stateful, meaning that at least one of the communicating parties needs to hold current state information and save information about the session history in order to be able to communicate.

Most client-server sessions are maintained by the transport layer - a single connection for a single session. However each transaction phase of a Web/HTTP session creates a separate connection.

## Software implementation

### Server-side web sessions
Server-side sessions are handy and efficient, but can become difficult to handle in conjunction with load-balancing/high-availability systems and are not usable at all in some embedded systems with no storage. The load-balancing problem can be solved by using shared storage or by applying forced peering between each client and a single server in the cluster, although this can compromise system efficiency and load distribution.

### Client-side web sessions
Client-side sessions use cookies and cryptographic techniques to maintain state without storing as much data on the server. 

### HTTP session token
A session token is a unique identifier that is generated and sent from a server to a client to identify the current interaction session. The client usually stores and sends the token as an HTTP cookie and/or sends it as a parameter in GET or POST queries.

### Session management
Session management is the process of keeping track of a user's activity across sessions of interaction with the computer system.