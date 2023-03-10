Contents:
[[Distributed Systems]]

### Indirect Communication
#### Indirect Communication
![[Pasted image 20230310094411.png]]
- These are reusable across a wide range of applications
![[Pasted image 20230310094422.png]]
- We use an intermediary with no direct coupling
- Our previous methods didn't have a middleman
#### Indirection in Computer Science
![[Pasted image 20230310094437.png]]
- The less indirect, the faster it is
#### Space and time uncoupling
![[Pasted image 20230310095056.png]]
- To send a message you usually need to specify IP address & port etc.
- We may not have to specify the recipient in this model
- Sometimes things go wrong, e.g. emergency responder communication stops working because one of them goes out of range. This is a model that fixes that issue
##### In distributed systems
![[Pasted image 20230310095120.png]]
- The top row is direct, the bottom row is indirect
- Each example we look at will occupy one of these quadrants
#### Aside: Time uncoupling vs asynchronous communication
![[Pasted image 20230310095015.png]]
- Asynchronous message passing can happen as a result of the API you're using; some APIs may be using blocks in threads etc.
- Sometimes the client just sends the request, doesn't care about the result and moves on to something else.
- There is a family of networking protocols such as Delay Tolerant Networking etc. which helps with time uncoupling
#### Indirect communication paradigms
![[Pasted image 20230310095409.png]]
- We have many paradigms for the different way of sending the message
#### Communicating entities and communication paradigms
![[Pasted image 20230310095512.png]]
- We add to our menu of ways of having the problem-oriented entities communicate
#### Summary
![[Pasted image 20230310095522.png]]


### Group Communication
#### Group Communication
![[Pasted image 20230310100040.png]]
- A good example is a shared whiteboard with multiple people viewing and drawing on the whiteboard simultaneously
- If there are multiple individuals which need to be messages, this is group communication
#### Group programming model
![[Pasted image 20230310100051.png]]
- Processes can join or leave a group
- if you are in a group, a message sent to a group is delivered to *all* member of that group
#### Group communication options
![[Pasted image 20230310100102.png]]
- 
![[Pasted image 20230310100110.png]]
- A process may belong to many groups simultaneously in an overlapping group
#### Implementation issues
##### Reliability
![[Pasted image 20230310100120.png]]
- Low-level multicast is not reliable (similar to UDP)
- For group communication to be reliable, it's more complicated than TCP as that only deals with one to one connections.
- We need to make sure the messages have integrity, validity and get to all the group members
##### Ordering
![[Pasted image 20230310100129.png]]
- Order should be maintained across the group. However, if messages are interleaved:
- A sends 1,2,3 at the same time B is sending 4,5,6 and C is sending 7,8,9
- We could end up with something along the lines of 1,4,2,5,6,7,3,8,9 at D
- Total order requires us to wait around to check if we managed to get our send in before the others or not
##### Group membership management
![[Pasted image 20230310100146.png]]
- We need to deal with the failure of group members as well
###### The role
![[Pasted image 20230310100200.png]]
- Software needs to handle the basic capability of sending a message to all current members
#### Summary
![[Pasted image 20230310100218.png]]
- Group communication is less widely used than other systems.
### Publish-subscribe
#### Publish-Subscribe
![[Pasted image 20230310100257.png]]
- More widely used than group systems
#### The paradigm
![[Pasted image 20230310100307.png]]
- Conceptually, you publish an event, and all interested subscribers get a copy of it
#### Applications of pub-sub
![[Pasted image 20230310100316.png]]
- Could be things like updates to the stock exchange, or youtube videos being uploaded
#### pub-sub characteristics and options
![[Pasted image 20230310100326.png]]
- Some systems can guarantee success, whereas others do not e.g. best-effort
#### Subscription (filter) model
![[Pasted image 20230310100341.png]]
- These are the most widely used options
![[Pasted image 20230310100351.png]]
- Semantic filtering may involve making something look like predicate logic, with a ruleset etc.
- 
#### Centralised vs distributed implementations
![[Pasted image 20230310100404.png]]
- Centralised = easy to make, easy to break
- Distributed = hard to make, hard to break
#### A network of event brokers
![[Pasted image 20230310100415.png]]

#### Event routing in a distributed event system
![[Pasted image 20230310100424.png]]
- Brokers could be smart and filter messages coming in
	- Can match subscriptions up in advance
#### Summary
![[Pasted image 20230310100438.png]]
