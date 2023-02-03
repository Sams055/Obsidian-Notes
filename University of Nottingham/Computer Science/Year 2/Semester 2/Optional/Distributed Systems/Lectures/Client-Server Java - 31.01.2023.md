Client Server
[[Distributed Systems]]
### Definition of a distributed System
- We define a distributed system as one in which hardware or software components located at networked computers communicate and coordinate their actions only by passing messages
Most applications of distributed systems are based on sharing resources
Sometimes we want to share 
- physical resources like printers, disks and computers.
- People
- Data resources e.g. files, documents, databases, web pages, 
- Computational/algorithmic resources e.g. search engines or machine learning algorithms
### Services
![[Pasted image 20230131111913.png]]

### Example Services & Associated Resources
![[Pasted image 20230131112016.png]]

### Architecture
![[Pasted image 20230131112039.png]]
- If you're thinking about how we architect / imagine a distributed systems we think of what the entities we are dealing with, e.g. processes (not always)
- How do they communicate?
- What roles and responsibilities do they have.
- Once we have an abstract model, e.g. request to print, someone how to worry about where they physically exist

### DSYS & the client-server 
![[Pasted image 20230131112243.png]]


### Java Socket Programming
![[Pasted image 20230131112314.png]]
- Senders send messages and they are received by receiver queues / buffers
- Socket is the OS's view of these endpoints

### Sockets
![[Pasted image 20230131112436.png]]
- In order to use a socket object it needs to be associated with key relevant information in the relevant protocol
- The OS has a table saying socket x is associated with address y or wildcard z
- A process can have a lot of sockets / multiple network connections
- Each socket can only be bound to a given port at any time.

### Sockets and Ports
![[Pasted image 20230131112637.png]]
- On the client side, we choose any port nobody is using
- Server side, we have an agreed port

### Message Destinations
![[Pasted image 20230131112745.png]]
- Port number identifies the process within the host
- Servers typically use well-known ports
- The server is sitting waiting for a request, the client is the one that sends that request
- The client needs to know / discover the ip address of the server
- DSYS use extra help such as name service to let you take a name and work out an IP address to figure out where you need to go.

### Address Application
![[Pasted image 20230131112929.png]]
- There will always be an API for host name resolution
- In Java it asks the OS to find the service

### Java TCP API
![[Pasted image 20230131113032.png]]
- Same sockets as COMP1007 C
- Make a specialised server object for TCP server sockets
- It will make the right OS object and bind it to the port
- ServerSocket object has an accept method.
- If a client wants to make a connection, it has a Socket object to do so
	- These sockets represent an end of a TCP connection.
	- Returned from accept in server
	- The socket object lets you read / write a sequence of bytes.

### TCP Client
![[Pasted image 20230131113348.png]]
- From the socket we get the input stream & the output stream
- A datastream is standard encoding for standard Java datatypes
- UTF Encoded stream for reading standard data types and objects
	- writeUTF
	- readUTF
### TCP Server
![[Pasted image 20230131113737.png]]
- Sits in an infinite loop until a client comes along and asks for a TCP connection.
- Starts a thread Connection as seen below upon successful connection.
Continued
	![[Pasted image 20230131113846.png]]
	The write could block if you pass enough data fast enough; reason why we `try catch`
### TCP Consideration
![[Pasted image 20230131114137.png]]
- In TCP, if the receiver needs to know how many bytes it needs to wait for
- One-one connection after connection is established
- Blocking can happen when you fill up a buffer
![[Pasted image 20230131114310.png]]
- TCP is reliable
- When the connection fails however, we can lose things and not know we lost them
- A failure model is what we use to fix this issue.
- TCP is versatile

### TCP Summary
![[Pasted image 20230131114434.png]]
