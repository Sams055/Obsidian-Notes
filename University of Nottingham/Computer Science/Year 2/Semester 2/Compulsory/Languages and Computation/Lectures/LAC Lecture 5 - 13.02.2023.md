Contents:
[[Languages and Computation]]

###### DFA & NFA Diagrammatic
| | DFA | NFA| Math DFA | MATH NFA |
|---|---|---|---|---|---|
|states|Has states|Has states|Q, a finite set| Q, a finite set|
|initial state| 1 initial state | can have several initial states| $q_0:Q$ | $S : Q \implies Prop = bool$ |  
|transitions|exactly 1 transition for each symbol|Can be several or 0 transitions for each symbol| $S : Q \implies \Sigma \implies Q$ | $S:Q \implies \Sigma \implies Q \implies Prop = bool$ |
|final state| Has any number of final states | Has any number of final states | $F : Q \implies Prop = bool$ | $F : Q \implies Prop = bool$ | 
|run|One token|Has multiple tokens| $\hat{S} : Q \implies \Sigma* \implies Q$ | $\hat{S}:Q \implies \Sigma* \implies Q \implies Prop$| 
|language|The token needs to end in a final state| At least one token needs to end in a finals state| $L_A w = F(\hat{S},q_0,w)$ | $L_A w=\exists q_s, q_e:Q, Sq_s \land Fq_E \land \hat{S}q_s w q_E$ |



