Contents:
[[Algorithms, Correctness & Efficiency]]

###### Removing Details
![[Pasted image 20230206091456.png]]
- We get different step counts depending on interpretation
- These steps don't represent runtime since runtime is determined by how the compiler etc. interprets the steps
###### Classification of Functions
![[Pasted image 20230206091510.png]]
- Think about big-Oh in terms of functions e.g. O(n)
- We use them to get rid of unnecessary details we don't care about
- Still needs to be precisely mathematically defined
	- Can be proved in lean
###### Advanced uses of Big-Oh
![[Pasted image 20230206091559.png]]
- As can be seen, there is no algorithm in sight, we just use big-oh to represent it.
###### Motivations for Big-Oh
![[Pasted image 20230206091621.png]]
- We can express the two functions by using their ratio
###### Important Comment
![[Pasted image 20230206091635.png]]

###### Ratio of two linear functions
![[Pasted image 20230206091646.png]]
- large values of n are easy to figure out, but small values are horrible to work with
![[Pasted image 20230206091657.png]]
- Bounding with 4/3 makes it much more predictable and we can make a very easy to understand inequality
![[Pasted image 20230206091708.png]]
- The bounds contain the easiest bit to read
![[Pasted image 20230206091719.png]]
- We place the bounds of one function relative to another
![[Pasted image 20230206091906.png]]
- We can replace the complex calculations with Big-Oh
###### Exercise: Computation
![[Pasted image 20230206091735.png]]

###### Big-Oh Notation Definition
![[Pasted image 20230206091750.png]]
- Say f(n) = 4/3 and g(n) = 8/3, O would represent 2
- O represents the ratio between the functions
![[Pasted image 20230206091824.png]]
- Let's apply the definition but swap the order of the quantifiers
- This can cause wrong answers; as we know from lean
- Make sure you get the order right!
![[Pasted image 20230206091836.png]]
- There is no way we can have 'c' depend on 'n'
- The definition is useless that way
![[Pasted image 20230206091844.png]]
- If we are dealing with infinite sets, we can use techniques such as induction (as seen in lean)
![[Pasted image 20230206091852.png]]

###### Which functions are used?
![[Pasted image 20230206091806.png]]
- We tend to assume it will be bigger than 0, eventually...
###### Exercise
![[Pasted image 20230206091920.png]]
- Let's start with the simplest function pssible
- exists c n0 s.t. 1 <= c 1 forall n >= n0
- e.g. c = 1 n0 = 1
- Done
- c = 539237327, n0 = 320483972
- Done
- ![[Pasted image 20230206123243.png]]

![[Pasted image 20230206092131.png]]

![[Pasted image 20230206092139.png]]

![[Pasted image 20230206092146.png]]
- Same thing
![[Pasted image 20230206092152.png]]
- What
![[Pasted image 20230206092158.png]]

![[Pasted image 20230206092205.png]]

![[Pasted image 20230206092212.png]]

![[Pasted image 20230206092219.png]]

![[Pasted image 20230206092225.png]]

![[Pasted image 20230206092231.png]]

![[Pasted image 20230206092237.png]]

![[Pasted image 20230206092250.png]]

![[Pasted image 20230206092258.png]]

