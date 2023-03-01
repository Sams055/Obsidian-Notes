Contents:
[[Distributed Systems]]

##### Intro
- The Web is an example of a distributed system
- It's for publishing and accessing resources
- Acts as a client server system
- By definition a client server system uses request-response protocols
- This is HTTP and is run over TCP

#### Example
- We manage sets of resources managed by parts of those URLS
#### Web Protocols
- There are lots of protocols
- The key building blocks are 
	- HTTP (transport)
	- URL (naming resources)
	- HTML (how do we represent documents)
- You put in a URL (formatting interpretation)
- Browser specifies the HTTP to set how we send a request and receive a response
- The server figures out how to deal with it
- The content follows the HTML standard.

#### URL syntax
The general form is 
`protocol://computer_name:port/document-name?parameters
- Protocol is the name of the protocol
- computer_name is the domain names
- port is the port number
- document_name is the name of the document
- parameters are optional parameters for the document

#### URL defaults
You can omit details e.g. the protocol http or port 80:
- e.g. www.cs.nott.ac.uk does not have http or port
If we have a URL which is relative to the current page URL it can also work with
- just the document name
	- details.html

#### What happens in the browser
- browser parses the URL
	- Protocol
	- Computer name
	- Port
	- document name
	- parameters
- Uses a protocol to decide which protocol to use, e.g. for HTTP
- Uses the the computer name and protocol port to form a TCP connection to the server on which the page resides
- Uses the computer name, document name and parameters to request a specific page form that server using HTTP
- Displays the content (or error) received from the server

#### Browser URLs and Navigation
Each tab in a browser is displaying the content retrieved form one URL
The URL can be changed by:
- Entering a new URL directly into the browser search bar
- pressing a hyperlink in a displayed web page
- Code running int he browser changing the URL (JavaScript)
But Note:
- Elements within the page (e.g. images) may have come from other URLs

#### Document Transfer
![[Pasted image 20230228112738.png]]

#### HTTP Request
![[Pasted image 20230228112716.png]]


#### HTTP Methods
![[Pasted image 20230228112759.png]]
#### HTTP Response
![[Pasted image 20230228112941.png]]
- The status code tells us how the operation went
- You don't have to have a response body, but it's usually good to do so

#### Raw Request
![[Pasted image 20230228113254.png]]

#### Raw Response
![[Pasted image 20230228113236.png]]
![[Pasted image 20230228113734.png]]
- This is the whole process

#### Discussion
![[Pasted image 20230228113755.png]]
- HTTP just says send these bytes, receive these bytes; doesn't care what's being done internally
- HTTPS uses sockets on top of HTTP to make it secure
#### HTTP Summary
![[Pasted image 20230228113845.png]]


#### HTML and Scripting
#### Client Side Scripting
![[Pasted image 20230228113946.png]]
- The browser has an engine to run JavaScript
#### Server-side scripting
![[Pasted image 20230228114101.png]]

#### Failure Handling
- We need to be able to cope with partial failure by doing things such as deploying multiple servers and retrying failed connections

#### Security
We use encryption and identity checking
#### Scalability
- a system if as it grows, it still works as well
