Contents:
[[Languages and Computation]]

- Language
	- L1 - Binary sequences representing binary numbers
		- No leading 0's
			- 101 - In the language
			- 001 - Not in the language
	- L2 - Binary sequences representing prime numbers
		- 11 - In the language
		- 110 - Not in the language
	- L3 - Sequences of a,b with the same number of 'a's and 'b's
		- abab is in the language
		- abbb is not in the language
		- ab is in the language
		- abb is not in the language
	- L4 - Sequences of a,b with the same number of 'a's 'b's modulo 2
		- Both of these numbers are even or both of these numbers are odd
		- In the language
			- abab, ab, abbb
		- Not in the language
			- abb (odd number of 'a's and even number of 'b's)
	- L5 - Sequences of '(' , ')' brackets match
		- In the language
			- (()(()))
		- Not in the language
			- (()))(
	- L6 - Sequences of characters representing valid C programs
	- L7 - Sequences of characters of the form code, arg. Where code is a valid C program which defines a funtion f s.t. f("arg") terminates
	- L8 - Sequences over a,b,c which are in the set {ab, ac, abc}
		- only 3 words in this language; finite language

	- L9 Sequences of characters with only 'bob'


- What is a language?
	- A language is a set of words.
		- Predicate over words.
		- What is a word?
			 A sequence of symbols
			 What is a symbol?
				 An element of an alphabet
				 What is an alphabet?
					 A finite set (or type)
- Sigma Notation
	- $$ \Sigma (sigma) $$
	- $$ \Sigma n = {a,b,c}  $$
- Example
	- ![[Pasted image 20230202112758.png]]

- Operations on Languages
	- ![[Pasted image 20230202114432.png]]
	- ![[Pasted image 20230202115203.png]]
	- 