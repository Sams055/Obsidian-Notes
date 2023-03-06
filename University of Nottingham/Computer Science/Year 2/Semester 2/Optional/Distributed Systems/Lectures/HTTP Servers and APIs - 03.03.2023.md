Contents:
[[Distributed Systems]]

#### HTTP recap
![[Pasted image 20230303120132.png]]

![[Pasted image 20230303120141.png]]

#### HTTP Servers
##### HTTP servers
![[Pasted image 20230303120152.png]]
- Servers are usually gonna run on those ports, though they don't have to
- You'll usually have 1 process handling all incoming and outgoing HTTP
##### HTTP server configuration
![[Pasted image 20230303120220.png]]
- The configuration will say how to handle errors etc.
##### Routing Requests
![[Pasted image 20230303120317.png]]
- The URL will be passed through the host header
- Separate set up according to what the actual host name was, called a virtual host
- Servers may be configured to deal with file extensions as well
##### Handling Requests: common options
![[Pasted image 20230303120449.png]]
- A static file server has rules for URL - filename conversion, sends you back the correct info
- CGI Server configured so URL's cause programs to be executed, with program output being returned back to you
- The first web server you hit, could be a reverse proxy which has hidden servers to pass your request to.
- You can also just make your own webserver which does whatever you want
##### A few notes on scaling up
![[Pasted image 20230303122524.png]]
- If you get enough requests at once, regardless of how beefy a machine is, it will eventually run out of capacity/capability
- As seen in DNS we can have multiple
##### HTTP Server Summary
![[Pasted image 20230303120511.png]]

#### HTTP APIs
##### HTTP from a browser with traditional server-side scripting
![[Pasted image 20230303120527.png]]
- The browser knows it needs to make a new http request and package up the values in a standard manner and post it in a request
- Browser receives a response and displays it to you
##### HTML form-style
![[Pasted image 20230303120543.png]]

##### HTTP Application Programming Interfaces (API)
![[Pasted image 20230303120553.png]]
- We know what the basic parts are
##### Example
![[Pasted image 20230303120559.png]]

##### Defining HTTP APIs
![[Pasted image 20230303120608.png]]
- We just need to specify what our HTTP request/responses are, and we can usually use it for any language we like
##### Types of HTTP API
![[Pasted image 20230303120620.png]]
- Virtually every firewall let's http requests through
	- If you want something that'll work everywhere, use http
##### HTML Form- or Query-style operations
![[Pasted image 20230303120629.png]]
- Whenever you want the server to change as a result of something, we'd post to it.
- With a normal form, we have a standard way of encoding our parameters
##### Example
![[Pasted image 20230303120638.png]]

##### REST - Representational State Transfer
![[Pasted image 20230303120644.png]]
- Could have a database where every record is given a URL
##### REST-style
![[Pasted image 20230303120653.png]]

##### Remote Procedure Call (RPC)
![[Pasted image 20230303120659.png]]
- Represent the exception in the return body which the recipient can reconstruct to determmine what kind of exception they received
##### RPC-style
![[Pasted image 20230303120709.png]]

##### HTTPS APIs Summary
![[Pasted image 20230303120719.png]]

