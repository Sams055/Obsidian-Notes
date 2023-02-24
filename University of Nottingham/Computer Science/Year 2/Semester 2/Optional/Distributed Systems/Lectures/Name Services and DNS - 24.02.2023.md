Contents:
[[Distributed Systems]]

### Name Services
#### Names
![[Pasted image 20230224112533.png]]
- Whenever we need to identify one amongst several, a name is a good way of doing it.
- Identifiers are more convenient for computers to use e.g. national insurance numbers
	- easy for computers, but harder for us to remember
#### Names in Distributed Systems
![[Pasted image 20230224112545.png]]
- A name is important to describe the particular processes and resources we're working with.
- In DSys an IP address allow us to send IP datagrams to the correct machine.
- There's nothing to stop you in defining a new service which has it's own way of naming things
#### URIs, URNs, URLs
![[Pasted image 20230224112556.png]]
- We wanted a way to name everything in the world
- We needed to create a uniform / consistent way to represent this.
- We created uniform designations for resource identifiers, names and locators
![[Pasted image 20230224112611.png]]
- Each layer has it's own methods which interact with the data to make it interpretable/useful for the respective layer.
- We break down the link, and split the data so they can individually go to the correct place.
#### Name Services
![[Pasted image 20230224112622.png]]
- A name service represents a set of attributes which are bound to a particular name
- You can have a tree of names with subnames with their own subnames and so on.
- If names are not bound, they are unbound without information.
- The range of possible names are subdivided to create subspaces of names
#### Example: JavaRMI registry
![[Pasted image 20230224112636.png]]
- Any RMI client can talk to it
- There's a host name level and and object name level
- For any given host, there's it's own list of of object names
#### Directory Services
![[Pasted image 20230224112657.png]]
- Name service is our entry level service where you know the name.
- If we don't have a name, we can use a directory service
- In terms of just naming, dns is universal, but there isn't a true universal system for directories
#### Name Services Summary
![[Pasted image 20230224112719.png]]

### DNS - Domain Name System
#### DNS name space
![[Pasted image 20230224112841.png]]
- The name system is written backwards:
	- in "www.cs.nott.ac.uk" uk is the first one to be considered
#### DNS Applications and Resource Records
![[Pasted image 20230224112901.png]]
- DNS gets used most for host name resolution.
- We have the name of the host and we need the IP address to make the connection
- There's a record with the alias of certain names; e.g. if you look x up, where x is the alias of y, y will be loaded
#### DNS data records
![[Pasted image 20230224113108.png]]
- CNAME represents an alias
- A represents the IPV4 address
- MX represents emails (in this example)
#### Other (less important) applications
![[Pasted image 20230224113122.png]]
- Host information has security issues; we don't use it often

#### Multiple records / values
![[Pasted image 20230224113131.png]]
- In general, we can have several records linked to the same domain name
- We can't have multiple CNAME records (SLIDE IS WRONG)
- We can have several hosts perform the same service.
#### Administrative domains
![[Pasted image 20230224113140.png]]
- The critical step is that DNS subdivides all the possible names into separate administrative domains
- University of Nottingham has control of anything that ends in nottingham.ac.uk
- There's also a national organisations for ac.uk (academic uk) and .uk (uk in general)
- Non-profit Organisation delegates portions of their namespace. The people delegated a namespace can chop it up and delegate it further.
#### DNS Name Servers
![[Pasted image 20230224113151.png]]
- There's a standard interface for dealing with DNS queries and responses
- A zone is an administrative subdomain of DNS
#### DNS name servers example
![[Pasted image 20230224113322.png]]
- There are lots of root servers around the world which at minimum knows which servers it can go to in the top level domain.
#### Name resolution
![[Pasted image 20230224113342.png]]
- A query is built and is sent to pre-configured server it knows about
- May need to keep going through servers till it finds one which knows the domain name we're looking for
#### Cacheing
![[Pasted image 20230224113352.png]]
- Without cacheing, we'd be doing the whole process every time we look up a server
- DNS cacheing let's us reduce the load by cacheing information to help with communication
### DNS Summary
![[Pasted image 20230224113424.png]]
#### Other notes
![[Pasted image 20230224113432.png]]
- Not dissimilar to an unencoded UDP service
#### More complications with DNS
![[Pasted image 20230224113457.png]]
- Sometimes we use DNS as a control channel for malicious content
#### Summary
![[Pasted image 20230224113512.png]]
