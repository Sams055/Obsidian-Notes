Contents:
[[Languages and Computation]]

More on regex
<b>The . represents an invisible operation</b>
What is a regular expression?
	- For example $\Sigma =${$a,b,c$}
	- Constants $\emptyset, \epsilon, x$ where $x$ is a member of $\Sigma$
	- Operations (binary) : E + F, E $.$ F, (EF)
	- Unary: E*
	- Bracket rules : + < $.$ < $*$
	- ab + c
		- ![[Pasted image 20230220151126.png]]
	- a(b+c)
		- ![[Pasted image 20230220151219.png]]
What laws do we know?
	- x + y = y + x
	- x . (y + z) = x . y + x . z
	- x + (y + z) = (x + y) + z
	- x . $\emptyset$ = $\emptyset$
What laws only work in regex?
	- x + x = x
What laws only work in arithmetic?
	- x . y = y . x
		- lets substitute a and b
		- a . b = b . a
		- ab : ba
		- {ab} $\neq$ {ba}
		- ab $\neq$ ba
		- Regular Expressions are not commutative
How does Kleene algebra work?
	- x$*$ = $\epsilon$ + x x$*$
	- Given E : RE $\Sigma$
	- we define L(E) $\subseteq \Sigma*$ 
	- $L(E) : \Sigma* \implies Prop$ 
	- L $\emptyset$ = $\emptyset$
	- L $\epsilon$ = {$\epsilon$}
	- L x = {x} ([x])
	- L (E + F) = LE $\cup$ LF (v)
	- L . (E . F) = . L(E) . L(F)
	- Example
		-  {ab, bc . d, ef}
			{abd, abef, bcd, bcef}
	- L (E$*$) = L(E)$*$
	- $\emptyset*$ = {$\epsilon$}
	- $\epsilon*$ = {$\epsilon$}
	- $\epsilon \epsilon = \epsilon$
The Bigger Picture
	- Given $L \subseteq \Sigma*$ TFAE
	1. L is the language of a DFA A
		$L = L^{DFA} A$ 
	2. L is the language of an NFA A
		$L = L^{NFA} A$ 
	3. L is the language of an RE E
		$L = L^{RE} E$ 

More on regular expressions
	- Given a RE E, we construct $N^{RE} E:NFA \Sigma$ 
	- s.t. $L^{RE}E = L^{NFA}(N^{RE} E)$ 
	- Diagram
		![[Pasted image 20230220153737.png]]
		![[Pasted image 20230220153844.png]]
		![[Pasted image 20230220153955.png]]
		![[Pasted image 20230220154324.png]]
		![[Pasted image 20230220154619.png]]
	N(a* b*)
		![[Pasted image 20230220154912.png]]
		![[Pasted image 20230220154954.png]]
		![[Pasted image 20230220155029.png]]
		![[Pasted image 20230220155113.png]]