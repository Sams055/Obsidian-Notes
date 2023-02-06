Contents:
[[Languages and Computation]]

###### Deterministic Finite Automata:
- 1st example: binary number $\Sigma =$ {$0,1$}
	- states
	- ![[Pasted image 20230206152405.png]]
	- lets say a q surrounded like this (q) is a final state
	- In this example we have decide that q3 is out final state, hence it will be indicated as such (q3)
	-          | 0,1 |         | 1 |       | 0  |       | 0, 1|     | 0, 1| 
	- | (q3) | <- | (q3) | <- | q0 | -> | q1 | -> | q2 | -> | q2 |
	-  001 would travel from q0 -> q1 -> q2 -> q2
		- However q2 is not the final state, hence we are in an impossible position, therefore 001 is not in the language
	- 110 would travel from q0 -> (q3) -> (q3) -> (q3)
		- q3 is the final state as indicated by the circling (), hence w
		- 
		- 
		- 
		- 
		- 
		- 
		- 
		- 
		- e are have achieved our goal state and 110 is in the language
	- Summary
		- we start at state `Q0` if we see a `0`, i.e. leading zero, we move to `Q1` 
		- if we see a `1`, we move to `Q2` from `Q1` 
		- we will always move to `Q3` regardless of whether we see a `0` or `1` 
		- `Q3` will also always move to `Q3`, it is the error state (we've parsed leading zeros, which is invalid, so the rest of the binary num will also be invalid)
		- from `Q2` we always move back to `Q2` again this is the "happy" state


- DFA A is given by
	- a finite set of states Q
	- An alphabet $\Sigma$ (finite set)
	- a transition function
		- $\delta \implies Q *\Sigma \implies Q$ 
		- $Q \implies \Sigma \implies Q$ 
	- An initial state $q_s : Q$
	- a set of final states $F \subseteq Q$
	- $F : Q \implies Prop$
	- A = (Q, $\Sigma$, $\delta$, q , F)
	data Q = Q0 | Q1 | Q2 | Q3 
	data Σ = 0 | 1 
	δ :: Q -> Σ -> Q 
	δ Q0 0 = Q1 
	δ Q0 1 = Q2 
	δ Q1 _ = Q3 
	δ Q2 _ = Q2 
	δ Q3 _ = Q3

- Language of a DFA A, L(A) $\subseteq \Sigma$*
	- L(A) : $\Sigma$* $\implies$ Prop
	- Extended transition function
	- $\hat{\delta} : Q$ x $\Sigma* \implies Q$ 
	- $\hat{\delta}(q, \epsilon) = q$ 
	- $\hat{\delta}(q, xw) = \hat{\delta}(\delta(q,x),w)$ 
	- L(A) = { $w = \Sigma* | \hat{\delta}(q_0,w)\in F$}
	- L(A)w = $F(\hat{\delta}(q_0,w))$
- Example: binary sequences divisible by 3, $\Sigma =${$0,1$}
- 0 o
- 1 x
- 11 o
- 111 x
- 1111 x