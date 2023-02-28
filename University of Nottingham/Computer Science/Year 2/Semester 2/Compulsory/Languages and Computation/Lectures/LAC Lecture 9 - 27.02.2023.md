Contents:
[[Languages and Computation]]

#### How do we show that a language is not regular?
$\Sigma$ = {$0,1$}
L = {$w | h0(w) = h1(w)$}
		No. 0's     No. 1's
0101 $\in$ L
0111 $\notin$ L
001011 $\in$ L
The number of 1's and 0's should be the same
- This language is not regular because this language is not finite
	- It has no DFA, NFA or regex representation
	- Proof
		- Assume that there is a DFA for this language
		- Let m = |Q| (cardinality of the set of states)
		- Consider word w from L
			- Because the word is at least as long as the number of states (i.e. |w| >= n)
			- If w is xyz, then xyz is in the language L
			- And this means xz is also in the language L, and xyyz and xyyyz etc.

#### The Pumping Lemma:
Given L $\subseteq \Sigma*$ is a regular language then
$\exists n : \mathbb{N}, \forall w \in L, |w| >= n,$
$\exists x, y, z \in \Sigma*, w = xyz$ $\land$
$y \neq \epsilon$ $\land$
|xy| <= n $\land$
$\forall i : \mathbb{N}, x y z \in L$

#### Assume L is Regular. Use the Pumping Lemma
- Let n be the pumping #
- Let w = $0^n 1^n |w| >= n$ 
- we know that w = xyz
- w = 0 
-
#### Paying attention again
L = {$1^{n^2} | n : \mathbb{N}$}