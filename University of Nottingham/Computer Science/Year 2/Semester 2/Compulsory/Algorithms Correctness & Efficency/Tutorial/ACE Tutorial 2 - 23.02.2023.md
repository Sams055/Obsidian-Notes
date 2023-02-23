Contents:
[[Algorithms, Correctness & Efficiency]]
![[Pasted image 20230223100303.png]]

1.
	Prove that $n^3 + 2n^2 log n$ is $O(n^3)$ using the multiplication and drop-smaller terms rules
	f(n) = $n^3 + 2n^2 log n$
	g(n) = $n^3$
	let's factor out $n^3$
	$n^3 + 2n^2 log n = n^3(1 + \frac{2logn}{n})$
	As n -> inf, $\frac{logn}{n} \implies 0$ 
	= $n^3(1)$ 
	= $n^3$ 

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

4.
	Prove that 4 is $\Omega(2)$ and hence that 4 is $\Theta(2)$
	Pick c'', n0 s.t. 4 >= c . 2 $\forall n >= n_0$
	c'' = 2, n0 = 1
	Pick c', s.t. 4 <= c . 2 $\forall n >= 1$
	c' = 2, n0 = 1
	n0 = 1, c' = 2, c'' = 2
	Hence, 4 is $\Theta(2)$

5.
	Prove that 2n + 1 is $\Omega(3n)$
	Pick c, n0 s.t. 2n+1 >= c . 3n, forall n > n0
	Pick c, n0 s.t. $\frac{2}{3}$ +$\frac{1}{3n}$ >= c, forall n > n0 (divide by 3n)
	$\frac{1}{3n}$ will never be greater than $\frac{1}{3}$, hence:
	c = 1, n0 = 1
	1 >= 1: 2n+1 is $\Omega(3n)$

6.
	Prove that 2n + 1 is $\Omega(n)$ and hence that 2n + 1 is $\Theta(n)$
	Pick c'', n0 s.t. 2n + 1 >= c . n forall n > n0
	Pick c'', n0 s.t. 2 + $\frac{1}{n}$ >= c  forall n > n0 (divide by n)
	$\frac{1}{n}$ will never exceed 1, hence:
	c'' = 3, n0 = 1: 3 >= 3
	2n + 1 is $\Omega(n)$
	Pick c' s.t. 2n + 1 <= c . n forall n > 1
	Pick c' s.t. 2 + $\frac{1}{n}$ <= c  forall n > 1 (divide by n)
	c' = 3: 3 <= 3
	c' = 3, c'' = 3, n0 = 1
	2n + 1 is $\Theta(n)$
	