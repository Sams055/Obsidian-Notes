Contents:
[[Distributed Systems]]

### Message Queues
#### Message Queues
![[Pasted image 20230314095346.png]]
- Messages are not sent to specfic processes; they are sent to an intermediary message queue instead
#### Message Queue Paradigm
![[Pasted image 20230314095428.png]]
- Could be implemented as one service, or implemented as a distributed service
#### Message Queue Operations
![[Pasted image 20230314095438.png]]

#### Implementation Notes
![[Pasted image 20230314095447.png]]
- The queues themselves are persistent and reliable; any message sent to a queue will stay in the queue until someone takes it
- We have assurance that the message will remain uncorrupted
#### Java Messaging Service JMS
![[Pasted image 20230314095456.png]]

#### Summary
![[Pasted image 20230314095507.png]]

### Distributed Shared Memory
#### Distributed shared memory
![[Pasted image 20230314095528.png]]
- Monitoring the various reads and writes of the systems
- Almost always a lot slower than physical memory
#### Distributed shared memory abstraction
![[Pasted image 20230314095546.png]]
- Disjoint machines with disjoint physical memory on some kind of network
- We're going to make it look like they're accessing the same shared memory
- We need to identify a space which is a physically separate thing on all of the machines
### Tuple Spaces
#### Tuple space communication
![[Pasted image 20230314100018.png]]
- Still a shared data abstraction, but different to the distributed shared memory from before
- Imagine all the processes share a virtual spaces where you can place a tuple
- All values are tuples
- Can do read, write and take in a tuple space
- Tuples do not have addresses; we use pattern matching
#### The tuple space abstraction
![[Pasted image 20230314100028.png]]
- The tuple space can persist beyond the lifespan of the processes
#### Characteristics
![[Pasted image 20230314100042.png]]
- Transactions groups together database operations
	- They've either all worked, or none of them have worked
#### JavaSpaces
![[Pasted image 20230314100052.png]]

#### EQUIP2?
![[Pasted image 20230314100103.png]]

#### Common platform/toolkit for mobile phone-based experiences
![[Pasted image 20230314100124.png]]

![[Pasted image 20230314100131.png]]
- Sits in the server, getting data in or getting data out of the space.
#### Day of the figurines
![[Pasted image 20230314100227.png]]
- Go down to the physical installation (table)
- Pick a figurine to represent you
- Sign up for the game
- 1 hour of game time takes 24 hours of real time
- You play it slowly in your free time.
#### MobiMissions
![[Pasted image 20230314100313.png]]

![[Pasted image 20230314100329.png]]
- Equip service behind the scenes
- Equip based mobile app
#### EQUIP2 discussion
![[Pasted image 20230314100347.png]]
- Tight integration between the state and the notification is the most distinct part of this approach
#### Summary
![[Pasted image 20230314100356.png]]

### Example: REDIS
#### Introducing Redis
![[Pasted image 20230314100412.png]]

#### Example Redis data structures / uses
![[Pasted image 20230314100421.png]]
- Unlike a regular database, it doesn't guarantee everything
- Need some way of recovering definitive information
#### Redis Notes
![[Pasted image 20230314100433.png]]
- Very well-documented which helps with implementation.
- 
#### Example Indirect Communication Cloud Services (in Microsoft Azure)
![[Pasted image 20230314100455.png]]
- Many products which fall into the indirect communication category
