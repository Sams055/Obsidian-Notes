Contents:
[[Distributed Systems]]

##### Remote Procedure Calls
###### Slide
![[Pasted image 20230214110503.png]]
- What's a programmer friendly way of working over a network?
- Programmers are familiar with procedure calls
- So let's try create remote procedure calls for networks
- We need to nail the 3 key considerations for RPCs
###### Programming with Interfaces
![[Pasted image 20230214110514.png]]
- Design implementation strategies usually involve working some kind of contract between an implementation and some other code that's gonna make use of it
- Often have encapsulation
- Implementation can be written in a different language as long as it follows the same rules
###### Local vs remote procedure
![[Pasted image 20230214110520.png]]
- We are interested in one piece of code calling another piece of code on another system
- We need to define an interface between the two systems
- Code running across boundaries must be doing something more than a local procedure call
- Some systems have some level of shared memory, but in general we have to have the variables on each system as separate variables due to system differences
![[Pasted image 20230214110526.png]]
- Sending pointers across a network aren't going to work here
- That pointer will point to something on the other system's memory, not what it was pointing to in it's original system's memory.
###### Interface Definition Languages IDLs
![[Pasted image 20230214110545.png]]
- We need a language to define our interface
- We could use a language with a built in interface
###### CORBA IDL Example 
![[Pasted image 20230214110552.png]]
- The struct holds the data
- The interface holds methods that can be invoked on the struct
###### RPC call semantics
![[Pasted image 20230214110600.png]]
- If you call printf once in your program, it runs only once.
- However, something could go wrong; could crash and the program is broken
- We can change how things are executed with semantics
![[Pasted image 20230214110617.png]]

###### Transparency
![[Pasted image 20230214110624.png]]
- The idea of transparency is making the things that don't matter invisible.
- Once you have access on another machine, location transparency is usually free
- Most RPC systems will look like local procedure calls
###### Summary
![[Pasted image 20230214110631.png]]
##### Remote Method Invocation
###### Slide
![[Pasted image 20230214110744.png]]
- With a normal procedure call, there's no sense of explaining what or where that procedure is.
- Exactly the same as RPC, but we can use OOP.
###### Regular Object Model
![[Pasted image 20230214110844.png]]
- The object model is what we see in Java or C++
###### Distributed Objects
![[Pasted image 20230214110928.png]]

###### Implementing RMI
![[Pasted image 20230214110936.png]]
- A reference to an object would just be a memory address
- To take the local reference and make it meaningful in another process, we'd need to send the address as well as supporting information such as IP addresss, port number etc.
![[Pasted image 20230214110941.png]]
- Let's say we ask for the time.
- We have a method to get the time.
- We package all the information about the request
- Send it off over the network using information built into the proxy.
- Gets the request to the right process on the other side.
- The request is invoked on the actual object on the other side
- A reply is sent and unpacked making it seem as if both sides were in the same place.
###### Summary
![[Pasted image 20230214110952.png]]

##### Java RMI
###### Slide
![[Pasted image 20230214111100.png]]
- Not massively used now.
- This is Java Exclusive
###### Remote Interfaces in Java RMI
![[Pasted image 20230214111107.png]]
- If the RMI finds something doesn't work, an exception will be thrown
- Has a set of constraints for arguments and return types
###### Java Remote interfaces Shape
![[Pasted image 20230214111113.png]]

###### Serializable vs Remote
![[Pasted image 20230214111154.png]]
- Copying primitives is straight forward
- If you see Serializable, it gives a hint that the class has serializable types
	- Creates a copy of the object
- If you see remote
	- Creates a remote reference to the object
###### Implementing a Remote Object
![[Pasted image 20230214111201.png]]
- Constructor of the class needs to throw an exception
###### RMI Registry
![[Pasted image 20230214111208.png]]
- Finding remote objects when we start is important
- How do you find the first remote reference?
	- We use the RMI registry
- The rmiregistry acts as a broker
- Remote objects use URL-like strings
- Random servers on random ports can be accessed with a registry
###### The Naming class of Java RMIregistry
![[Pasted image 20230214111216.png]]
- These methods will let us interact with the registry
###### RMI Summary
![[Pasted image 20230214111222.png]]

