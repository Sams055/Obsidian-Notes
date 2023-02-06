Contents:
[[Distributed Systems]]

Q1. What kind of socket does it create/open? What communication protocol will this use? 
	- It creates/opens a ServerSocket
	- It uses TCP as it seems to create a connection
Q2. What port is the socket bound to? Who needs to know the port number? Why?
	- The server socket is bound to port 7896
	- The client needs to know the port number as it needs the port number to communicate with the server
Q3. What does the Connection object do? Why is it a thread?
	The connection object creates a specific connection with the client socket.
	<b> The above is wrong, ask why </b>
	It's a thread because we may want to create multiple connections for multiple clients to connect to the server simultaneously

Q4.
	It sends the request to the host (my IP) and port 7896
Q5.
	Received hello
Q6. 
	A Socket using UDP
Q7.
	It sends the request to the localhost and Port 7896
Q8.
- Bound to pord 7896
Q9.
