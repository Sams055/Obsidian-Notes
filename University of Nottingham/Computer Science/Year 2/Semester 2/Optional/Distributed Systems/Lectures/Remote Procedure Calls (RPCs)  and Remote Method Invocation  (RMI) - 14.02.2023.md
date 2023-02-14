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
- 
###### CORBA IDL Example 
![[Pasted image 20230214110552.png]]

###### RPC call semantics
![[Pasted image 20230214110600.png]]

![[Pasted image 20230214110617.png]]

###### Transparency
![[Pasted image 20230214110624.png]]

###### Summary
![[Pasted image 20230214110631.png]]

##### Remote Method Invocation
###### Slide
![[Pasted image 20230214110744.png]]

###### Regular Object Model
![[Pasted image 20230214110844.png]]

###### Distributed Objects
![[Pasted image 20230214110928.png]]

###### Implementing RMI
![[Pasted image 20230214110936.png]]

![[Pasted image 20230214110941.png]]

###### Summary
![[Pasted image 20230214110952.png]]

##### Java RMI
###### Slide
![[Pasted image 20230214111100.png]]

###### Remote Interfaces in Java RMI
![[Pasted image 20230214111107.png]]

###### Java Remote interfaces Shape
![[Pasted image 20230214111113.png]]

###### Serializable vs Remote
![[Pasted image 20230214111154.png]]

###### Implementing a Remote Object
![[Pasted image 20230214111201.png]]

###### RMI Registry
![[Pasted image 20230214111208.png]]

###### The Naming class of Java RMIregistry
![[Pasted image 20230214111216.png]]

###### RMI Summary
![[Pasted image 20230214111222.png]]

