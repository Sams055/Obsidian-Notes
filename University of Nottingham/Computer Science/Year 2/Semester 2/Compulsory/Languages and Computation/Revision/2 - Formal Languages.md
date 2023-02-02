Contents:
[[Languages and Computation]]

- Definitions
	- A language is a set of words.
	- A word is a sequence of symbols.
- Let's build our notation
	- Let's represent an empty word with $\epsilon$
		- $\epsilon$ is a symbol sequence of length 0.
	- We now have definitions for a word, so let's talk about the symbols that make up a word.
	- What is a symbol?
		- Anything that comes from an alphabet.
	- Lets represent the alphabet with $\Sigma$ which represents a finite set.
		- A common and important instance of this is $\Sigma =$ {0, 1}.
		- NOTE: $\epsilon$ will *never* be a symbol
			- avoids confusion
	- Lets define $\Sigma$* as a 'set of words' where a 'set of words' can also be a 'sequence of symbols'
		- This is essentially making a set of the alphabet
- Notation summary
	- Empty Word = $\epsilon$
	- Alphabet = $\Sigma$
	- Alphabet Set = $\Sigma$*
	- Element of = $\in$ 
- Example of notation in action
	- Example
		- Mathematically we say: Given an alphabet Σ we define the set Σ ∗ as set of words (or sequences) over Σ: the empty word ϵ ∈ Σ ∗ and given a symbol x ∈ Σ and a word w ∈ Σ ∗ we can form a new word xw ∈ Σ ∗ .
		- Let's break it down: 
			- Given an alphabet Σ 
			- we define the set Σ ∗ 
				- as a set of words
			- over the alphabet Σ, where we have 
				- the empty word
					- ϵ ∈ Σ ∗ 
						- which is an element of the alphabet set
				- a given symbol 
					- x ∈ Σ 
						- Which is an element of the alphabet
				- a word 
					- w ∈ Σ ∗ 
						- Which is an element of the alphabet s
			- from which we can concatenate the 'given symbol' and 'word' to form a new word xw
				- xw ∈ Σ ∗ 
					- Which is also an element of the alphabet set