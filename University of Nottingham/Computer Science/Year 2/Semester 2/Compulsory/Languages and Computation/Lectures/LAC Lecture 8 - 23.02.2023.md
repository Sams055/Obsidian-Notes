Contents:
[[Languages and Computation]]

- A regular language is
	1. The language of a regular expression
	2. The language of a NFA
	3. The language of a DFA
	- They are all the same as they can be expressed as each other to an extent
- Let's show how an RE can be represented with an automaton
	![[Pasted image 20230223111221.png]]
	- Div 3 $\Sigma =${$0,1$}
		![[Pasted image 20230223111435.png]]
		- The transitions are regular expressions
	- Eliminate q1
		![[Pasted image 20230223112122.png]]
		- Simplify
		![[Pasted image 20230223112245.png]]
	- Eliminate q2
		![[Pasted image 20230223112611.png]]
		- Simplify
		![[Pasted image 20230223112640.png]]
	- Eliminate q0
		![[Pasted image 20230223112754.png]]
	- The end goal is one initial state and one final state, with no other transitions other than the single one between them.
- Overall
	1. Add a new initial + final state with $\epsilon$ transition to (from the old initial + final states)
	2. Eliminate all states and sum up transitions.
	3. End with this DFA
		![[Pasted image 20230223113535.png]]
###### Minimisation of DFAs
- If we have two states we cannot distinguish, we can merge them
- Corollary of Myhill - Nerode
	- Give 2 DFA with the same language, then their minimisations
	- Are the same (isomorphic)