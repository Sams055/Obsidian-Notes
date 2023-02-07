Contents:
[[Distributed Systems]]

###### TCP Server
Q1. What kind of socket does it create/open? What communication protocol will this use? 
	- It creates/opens a ServerSocket
	- It uses TCP as it seems to create a connection
Q2. What port is the socket bound to? Who needs to know the port number? Why?
	- The server socket is bound to port 7896
	- The client needs to know the port number as it needs the port number to communicate with the server
Q3. What does the Connection object do? Why is it a thread?
	It echoes its input back to its output, assuming it is encoded as UTF-8 strings.
	It's a thread because we may want to create multiple connections for multiple clients to connect to the server simultaneously

###### TCP Client
Q4. What host and port does it send the request to
	It sends the request to the host (IP) and port 7896
Q5. What reply does it get?
	Received hello
Q6. What kind of socket does it create/open? What communication protocol will this use?
	A Socket using TCP
Q7. What address and port will it connect to?
	It sends the request to the localhost and Port 7896
	Bound to port 7896
Q8. Do you know what port the socket is bound to? Does it matter? (hint: look at the output from the TCPServer)
	It is bound (on the client end) to a random free port. The server learns the port when the client first connects. (The server prints the IP address and port that it accepts the connection from. Typically the port will be different each time you run the client.)
Q9. What will happen if you run the client when the server is not running? Will it report any error, and if so how quickly? Why/why not?
	It will fail. Specifically it reports “IO:Connection refused” almost immediately. The TCP connection request is rejected by the host if there is no process bound to the requested port. This explicit failure is communicated straight back to the client application
Q10. What will happen if you tell the client to send its request to another computer, e.g. “severn.cs.nott.ac.uk”, or “128.243.22.243”?
	Typically you will get the same result (immediate Connection refused) because there is also no process bound to that port on that machine. For some addresses you may get a long delay (typically 30-60 seconds) and then the error “IO:Connection timed out”. In this case there was not computer at that IP address (or the TCP request was filtered out before or at that computer) and no response was ever received to the connection request. Eventually the client gives up the attempted connection.

###### Dockerised Server
Q11. What command does the image specify? What should this do?
	java -cp app/project.jar comp2014.lab1.MyTCPServer This should run the TCP server in a JVM within the container.
Q12. What does this docker compose file say about how to build and run the “tcpserver” container/service? 
	- Build the image using the Dockerfile in the server/ directory 
	- Use the docker network “local” by default (docker compose normally uses a different default network) 
	- Make TCP port 7896 available (i.e. “expose” it) on the host (VM)
Q13. If a client is running in a different container, what hostname or IP address should it use to access this server instance? Why?
	

Q14. If a client is running in a different container, or on a different host (on the local network) what IP address could it use to access this server instance? Why?
	- A client on the same or a different host/VM can use the host’s IP address, e.g. “10.0.2.15”, obtained from network settings or “ip addr”.
	- (Note, 10.x.x.x, 172.x.x.x and 192.x.x.x IP addresses are all private addresses, and will only be usable within the scope of some particular local virtual or physical network. Host and network firewalls or network access controls may also prevent clients on other machines reaching the server.

