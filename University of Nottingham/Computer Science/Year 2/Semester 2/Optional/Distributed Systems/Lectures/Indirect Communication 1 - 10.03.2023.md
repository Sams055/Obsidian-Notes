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

#### Group programming model
![[Pasted image 20230310100051.png]]

#### Group communication options
![[Pasted image 20230310100102.png]]

![[Pasted image 20230310100110.png]]

#### Implementation issues
##### Reliability
![[Pasted image 20230310100120.png]]

##### Ordering
![[Pasted image 20230310100129.png]]

##### Group membership management
![[Pasted image 20230310100146.png]]

###### The role
![[Pasted image 20230310100200.png]]

#### Summary
![[Pasted image 20230310100218.png]]

### Publish-subscribe
#### Publish-Subscribe
![[Pasted image 20230310100257.png]]

#### The paradigm
![[Pasted image 20230310100307.png]]

#### Applications of pub-sub
![[Pasted image 20230310100316.png]]

#### pub-sub characteristics and options
![[Pasted image 20230310100326.png]]

#### Subscription (filter) model
![[Pasted image 20230310100341.png]]

![[Pasted image 20230310100351.png]]

#### Centralised vs distributed implementations
![[Pasted image 20230310100404.png]]

#### A network of event brokers
![[Pasted image 20230310100415.png]]

#### Event routing in a distributed event system
![[Pasted image 20230310100424.png]]

#### Summary
![[Pasted image 20230310100438.png]]
