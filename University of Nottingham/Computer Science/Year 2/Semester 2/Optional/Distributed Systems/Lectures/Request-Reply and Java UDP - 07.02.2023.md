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
- Quality of Service - performance & other non-functional character
###### Heterogeneity
- All the parts of a distributed system have to work together, even if some are made differently
- Typically this means using common protocols, interfaces and encodings
	- Perhaps supported by common libraries, tools and services.
- 
- Java Data Input/Output streams 
	- See also External Data Representation (later)
###### Failure Handling
- ![[Pasted image 20230207094110.png]]
- 
###### Concurrency
- ![[Pasted image 20230207094131.png]]
- 
##### Request-Reply
###### Protocols
- ![[Pasted image 20230207094221.png]]
- 
###### API / Data requirements
- ![[Pasted image 20230207094419.png]]
- 
###### Message Structure
- ![[Pasted image 20230207094753.png]]
- 
###### Implementation Notes
- ![[Pasted image 20230207094935.png]]
- 
- ![[Pasted image 20230207094944.png]]
- 
###### TCP vs UDP
- ![[Pasted image 20230207095002.png]]
- 
##### Java UDP Programming
###### Java UDP API
- ![[Pasted image 20230207095033.png]]
- ![[Pasted image 20230207095056.png]]
- ![[Pasted image 20230207095122.png]]
###### UDP Considerations
- ![[Pasted image 20230207095140.png]]
- ![[Pasted image 20230207095150.png]]
- 
##### External Data Representation (EDR) 
###### EDR and marshalling
- ![[Pasted image 20230207095211.png]]
- 
###### EDR examples for Java
- ![[Pasted image 20230207095341.png]]
- ![[Pasted image 20230207095350.png]]
- 
