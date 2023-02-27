Contents:
[[Algorithms, Correctness & Efficiency]]
![[Pasted image 20230223100303.png]]

1.
	Prove that $n^3 + 2n^2 log n$ is $O(n^3)$ using the multiplication and drop-smaller terms rules
	f(n) = $n^3 + 2n^2 log n$
	g(n) = $n^3$
	let's factor out $n^3$
	$n^3 + 2n^2 log n = (n^3) * (1 + \frac{2logn}{n})$
	As n -> inf, $\frac{logn}{n} \implies 0$ 
	
	($n^3$) * (1)
	O(n^3) * O(1) = O($n^3$)
	= $n^3(1)$ 
	= $n^3$ 

2.
	Big omega recap
	$f(n) >= c . g(n), \forall n >= n_0$ 
	
	Big theta recap
	$f(n) <= c' . g(n)$, 
	$f(n) >= c'' . g(n)$,
	$\forall n >= n_0$.

3.
	Prove 5 is $\Omega(1)$ and hence that 5 is $\Theta(1)$
	We know already that 5 is O(1) so if we can show that 5 is $\Omega(1)$ then we know that 5 is $\Theta(1)$ 
	Pick c, n0 s.t. $5 >= c . 1, \forall n >= n_0$   
	c = 5, n0 = 1
	We can say c' = 5 and n0 = 1, and it's fairly easy to say that c'' is also 5
5 is $\Omega(1)$ and 5 is $\Theta(1)$ 
5 >= c(1)
5 >= c
5 >= 1
trivially true that n0 = 1
c'' = 1, n0 = 1
5 <= c
c' = 5
c' = 5, c'' = 1, $n_0$ = 1 (trivially true)


4.
	Prove that 4 is $\Omega(2)$ and hence that 4 is $\Theta(2)$
	Pick c'', n0 s.t. 4 >= c . 2 $\forall n >= n_0$
	c'' = 1, n0 = 1
	Pick c', s.t. 4 <= c . 2 $\forall n >= 1$
	c' = 2, n0 = 1
	n0 = 1, c' = 2, c'' = 1
	4 <= 4, 4 >= 2, $\forall n >= 1$ 
	Hence, 4 is $\Theta(2)$

![[Pasted image 20230220101208.png]]

4 is $\Omega(2)$ and hence 4 is $\Theta(2)$
4 >= c(2)
c'' = 1, n0 = 1 (trivially true)
4 is $O(2)$
4 <= c(2)
c' = 2, n0 = 1 (trivially true)
c' = 2, c'' = 1, n0 = 1

5.
	Prove that 2n + 1 is $\Omega(3n)$
	Pick c, n0 s.t. 2n+1 >= c . 3n, forall n > n0
	Pick 1/3, n0 s.t. 2n+1 >= n forall n > n0
	c = 1/3, n0 = 1
	1 >= 1/3
	2n+1 is $\Omega(3n)$

6.
	Prove that 2n + 1 is $\Omega(n)$ and hence that 2n + 1 is $\Theta(n)$
	Pick c'', n0 s.t. 2n + 1 >= c . n forall n > n0
	Pick 1, n0 s.t. 2n + 1 >= n  forall n > n0
	c'' = 1, n0 = 1: 3 >= 3
	2n + 1 is $\Omega(n)$
	Pick c' s.t. 2n + 1 <= c . n forall n > 1
	Pick c' s.t. 2 + $\frac{1}{n}$ <= c  forall n > 1 (divide by n)
	$\frac{1}{n}$ will never exceed 1, hence:
	c' = 3: 3 <= 3
	c' = 3, c'' = 1, n0 = 1
	2n + 1 is $\Theta(n)$

Recap:
	Given f(n) and g(n) is o(g(n)) iff for all positive real constant c > 0 there exists $n_0$ such that:
	f(n) < c . g(n), $\forall n >= n_0$
	$\frac{f(n)}{g(n)} \implies 0$ as $n \implies \inf.$ 

7.
 Prove or disprove that 5 is o(1)
 5 < c
 all c > 0
 5 < 3
8.
	Prove or disprove that 5 is o(n)
	5 < n(c), forall n >= $n_0$, c > 0
	We can have n0 be dependent on c
	c = 1, $n_0$ = $\frac{5}{c} + 1$
	5 <= c($\frac{5}{c} + 1 + x)$ will hold for all values of c greater than 0, 
	as 5 <= $5 + c + cx$, where c and x are both > 0   
	hence:
	5 is o(n) is proved
