Contents:
[[Algorithms, Correctness & Efficiency]]

Things we need to know:
Primitive Operation Counting
- Lab
Big-Oh Family Calculations
- Tutorial
Linked Lists
- Lecture
Simple Sorting Methods
- Lecture



#### Big-Oh Family Calculations
Impact:
![[Pasted image 20230226144323.png]]
- You may have seen some questions that talk about dropping smaller terms etc.
- The above order of size will help with that
- <b>However</b>, You should not use techniques such as dropping smaller terms if the question has not asked us to...

Big-Oh
![[Pasted image 20230220100930.png]]
Any value of c
Any value of $n_0$

Syntax:
Pick c, $n_0$ s.t. f(n) <= c(g(n)), $\forall : n >= n_0$
c = ?, $n_0$ = ?

Copy the above formula, and then substitute in values for the "?" to finish the proof

Big-Omega
![[Pasted image 20230220101025.png]]
Any value of c
Any value of $n_0$
- The only difference is which way the inequality points

Big-Theta
![[Pasted image 20230220101208.png]]
- Big-Theta is basically:
	- Proving Big-Oh
	- Proving Big-Omega
	- Where n0 is the same for both
	- c' and c'' can be any values that work for this

Little-Oh
![[Pasted image 20230220101235.png]]
- it's 2 minutes till 3, will just wing this 

- i will wing the rest of this
