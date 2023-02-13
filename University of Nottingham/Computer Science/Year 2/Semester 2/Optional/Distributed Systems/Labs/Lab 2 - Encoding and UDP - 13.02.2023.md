Contents:
[[Distributed Systems]]

##### Marshalling
Q1.
- Yes, they all read back the same values, though with different formats for some of the encoding
Q2.
- There are 7 characters and 8 bytes, the quotation mark takes up two bytes as it's not in ASCII
Q3.
- Yes, given this is UDP, we would also want to send the length so the user knows how many bytes they need for the full message
Q4.
- Everything that goes in and out would be a string, which may require type conversion which is slower than simply retrieving the data as is. The other methods will allow for other types such as integers to be encoded more efficiently
Q5.
- It writes a UTF-encoded string (encoding as a 2-byte length (6) and then 6 bytes of UTF-8 encoded characters) and a Java (32 bit) integer (encoded as 4 bytes, big endian, 2s-complement encoding)
Q6.
- The same, I.e. a UTF-encoded string and then a 32 bit signed integer.
Q7.
- The receiver must know the next type to ask for, as the sender and receiver use the same fixed sequence of types.
- JSON and XML encodings allow almost any (tree-)structured value to be sent and decoded. Java class/object encoding allows instances of any class (available to the decoder) to be sent.
##### UDP Client/Server
###### UDP Server
Q8.
It open a DatagramSocket
This will use UDP
Q9.
Q10.
Q11.
###### UDP Client
Q12.
Q13.
Q14.
Q15.
Q16.
Q17.
Q18.
Q19.
Q20.
Q21.
##### TCP Client / Server
Q22.
Q23.
Q24.
