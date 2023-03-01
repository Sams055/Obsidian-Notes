Contents:
[[Algorithms, Correctness & Efficiency]]
![[Pasted image 20230223100303.png]]
### Attempt 1
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

### Attempt 2
##### 1.
$n^3 + 2n^2$ = $n^3(1 + \frac{2}{n})$
as n -> inf : $\frac{2}{n}$ -> 0 we drop this. (drop smaller terms rule)
= $n^3(1)$ = $O(n^3) * O(1)$ = O($n^3$) (multiplication rule)

##### 2.
$n^3 + 2n^2logn$ = $n^3(1+\frac{2logn}{n})$
as n -> inf : $\frac{2logn}{n}$ -> 0 we drop this. (drop smaller terms)
$n^3(1)$ = $O(n^3)*O(1)$ = $O(n^3)$ (multiplication rule)

##### 3.
prove 5 is $\Omega(1)$, 
Pick n0, c s.t. 5 >= c(1) forall n >= n0
c = 1, n0 = 1 (trivially)
5 >= 1: This holds
and hence 5 is $\Theta(1)$,
c'' = 1, n0 = 1
Pick 1, c' s.t. 5 <= c(1) forall n >= 1
c' = 5
5 <= 5: This holds
c' = 5, c'' = 1, $n_0$ = 1
5 >= 1, 5 <= 5, forall n >= 1
This holds; hence, 5 is $\Theta(1)$

##### 6.
Prove 2n+1 is $\Omega(n)$
Pick c, n0 s.t. 2n+1 >= c(n) forall n >= n0
c = 1
2n + 1 >= n
n0 = 1
3 >= 1
This holds, hence 2n+1 is $\Omega(n)$.
And hence prove that 2n+1 is $\Theta(n)$
c'' = 1, n0 = 1
Pick c', 1 s.t. 3 <= c(1) forall n >= 1
c' = 3
3 <= 3
c' = 3, c'' = 1, $n_0$ = 3
3 <= 3, 3 >= 1, forall n >= 1
This holds, hence 2n+1 is $\Theta(n)$

##### 7.
Prove or disprove that 5 is o(1)
Pick c, n0 s.t. 5 < c(1), forall n >= n0, c > 0
c = 1
5 < 1 
c <= 5 does not hold regardless of our value of n, hence this is disproved.

#### 8.
Prove or disprove that 5 is o(n)
Pick n0 s.t. 5 < c(n) forall n >= n0, c > 0
$\frac{5}{c}$ < n (divide by c)
We need anything above $\frac{5}{c}$ so we can just say:
n0 > $ceiling(\frac{5}{c}) + 1$ 


#### 9.
Prove $n^2$ is $\Omega(2n^2)$
Pick c, $n_0$ s.t. $n^2 >= c*2n^2$, forall n >= $n_0$
c = $\frac{1}{2}$
$n^2 >= n^2$
$n_0$ = 1
1 >= 1
This holds, hence: $n^2$ is $\Omega(2n^2)$
#### 10.
Prove $n^2 - 3$ is $\Omega(n^2)$
Pick c, $n_0$ s.t. $n^2 - 3 >= c(n^2)$, forall n >= $n_0$
c = $\frac{1}{4}$ 
$n^2 - 3 >= \frac{n^2}{4}$
$n_0$ = 2
1 >= 1
This holds, hence $n^2 - 3$ is $\Omega(n^2)$

#### 11.
Prove $n^2 - 5n$ is $\Omega(n^2)$
Pick c, $n_0$ s.t. $n^2 - 5n >= c(n^2)$, forall n >= $n_0$
$n_0$ = 10
$50 >= c*100$ 
c = $\frac{1}{2}$ 
50 >= 50
This holds, hence $n^2 - 5n$ is $\Omega(n^2)$
And hence, Prove $n^2 - 5n$ is $\Theta(n^2)$
c' = ? c'' = $\frac{1}{2}$ $n_0 = 10$ 
Pick c', 10 s.t. 50 <= 100c, forall n >= $n_0$
c' = 10 c'' = $\frac{1}{2}$ $n_0 = 10$ 
50 >= 50, 50 <= 50, forall n >= 10
This holds, hence $n^2 - 5n$ is $\Theta(n^2)$


#### 12.
Prove $n^2 + 1$ is $\Omega(n^2)$
Pick c, $n_0$ s.t. $n^2 + 1 >= c(n^2)$, forall n >= $n_0$
c = 1
2 >= c
$n_0$ = 1 
2 >= 1
This holds, hence $n^2 + 1$ is $\Omega(n^2)$

#### 13.
Prove or disprove that 1 is $\Omega(n)$
Pick c, $n_0$ s.t. $1 >= c*n$, forall n >= $n_0$
c = 1, n0 = 1
1 >= 1
This holds, hence, 1 is $\Omega(n)$


#### 14.
Prove or disprove that n is $\Omega(1)$
Pick c, $n_0$ s.t. $n >= c$, forall n >= $n_0$
c = 1, n0 = 1
1 >= 1
This holds, hence, n is $\Omega(1)$

#### 15.
Prove or disprove that $n^2$ is $\Omega(n)$
Pick c, n0 s.t. $n^2 >= c(n)$, forall n >= n0
c = 1, n0 = 1
1 >= 1
This holds, hence $n^2$ is $\Omega(n)$

