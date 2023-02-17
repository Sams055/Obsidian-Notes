Contents:
[[Distributed Systems]]

#### RPC and RMI Summary
![[Pasted image 20230217110658.png]]

#### Defining a remote interface
![[Pasted image 20230217110711.png]]
- 1 service has 1 interface
- Each request has a method
- Each method has a name, arguments and types
- There are exceptions for things going wrong
#### Java RMI Case Study
![[Pasted image 20230217110724.png]]
- The key building blocks are the ShapeList, Shapes and packaging.
- There's a client which is our drawing client.
- Each of our clients will talk to the same master shapelist
- The initial discovery step is done with the registry
#### Java Remote Interface Sape and Shapelist
![[Pasted image 20230217110742.png]]
- The interface for a shape has a version and state
- 
#### RMI Argument/Return types
![[Pasted image 20230217110755.png]]
- getVersion takes a primitive int and recreates the same primitive value
- We create a remote reference to the original shape object which we represent with a proxy for using the methods.
![[Pasted image 20230217110806.png]]
#### ShapeListServant 
![[Pasted image 20230217110847.png]]
- Creates an interface for the shape
- Another class we haven't seen
- 
#### Implementing a Remote Object
![[Pasted image 20230217110913.png]]
- We call these classes to implement the interface
#### Naming class of Java RMIregistry
![[Pasted image 20230217111015.png]]

#### ShapeListServer with main method
![[Pasted image 20230217111044.png]]
- We wanted to make untrusted code run in a relatively safe way on our system
#### Server Program
![[Pasted image 20230217111123.png]]

#### Client of ShapeList
![[Pasted image 20230217111141.png]]

#### Client Program
![[Pasted image 20230217111214.png]]

#### RMI Case study walkthrough
![[Pasted image 20230217111239.png]]
- Start a new java vm and start the shapelist server
- Proxy for original object is created
- We send a remote reference to the shapelist proxy object
#### Java RMI Summary
![[Pasted image 20230217111300.png]]

#### Java RMI/Docker issues
![[Pasted image 20230217111308.png]]
- For security purposes, the registry will only allow machines on the same network to talk to it.