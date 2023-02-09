Contents:
[[Languages and Computation]]

- DFA $\Sigma$ = {a,b}
###### DFA Example Machine
![[Pasted image 20230209110814.png]]
We enter
at EE
Q = {EE,EO,OE,OO}
S : $Q$ x $\Sigma \implies Q$ 

| | a | b |
|---|---|---|
|EE|OE|EO|
|EO|OO|EE|
|OE|EE|OO|
|OO|EO|OE|

$q_0$ = EE
F = {EE, OO}

We can simplify the automaton
![[Pasted image 20230209111327.png]]
We enter at 0
##### Nondeterministic Finite Automaton (NFA)
###### NFA Example
$\Sigma$  = {0,1} Symbol before last is 1
![[Pasted image 20230209111602.png]]
010 will end up in the final state via q0, q0, q1,q2
101 will end up as q0, q1, q2, qNull, not part of the final state
This is because the token in q2 has no where to go and hence, disappears

Why is the loop there?
- It allows us to conditionally recognise words beyond a length of 3


###### Bigger NFA Example
![[Pasted image 20230209112338.png]]
- We should think about this finite state machine in terms of tokens,
- Every time a token finishes in the final state, our word is valid

aaa - X
abc a - o
bba - x
abbb -o

###### Mathematical Notation for NFA
NFA = (Q, $\Sigma$, $\delta$, S, F)
Example:
- Q = {0,1,2,3,4,5}
- $\Sigma$ = {a,b,c}
	- Q and $\Sigma$ are finite sets
- S : Q x $\Sigma \implies PQ$ 
	- $Q  \implies \Sigma \implies Q \implies Prop$
	- S $\land$ b 3
	- S $\land$ b 4
	- S $\land$ b = {3,4}
- S $\subseteq$ Q (S : Q $\implies$ Prop)
| |a|b|c|
|---|---|---|---|
|0|{1}|{2}|{}
|1|{4}|{3,4}|{}
|2|{3,4}|{4}|{}
|3|{1}|{2}|{3}
|4|{}|{}|{5}
|5|{}|{}|{4}
S = {0,4}
F $\subseteq$ Q    (F : Q $\implies$ Prop)
F = {1,2,4}
###### Better NFA Example
$\hat{S}:Q \implies \Sigma* \implies Q \implies Prop$ 
$\hat{S} q \in q' = (q = q')$ 
$\hat{S}$ q xw q' = $\exists q'' : Q,$  S q x q' $\land$ $\hat{S}$

###### Language Interpretation
L(A) = $\subseteq \Sigma*$
L(A) w = $\exists$ $q_0,q_E$ : Q, S $q_0$ $\land$ F $q_E$ $\land$ $\hat{S}$ $q_0$ w $q_E$ 
