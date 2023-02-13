Contents:
[[Algorithms, Correctness & Efficiency]]

##### Rules for Finding big-Oh
- Slide
	- ![[Pasted image 20230213111617.png]]
	- 
###### Multiplication Rule for big-Oh
![[Pasted image 20230213111718.png]]

![[Pasted image 20230213111734.png]]

###### Drop smaller terms
![[Pasted image 20230213111751.png]]

###### Exercise
![[Pasted image 20230213111906.png]]

![[Pasted image 20230213111919.png]]


###### Big-Oh Rules
![[Pasted image 20230213111947.png]]

###### Seven Important Functions
![[Pasted image 20230213111959.png]]

###### Drop smallers terms (Cont'd)
![[Pasted image 20230213112008.png]]

##### Useful Limits
###### Exponents vs powers
- Slide
	- ![[Pasted image 20230213112033.png]]
	- Eventually, the exponential will reach infinity
- ###### Exercise
	- ![[Pasted image 20230213112046.png]]
	- Exponent law will usually be way big than power law
	- ![[Pasted image 20230213112110.png]]
	- Once again, exponents beat powers
###### Powers vs logs
- Slides
	- ![[Pasted image 20230213112150.png]]
	- Exponentials have more impact than powers which have more impact than logs.
	- May only be obvious with larger values of n
- ###### Exercise
	- ![[Pasted image 20230213112439.png]]
	- n^2 dominates the rest of it
	- ![[Pasted image 20230213112454.png]]
	- It's n^2
##### Offline Exercises 
![[Pasted image 20230213113110.png]]

##### Big-Oh Conventions
![[Pasted image 20230213113133.png]]
- We simply use the simplest expression of the greatest weight
##### Usage of 'O' in practice
![[Pasted image 20230213113147.png]]
- We want a good amount of information, but we don't want to go crazy trying to get the true worst / best case.
##### Algorithm or Problem
![[Pasted image 20230213113203.png]]
- We don't know exactly if we can modify an algorithm for a different big-Oh, so we generally just analyse them
##### Exercise
![[Pasted image 20230213113217.png]]

![[Pasted image 20230213113236.png]]

##### Reminder of Big-Oh as a set
![[Pasted image 20230213113358.png]]

![[Pasted image 20230213113430.png]]

##### Usage for Algorithms
![[Pasted image 20230213113446.png]]
- Shouldn't always *only* consider the worst case
- But if nothing else is mentioned, the Big-Oh notation will usually by default refer to the worst case
![[Pasted image 20230213113501.png]]

![[Pasted image 20230213113525.png]]

##### Asymptotic Algorithm Analysis in Practice
![[Pasted image 20230213113704.png]]
