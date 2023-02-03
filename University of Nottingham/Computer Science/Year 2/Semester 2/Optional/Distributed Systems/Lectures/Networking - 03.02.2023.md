Contents:
[[Distributed Systems]]

- Learning Objectives
	- Layered Network Models
		- TCP/IP network protocol stack
			- ![[Pasted image 20230203092124.png]]
		- Layer 1 / layer 2: individual networks
	- The internet:
		- IP
		- TCP
		- UDP
	- Network Configuration
	- VMs, Containers and the Cloud
- Network Models
	- Internet Layer
		- ![[Pasted image 20230203092948.png]]
	- ISO Model
		- ![[Pasted image 20230203093002.png]]
- Layer 1 / Layer 2
	- Graphical representation of Layer 1 / 2
		- ![[Pasted image 20230203112219.png]]
		- 
	- Each network can use different technology, which can have different levels of bandwidth, latency and reliability.
	- A single computer can connect to several different networks
		- e.g. a phone on both WiFi and mobile data (3g, 4g)
		- e.g. a server on two different ethernets
	- Each network interface has it's own layer 2 Medium Access Control address (MAC address)
	- Some (not all) networks allow a single message to be sent to all machines on the network.
		- Like what James Harvey did on Bann during the OSC coursework
		- Can be done through ethernet, wifi, broadcast or multicast
- The Internet
	- This is an illusion of a single network provided to users and applications.
	- It's an underlying physical structure with routers interconnecting networks
	- Largely based on Layer 3, 4 & supporting layer 5 protocols such as DNS and Routing.
	- Acts as a unifying point for almost any network application
	- Does not care about what it's built on, or what it's used for, (layers 1,2 and 5 aren't really considered)
- Typical Network Protocol Stack
	- ![[Pasted image 20230203111412.png]]

- How layer 4 sees layer 3
	- ![[Pasted image 20230203112119.png]]
	- 
- The Internet Model
	- Every networked machine is either seen as a node or a host
	- Every host machine has an Internet (IP) Address
		- One for each network interface
			- e.g. 128.243.22.73
			- Could have a longer one if we're using IPv6
	- Any machine can send a packet of data to another machine
		- e.g. a datagram
		- Usually a packet is limited to 64kB or less
	- Sometimes packets are lost, delayed, corrupted or duplicated, but there is some checking for corruption
		- This is referred to as a best effort service

- How layer 5 sees layer 4
	- ![[Pasted image 20230203112045.png]]

- TCP and UDP: Streams and Messages
	- Applications don't use IP directly; they use one or more tranport protocols such as UDP or TCP
	- TCP is a bi-directional connection-oriented service for streams of bytes
		- Uses failure masking techniques
	- UDP is a 'best effort' connectionless service for packets of bytes (messages)
		- Uses IP directly
		- Is one to one, but can use multicast

	- Each application in the host is identified with a protocol-specific port number
		- e.g. TCP port 80
		- Clients usually use random unused ports

- Routing and configuration
	- Layer 2/3 networks and routing
		- Visualised
			- ![[Pasted image 20230203112733.png]]

	-  Routing and forwarding
		 - Routers have interfaces on two or more networks and forward packets from one network to the next 
		 - Host and routers have routing tables; these identify for each destination IP address which interface/host to send it to next 
		 - Hosts and routers work together to deliver each packet to its destination “hop by hop” (aka store and forward
	- Host Configuration
		- ![[Pasted image 20230203112920.png]]

	- Router Configuration
		- ![[Pasted image 20230203112936.png]]

- Java TCP example revisited
	- Parsing Arguments
		- ![[Pasted image 20230203113006.png]]

	- Looking across the layers
		- ![[Pasted image 20230203113040.png]]

- Virtual Machines, containers, the cloud and SSH
	- Machines, Virtual Machines & Containers
		- ![[Pasted image 20230203113127.png]]

	- Virtual Machine & Container Networking Components
		- ![[Pasted image 20230203113209.png]]

	- Virtual Machine & Container (main) Networking Options
		- ![[Pasted image 20230203113232.png]]

	- The Cloud
		- ![[Pasted image 20230203113248.png]]

	- SSH (Secure SHell)
		- ![[Pasted image 20230203113302.png]]
		- 
		  
		  

- Low Level Networking Summary
	- ![[Pasted image 20230203113403.png]]
	- 
- Internet Summary
	- ![[Pasted image 20230203113411.png]]
	- 
- Typical Network Protocol Stack (revisited)
	- ![[Pasted image 20230203113420.png]]
	- 
- Network Configuration Summary
	- ![[Pasted image 20230203113429.png]]
	- 
- VM, Containers and the Cloud Summary
	- ![[Pasted image 20230203113440.png]]
	- 
	- ![[Pasted image 20230203113447.png]]
	- 