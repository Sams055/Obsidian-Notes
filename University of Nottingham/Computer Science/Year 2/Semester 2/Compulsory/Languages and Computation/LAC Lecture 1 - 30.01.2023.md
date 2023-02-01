Contents
[[Algorithms, Correctness & Efficiency]]

### Admin
#### Creating Code Blocks
``` C
int x = 7;
```

#### General Module info
	- Exam only
	- Do exercises and check the solutions
		- Tutors will be able to give you feedback on your attempts
	- You need to sign up to tutorials
	- Use moodle discussion group to ask questions
		- You can also answer other students questions on here as well
	- The main reference text for the module are the lecture notes available on moodle
	- There is a book available on moodle
		- Introduction to automata theory, languages, and computation


- Good revision is to formalise the work in Lean
- Summer work opportunity for this with Thorsten
#### Lecture Note Coverage
- Do not cover:
	- 1.3
	- 1.4



### LAC
###### Languages
	- Regular languages
		- Can be recognised by a computer with a finite amount of memory
###### Automata
	- Deterministic Finite Automata (DFA)
	- Non-Deterministic Finite Automata (NFA)
###### Grammars / Regular Expressions
	- Declarative Languages
		- Regular Expressions
###### Language Hierarchy
	![[Pasted image 20230130151925.png]]
	Type 3 / Regular languages
		- Finite Automata
	Type 2 / Context Free languages
		- Pushdown Automata
		- LIFO (stack)
		- Recursion
	Type 1 / Context Sensitive languages
###### Table
| Type | Languages | Automata | Grammars |
| ------------ | ----------- | ----------- | ----------- |
| Type 3 | Regular | Finite DFA & NFA | Regular Expressions |
| Type 2 | Context-Free | Pushdown Automata PDA | Context-Free Grammar |
| Type 1 | Context-Sensitive | Turing Machines | Grammar X |
| Type 0 | Recursively Decideable | | |

###### Halting-Problem (Undecidability of the...)
``` C
int halts (char * code, char * args) ...
	/* Returns n, if code is a C-program, def. a function with a (char *) arg, for which if I apply for arg it will terminate without error. */
	/* Returns 0, otherwise */
	void weird (char * code) {
		if halts (code, code)
			while (n);
		else
			return;
		} 
	}
	// There are some programs that you can't prove that terminate correctly
```
$$ weird(w - str) \neg (\exists halts) $$
$$ \neg (H \iff \neg H) $$
- If exists halts, then False
- Propositional formular is a tautology
- Predicate logic with type-vars and propositional variables
- Predicate logic without type-vars - only bools
- Only natural numbers
