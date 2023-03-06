Contents:
[[Languages and Computation]]

Why mochas are good

- Chomsky Type 3 = regular languages (REG)
	- DFA, NFA, RE
- Chomsky Type 2 = context-free languages (CFL)
	- Context-free grammars (CFG)
	- (later) Push-down Automata (PDA)

- 2 $*$ (x+3)
	- Expressions E
		- Terms (part of $+$) T
		- Factor (part of $*$) F

##### Expressions:
- An expression can be a term $E \implies T$
- An expression can be an expression + a term $E \implies E + T$
- A term can be a factor $T \implies F$
- A term can be a term $*$ a factor $T \implies T * F$ 
- A factor is just an *a* $F \implies a$ 
- A factor can just be an expression in brackets $F \implies (E)$
###### Short form
- $E \implies T$ | $E + T$
- $T \implies F$ | $T * F$ 
- $F \implies a$ | $(E)$



##### What
- What is a CFG?
- $\mathbb{N}$ a finite set of non-terminal symbols
- $\Sigma$ (or T) a finite set of symbols (or terminal symbols)
	- N $\cap$ $\Sigma = \emptyset$ 
	- $P \subseteq N$ x $(N \uplus \Sigma)*$ 
	- fin
	- S : N the start symbol
