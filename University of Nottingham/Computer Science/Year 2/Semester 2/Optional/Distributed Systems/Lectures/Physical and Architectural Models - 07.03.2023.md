Contents:
[[Distributed Systems]]

### Introduction to Models
#### Introduction
![[Pasted image 20230306141146.png]]
- You are never going to fit the entire complexity of a system into your head at any one time.
- We abstract it into models
### Physical Models
#### Physical Models
![[Pasted image 20230306141202.png]]
- The open set of nodes has a network between them
![[Pasted image 20230306141210.png]]
- These are the physical parts of this network
![[Pasted image 20230306141216.png]]
- We need to consider these when building a system.
#### Generations of distributed systems
![[Pasted image 20230306141237.png]]
- The Internet scale is where we have a computer on every desk
- The contemporary stage is where we have potentially many computational devices per person
### Architectural Models
#### Architectural Models
![[Pasted image 20230306141343.png]]
- Architecture is about the parts that make something up and their relationships
#### Communicating Entities
![[Pasted image 20230306141358.png]]
- We have server processes, browser processes, threads within a process, etc.
- Not every distributed system has processes as an end point though
	- In some situations you may have a piece of hardware which isn't powerful enough to bother running an operating system on it.
- e.g. in this node sewn into a fabric; there's no operating system, just a piece of code which *for example* runs a C program
![[Pasted image 20230306141410.png]]
- Objects and models are good for some things, but not very good at expressing dependencies in a pluggable way.
- Suceptible to brittleness; if one thing breaks, the rest of it is likely to break
#### Communicating Paradigms
##### Interprocess Communication
![[Pasted image 20230306141653.png]]

##### Remote invocation
![[Pasted image 20230306141700.png]]

##### Indirect Communication
![[Pasted image 20230306141719.png]]
- Indirect communication has a range of ways of communicating between entities
- Group communication is very high level
- Message queues concern individual messages
![[Pasted image 20230306141730.png]]
- The entities and paradigms together give us the building blocks for our distributed system
- 
#### Roles and Responsibilities
##### Client Server
![[Pasted image 20230306142104.png]]
- Distinctions between processes are made here
##### Peer-to-peer
![[Pasted image 20230306142125.png]]
- Every process is equal here
- In the peer to peer model, processes have shared resources.
- They can communicate and exchange resources/files.
#### Placement
![[Pasted image 20230306142143.png]]
- Making decisions about where things happen may take account of what's communicating which what and what data is being exchanged etc.
#### Common Placement Strategies
![[Pasted image 20230306142203.png]]
- DNS feels like a unified service, but behind the scenes it's just multiple DNS servers working together to achieve this
- When we got a 304 in the labs, it was because of the caching
- An important example of mobile code is JavaScript running on webpages
#### Summary
![[Pasted image 20230306142217.png]]

![[Pasted image 20230306142221.png]]

### Architectural Patterns
#### Architectural Patterns
![[Pasted image 20230306142310.png]]

#### Layering
![[Pasted image 20230306142318.png]]
- This is just another kind of network stack
#### Tiered Architectures
![[Pasted image 20230306142331.png]]
- Is it possible to divide all the processes in this system into different layers / tiers
- Our typical client-server / web systems are two-tier & three-tier
#### Some more patterns
![[Pasted image 20230306142340.png]]
- Proxying means we construct an object which allows us to pass requests in a closer position to our objective.
	- Makes it faster / more reliable
- A broker acts as a common point such as the RMI registry
#### Middleware
![[Pasted image 20230306142349.png]]
- The OS gives us universal communication services e.g. TCP UDP etc.
- Middleware allows us to access more specific communication paradigms
#### Summary
![[Pasted image 20230306142651.png]]
