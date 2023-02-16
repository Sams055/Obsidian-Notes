Contents:
[[Languages and Computation]]

### Regular Expressions
Tools: grep, sed
specify lexical syntax
detonational is procedural
RE DFA, NFA

- Regexes specify lexical syntax
	- How constructs such as comments, identifiers, etc. are structured
- Denotational view
	- As opposed to procedural views (such as automata)
#### Definition:
Define Regular Expression $\Sigma$ and given $E: RE$ $\Sigma$, $L^{RE} E : \Sigma* \implies Prop$ 
###### Mathematical:
$L^{RE} \subseteq \Sigma*$ 
$\emptyset : RE$ $\Sigma$ 
$L \emptyset =$ { }
$L \emptyset = \lambda$ $wq$ $False$ 
$\epsilon  = RE$ $\Sigma$ 
$L$ $\epsilon$ = {$\epsilon$}
= $\lambda w$, $w = \epsilon$  

###### $a : \Sigma$
$a : RE$ $\Sigma$ 
La = {a} (= {[a]})
La = $\lambda w, w = [a]$ 

###### $E, F : RE$ $\Sigma$ 
$E + F : RE$ $\Sigma$
$L (E + F) = LE \cup LF$ 
$L (E + F) w = LE w \lor LF w$ 
###### $E, F : RE$ $\Sigma$
$E, F : RE$ $\Sigma$
$L(EF) = (LE)(LF)$
###### Inductive Type:
inductive $RE (\Sigma : Type)$ 
| $empty : RE$
| $epsilon : RE$
| $lit : \Sigma \implies RE$
| $union : RE \implies RE \implies RE$ 


##### Concatenation of languages:
$\Sigma =$ {$a,b,c$}
{$a,b,c$} {$a,bc$} = {$aba, abbc, concat, cbc} 
$L, M : \Sigma* \implies Prop$ 
###### $Lw \land Mv$
$(L M)(wv)$
$LM : \Sigma* \implies Prop$
$L$ $hello$ = {$hello$} 
$L (hello+hello) =$ {$hello, hello$}
$L(e+a) LLO$
\Sigma 
###### Maths
$E : RE \Sigma$ 
$E* : RE \Sigma$ 
$L E* = (LE)*$

$L \subseteq \Sigma*$ 
$L* \subseteq \Sigma*$

$\epsilon : L*$
$Lw \land L*$ 
$L* (wv)$




- For every $E : RE \Sigma$ we construct an NFA, $N^{RE} E : NFA \Sigma$ such that:
	- $L^{RE} E = L^{NFA} (N^{RE} E)$
	- $N^{RE} \emptyset =$ nothing
	- $N^{RE} \epsilon =$ entry state = accepting state
	- $N^RE a .. \Sigma$ = entry state ->(a) accepting state
- 