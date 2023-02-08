Contents:
[[Distributed Systems]]

##### Introduction
###### Network Protocol
- What is it?
	- A set of rules about how to communicate
		- What a service can ask for
		- What information to send
		- When to send it
		- How to encode the information
		- What to do if something goes wrong
	- If everyone follows the same rules, then effective communication is achieved
	- The protocol should be well described to make it easier for this to happen
###### Network Protocol Stacks
- It's best to organise everything in layers
- Each layer in the protocol stack has its own set(s) of protocols
- Each layer makes use of the services offered by protocols of the layer below
- Abstraction for users working at higher levels
###### Typical Network Protocol Stack
- ![[Pasted image 20230207091653.png]]
- As an application programmer we will almost always be using something with TCP or UDP
###### DSY Challenges
- A distributed system has it's own problems that you have to deal with that you wouldn't if you were just working on one machine
- Heterogeneity
	- Coping with system component variability
- Failure Handling
	- Coping with partial failure
- Concurrency
	- Correctness and performance with concurrency
- Openness - to extension or reproduction 
- Security - protection from threats
- Scalability - good performance as systems grow
- Transparency - selective abstraction
- Quality of Service - performance & other non-functional characteristics
###### Heterogeneity
- All the parts of a distributed system have to work together, even if some are made differently
- Typically this means using common protocols, interfaces and encodings
	- Perhaps supported by common libraries, tools and services.
- Java Data Input/Output streams 
	- See also External Data Representation (later)
	- All Java VMs are required to support these streams for primitive datatypes
	- 
###### Failure Handling
- ![[Pasted image 20230207094110.png]]
- If we have two or more parts, one part can fail but other parts will still run
- Think of the WWW, once site going down doesn't cause the others to go down as well
- We can abstract things to allow several different servers to implement the same service across several different machines.
- We design it to cope with something going wrong
###### Concurrency
- ![[Pasted image 20230207094131.png]]
- This is true concurrency; hence we can end up with inconsistencies
- They need to communicate and perform additional checks to make sure there is global consistency
- 
##### Request-Reply
###### Protocols
- ![[Pasted image 20230207094221.png]]
- General example for what interaction a client and server will have
- The client needs the server response as it lets the client know what's happening/happened on the server
###### API / Data requirements
- ![[Pasted image 20230207094419.png]]
- There's information that a client and server need to communicate
- The client and server need to agree how the the data should be represented (something sensible)
- You'll usually see the client blocking within a threaded language
###### Message Structure
- ![[Pasted image 20230207094753.png]]
- We don't need to explicity say the message type is a request; can be inferred
- There could be multiple requests simultaneously; hence a requestID should be used to make sure the order isn't mixed up, though TCP does not have this issue given how it functions
- If a process hosts several distributed objects; we may need a reference
- OperationID needed for multiple operations
- Arguments are usually passed in as a way of telling the server what needs to happen.
###### Implementation Notes
- ![[Pasted image 20230207094935.png]]
- e.g. we could increment the ID for each new request created
	- Should usually be enough to uniquely identify a request
- However, these are still finite, so they may repeat and need to wraparound or use another solution
- ![[Pasted image 20230207094944.png]]
- If we send a request, and we get a reply, we must have got through
- If we send a request and don't get a reply, we have to give ourselves a time we are willing to wait before we assume that something has gotten lost
- We describe the above as a Timeout
- We will need history to allow us to give a sensible reply to situations involving duplicates
###### TCP vs UDP
- ![[Pasted image 20230207095002.png]]
- TCP is more reliable and versatile
- UDP has less overhead
- TCP has no size limit whereas UDP does
##### Java UDP Programming
###### Java UDP API
- ![[Pasted image 20230207095033.png]]
- DatagramPackets represent a UDP datagram
- DatagramSockets send and recieve Datagram Packets, representing a UDP socket
- ![[Pasted image 20230207095056.png]]
- The socket should close when the program ends
- ![[Pasted image 20230207095122.png]]
- Similar to the client in terms of socket, but we make it on a well-known port since the client needs to know the port to send the request
- Waits in a while loops until it receives a request.
###### UDP Considerations
- ![[Pasted image 20230207095140.png]]
- Fragmentation means we want a small message size in the best case scenario; hence the hard limit
- ![[Pasted image 20230207095150.png]]
- Failure Model uses checksums on the receiving end to check what got sent is correct (scraps it otherwise as it doesn't know how to fix it)
- We like UDP because we can use multicast; can't do it with TCP since that only creates a connection between 2 machines
- UDP is used for specialised situations really
##### External Data Representation (EDR) 
###### EDR and marshalling
- ![[Pasted image 20230207095211.png]]
- Outside of our program, how do we represent our data?
###### EDR examples for Java
- ![[Pasted image 20230207095341.png]]
- Strings in Java are UNICODE strings
- Each character isn't necessarily just 1 byte
- Need to know how to convert characters to bytes and vice versa
- We add extra information to the stream e.g. string length, to help the recipient figure out how to decode the string
- ![[Pasted image 20230207095350.png]]
-  Technically binary encoding would be more compact, but these encodings are more readable and portable
- Some older protocols are just plain text in ASCII