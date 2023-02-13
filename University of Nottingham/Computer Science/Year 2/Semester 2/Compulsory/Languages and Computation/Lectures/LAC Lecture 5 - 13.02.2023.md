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

###### Theorem 1:
For every DFA A there is a NFA NA that accepts the same language
LA = L (NA)
NA(Q, $\Sigma$, $\delta_N$, $S$, $F$)
$S_N$ q x q'= ($\delta$ $qx = q'$ ) 
S $q$ = ($q$ = $q_0$) 

###### Theorem 2:
For every NFA A = (Q, $\Sigma$, $\delta$, S, F)
There is a DFA DA that recognizes the same language.
LA = L(D(A))
###### Truth Table and FSM
$P, Q = Q \implies Prop$
$N^Q \implies bool$ 
|PQ = {}| $q_0$ | $q_1$ | $q_2$ |
|---|---|---|---|
|{}|F|F|F|
|{$q_2$},|F|F|T|
|{$q_1$},|F|T|F|
|{$q_1,q_2$},|F|T|T|
|{$q_0$},|T|F|F|
|{$q_0,q_2$},|T|F|T|
|{$q_0,q_1$},|T|T|F|
|{$q_0,q_1,q_2$},|T|T|T|
![[Pasted image 20230213154231.png]]
![[Pasted image 20230213154538.png]]
We do not include the second fsm as that it never starts
###### Theorem 2 (continued)
For every NFA A = (Q, $\Sigma$, $\delta$, S, F) there is a DFA $DA = (PQ,\Sigma, \delta_D, S, F_D)$, that recognises the same language.
$LA = L(D(A))$

$\delta_D : PQ \implies \Sigma \implies PQ$
$(Q \implies Prop) \implies Sigma \implies Q \implies Prop$
$\delta$ P x q = $\exists q':Q, Pq' \land$ S q x q'




