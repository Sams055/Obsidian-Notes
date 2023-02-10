Contents:
[[Distributed Systems]]

#### Security Models and (Network) Threats
###### Security Model
![[Pasted image 20230208154536.png]]
- Securing the system means we need to secure the processes, communication channels and our resources e.g. objects
###### Protecting objects
![[Pasted image 20230208154551.png]]
- e.g. we might have an email client trying to get my emails from a server somewhere else
![[Pasted image 20230208154614.png]]
- who is allowed to do what?(in principle)
- Following the e-mail example
	- Only i should have access to my emails and only you should have access to your emails
![[Pasted image 20230208154623.png]]
- The server is part of the process of achieving security
- It checks whether particular operations are allowed
- It checks that a request has indeed come from the right person
- The client needs to make sure it's communicating to the correct server
	- e.g. you don't want to enter your bank details on the wrong website
- 
###### Securing processes and communication
![[Pasted image 20230208154732.png]]

###### Network threat model
![[Pasted image 20230208154755.png]]
- We should start by thinking about what the current risks are.
- In terms of network security, we think of a malicious party which we need to build our security to combat for.
- The malicious party could intercept and modify the messages we send
#### Network exploits & attacks
###### Criminal Exploits and Attacks
![[Pasted image 20230208154819.png]]
- In some simple protocols, we have a password login; if someone can intercept our sent password, they may be able to use it later maliciously
![[Pasted image 20230208154834.png]]
- This is a man-in-the-middle attack, where an interaction can be modified maliciously
![[Pasted image 20230208154841.png]]
- e.g. google.com being impersonated by go0gle.com
- Alternatively, the name could be correct, but the IP itself is a bogus IP address
![[Pasted image 20230208154848.png]]

![[Pasted image 20230208154855.png]]
- There are many more examples
- Ransomware is a very dangerous example which is seen quite often in modern malware
#### Encryption and VPNs
###### Encryption: a Fundamental Security Technique
![[Pasted image 20230208154916.png]]
- Cryptography can give us confidentiality to the extent that the strength of the cryptography enables us to have.
- We tend to use random sequences of numbers to encrypt and decrypt bits.
- But this is almost never absolute; so we just make the strongest encryption we can.
###### Private-key (symmetric) encryption
![[Pasted image 20230208154947.png]]
- The romans had this
- It uses a cunning algorithm, such that even a single change in bits will scramble the message into something completely different.
###### Public-key (asymmetric encryption)
![[Pasted image 20230208155013.png]]
- Only someone with a matching private key can decrypt a message encrypted by a public key.
- Hence, private keys don't need to be shared and only one needs to exist.
###### About Keys
![[Pasted image 20230208155022.png]]
- In symmetric encryption, both ends need the same key, but in order to share the keys, you risk someone else gaining access to the key.
- In Asymmetric encryption, we don't know if the public key we retrieve isn't a bogus public key a middle man has given us to get us to encrypt it into something they can decrypt.
- We use certification agencies to remedy this.
- When you install a web browser, it comes with certificates which are statements that the public key sent to you is definitely legitimate.
- You can send the public key to a certification agency to a certification agency which will sign the message to show that the public key can be trusted
###### Private Networks
![[Pasted image 20230208155037.png]]
- 
###### Virtual Private Networks
![[Pasted image 20230208155053.png]]


###### Personal VPN
![[Pasted image 20230208155104.png]]

#### Firewalls and NAT
###### Routers
![[Pasted image 20230208155122.png]]

###### Firewalls
![[Pasted image 20230208155133.png]]

![[Pasted image 20230208155139.png]]

###### Firewall Implementation with a Packet Filter
![[Pasted image 20230208155148.png]]

###### Network Address Translation (NAT)
![[Pasted image 20230208155200.png]]

![[Pasted image 20230208155207.png]]


