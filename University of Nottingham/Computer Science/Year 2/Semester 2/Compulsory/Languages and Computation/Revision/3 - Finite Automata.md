Contents:
[[Languages and Computation]]

###### Deterministic Finite Automata (DFA)
- The main part of this section is the notation and finite state machines
- A deterministic finite automaton (DFA) A = (Q, Σ, δ, q0, F) is given by: 
1. A finite set of states Q 
2. A finite set of input symbols, the alphabet, Σ 
3. A transition function δ ∈ Q × Σ → Q 
4. An initial state q0 ∈ Q 
5. A set of final states F ⊆ Q 
- The initial states are sometimes called start states,
- The final states are sometimes called accepting states.
There's formal notation in the lecture notes document, however this may confuse you.
Let's think about how finite state machines work:
- We have a starting point
- And an ending point (usually indicated with an extra circle around the state)
- If our expression finishes in an ending point, it is a valid value in our set.
- If our expression finished anywhere else, it is not a valid value in our set.
- We now want to represent this with the formal notation:
$$δD = {((q0, 0), q1),((q0, 1), q0),((q1, 0), q1),((q1, 1), q2),((q2, 0), q2),((q2, 1), q2)}$$
This is extremely messy and you would not expect anyone to understand it for the first time, let's try make it more readable
	δD(q0, 0) = q1 
	δD(q0, 1) = q0 
	δD(q1, 0) = q1 
	δD(q1, 1) = q2 
	δD(q2, 0) = q2 
	δD(q2, 1) = q2

- The notation above can be interpreted as taking a function which takes in the current state and an arbitrary value from the set {0,1}
- The function then returns the new current state based on these parameters.
- But you may ask yourself, how do we tell what the start and accepting states are?
<b> Open page 13 of the LAC lecture notes and head to the bottom of the page</b>
	- The transition table functions essentially acts as a truth table for the finite state 'functions' (call them finite states for proper terminology) we used above.
	- The main difference you should pay attention to is 
	- the $=>$ arrow, 
	- and the $*$ star,
	- The arrow indicates that the current state is the start state
	- The star indicates that the current state is the accepting state.
	- We can a finite state which is both a start state and an accepting state as seen on the top transition table on page 14
From here, you'll want to take a look at the finite state machines on page 14, it very clearly shows the equivalent finite state machines for the table above.
	- Each subsequent section and page for DFA shows more examples with different inputs for other finite state machines
	- However, the fundamental concept is the same as what has been explained here in these revision notes and there shouldn't be anything particularly new to cover.
	- There may be tricky bits such as the recursive formula and language definitions; the only thing you need to do is to look at them, see how they are constructed, and try construct one yourself as practice
###### Non-Deterministic Finite Automata (NFA)
- 