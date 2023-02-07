Contents:
[[Languages and Computation]]


###### 2.1
Let the alphabet Σ = {3, 5, 7, 9}, and let the language L = {w | w ∈ Σ ∗ , 1 ≤ |w| ≤ 2}. (If w is a word, |w| denotes the length of that word. If X is a finite set, like an alphabet or finite language, |X| denotes the number of elements in that set, its cardinality.) Answer the following questions:

1. Describe L in plain English. 
	- The language of all words over the alphabet {3,5,7,9} of length at least one and at most two
2. Enumerate all the words in L. 
	- {{3},{5},{7},{9},
	- {33},{35},{37},{39}
	- {53},{55},{57},{59}
	- {73},{75},{77},{79}
	- {93},{95},{97},{99}
3. In general, for an arbitrary alphabet Σ1 and 0 ≤ m ≤ n, how many words are there in the language L1 = {w | w ∈ Σ ∗ 1 , m ≤ |w| ≤ n}? That is, write down an expression for |L1|.
	- $|\Sigma| = 2:$ {0,1}
	- n = m = 0
		- $\epsilon$ (1)
	- n = m = 1
		- 2
	- n = m = 2
		- 4
	- n = 2, m = 1
	- 2^2 + 2^1 = 6
		- {0,1,01,10, 00, 11} = 6
	- It is clear by this point that it functions as binary
	- We can expand beyond binary by simply apply the power to the number of 

	- $|L1| = \sum\limits_{i=m}^{n}|\Sigma_1|^i$  
4. How many words would there be in L1 if Σ1 = Σ, m = 3, and n = 7?
	- | Σ | = 4
	- 4^3 + 4^4 + 4^5 + 4^6 + 4^7
	- 21824

###### 2.2
Let the alphabet 
Σ = {a, b, c} and let 
L1 = {ϵ, b, ac} and 
L2 = {a, b, ca} 
be two languages over Σ. 
Enumerate the words in the following languages, showing your calculations in some detail:

1. L3 = L1 ∪ L2 
	- L3 = {$\epsilon, a, b, ac, ca$} 
2. L4 = L1{ϵ}(L2 ∩ L1)
	- L1{$\epsilon$} (L2 ∩ L1) == L1 (L2 ∩ L1) 
		- L2 ∩ L1 = {b}
	- L4 =  $L2$  ∩  $L1$  = {$\epsilon$b, bb, acb}
	- L4 = {b, bb, acb}
3. L5 = L3 $\emptyset$ L4
	- L3 $\emptyset$ L4 = $\emptyset$ L4
	- $\emptyset$ L4 = $\emptyset$ 
	- L5 = $\emptyset$ 
###### 2.3
Let the alphabet 
Σ = {a, b, c} and let 
L1 = {ϵ, b, bb} and 
L2 = {a, ab, abc} 
be two languages over Σ. 
Enumerate the words in the following languages, showing your calculations in some detail:

1. L3 = L1 ∩ L2 
	- L3 = $\emptyset$
2. L4 = (L2{ϵ}L1) ∩ Σ∗
	-  {L2 {$\epsilon$} L1}
		- {a$\epsilon$, ab$\epsilon$, abc$\epsilon$,
		-  ab abb, abcb,
		-  abb abbb, abcbb}
		- {a, ab, abb, abbb, abc, abcb, abcbb}
		- = {a, ab, abc, abb, abcb, abbb, abcbb}
	- Σ∗
		- {Anything which has a, b, c}
	-  {L2 {$\epsilon$} L1} ∩ Σ∗
		- {a, ab, abb, abbb, abc, abcb, abcbb}
	- L4 = {a, ab, abb, abbb, abc, abcb, abcbb}
3. L5 = L3∅ ∩ L4
	- L3∅  = ∅ 
	- ∅  ∩ L4 = $\emptyset$ 
	- L5 = $\emptyset$

###### 2.4
Let the alphabet 
Σ = {a, b, c}. 
Enumerate the words in 
L = {w | w ∈ {ϵ, a, b, bc} ∗ , |w| ≤ 3}
- 0, 1, 2, 3 length words
- {$\epsilon$, a, aa, ab, abc, aaa, aab, aba, abb,
-  b, ba, bb, bbc, bba, bbb, bab, baa
-  bc, bca, bcb}

