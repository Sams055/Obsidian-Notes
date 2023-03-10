Contents:
[[Algorithms, Correctness & Efficiency]]


###### Q1. Prove 5 is O(1)
- f(n) = 5
- g(n) = 1

- Pick c, n0 s.t. 5 <= c(1) forall n >= n0
- Pick c, n0 s.t. 5 <= c forall n >= n0
- c=5, n0=1 (anything)

Pick c, $n_0$ s.t. 5 <= c(1) $\forall$ n >= $n_0$
5 <= c
c = 5, n0 = 1 (trivially true)
5 <= 5
###### Q2. Prove 4 is O(2)
- f(n) = 4
- g(n) = 2
- Pick c, n0 s.t. 4 <= c(2) forall n >= n0
- Pick c, n0 s.t. 2 <= c forall n >= n0 (divided by 2)
- c = 2, n0 = 1 (trivially true - means we could put anything for n0)

###### Q3. Prove 2n+1 is O(3n)
- f(n) = 2n+1
- g(n) = 3n
- Pick c, n0 s.t. 2n+1 <= c(3n) forall n >= n0
- Pick c, n0 s.t. 2+1/n <= c(3) forall n >= n0 (we divided by n)
- (Given n >= 1, (2 + 1/n) will never be greater than 3)
- c = 1, n0 = 1 (trivially true - means we could put anything for n0)

f(n) = 2n +  1
g(n) = 3n
Pick c, $n_0$ s.t. 2n+1 <= c(3n) forall n >= n0
2n+1 <= 3n
1 <= n (-2n from both sides)
1 <= 1
c = 1, n0 = 1,

###### Q4. Prove 2n+1 is O(n)
- f(n) = 2n+1
- g(n) = n
- Pick c, n0 s.t. 2n+1 <= c(n) forall n >= n0
- Pick c, n0 s.t. 2+1/n <= c forall n >= n0 (divided by n)
- c = 3, n0 = 1 (trivially true - means we could put anything for n0)

###### Q5. $n^2$ is $O(2n^2)$
- f(n) = $n^2$
- g(n) = $2n^2$
- Pick c, n0 s.t. $n^2$ <= c($2n^2$) forall n >= n0
- Pick c, n0 s.t. $1$ <= c($2$) forall n >= n0 (divided by $n^2$)
- Pick c, n0 s.t. $\frac{1}{2}$<= c forall n >= n0 (divided by $n^2$)
- c = 1, n0 = 1 (trivially true - means we could put anything for n0)

f(n) = $n^2$
g(n) = $2n^2$
Pick c, $n_0$ s.t. $n^2 <= c(2n^2)$ forall n >= n0
(divide by $n^2$) 1 <= 2c 
1 <= 2
c = 1, n0 = 1, (trivially true)
###### Q6. $n^2 - 3$ is $O(n^2)$
- f(n) = $n^2 - 3$
- g(n) = $n^2$
- Pick c, n0 s.t. $n^2 - 3$ <= c($n^2$) forall n >= n0
- Pick c, n0 s.t. $1 - \frac{3}{n^2}$ <= c forall n >= n0 (divided by $n^2$)
- c = 1, n0 = 1 

###### Q7. $n^2 - 5n$ is $O(n^2)$
- f(n) = $n^2 - 5n$ 
- g(n) = $n^2$
- Pick c, n0 s.t. $n^2 - 5n$ <= c($n^2$) forall n >= n0
- Pick c, n0 s.t. $1 - \frac{5}{n}$ <= c forall n >= n0 (divided by $n^2$)
- c = 1, n0 = 1 (trivially true - means we could put anything for n0)

###### Q8. $n^2 + 1$ is $O(n^2)$
- f(n) = $n^2 + 1$
- g(n) = $n^2$
- Pick c, n0 s.t. $n^2 + 1$ <= c($n^2$) forall n >= n0
- Pick c, n0 s.t. $1 + \frac{1}{n^2}$ <= c forall n >= n0 (divided by $n^2$)
- The highest $\frac{1}{n^2}$ can be is 1; hence, 2 <= c is the worst case
- c = 2, n0 = 1 (trivially true - means we could put anything for n0)

###### Q9. Prove or Disprove that 1 is $O(n)$
- f(n) = 1
- g(n) = n
- Pick c, n0 s.t. 1 <= c($n$) forall n >= n0 
- Pick c, n0 s.t. $\frac{1}{n}$ <= c forall n >= n0  (divided by n)
- $\frac{1}{n}$  can be no bigger than 1, hence:
- c = 1, n0 = 1 (trivially true - means we could put anything for n0)

###### Q10. Prove or disprove that $n$ is $O(1)$
- f(n) = n
- g(n) = 1
- Pick c, n0 s.t. $n$ <= c(1) forall n >= n0 
- Pick c, n0 s.t. $n$ <= c forall n >= n0 
- c = , n0 = ,
- We can't choose a value of c as it would have to be based on n, but we can't choose a value of n before choosing a value of c.
- This means it's unprovable

###### Q11. Prove or disprove that $n^2$ is $O(n)$
- f(n) = $n^2$
- g(n) = $n$
- Pick c, n0 s.t. $n^2$ <= c(n) forall n >= n0
- Pick c, n0 s.t. $n$ <= c forall n >= n0 (divided by $n$)
- c = , n = ,
- We can't choose a value of c as it would have to be based on n, but we can't choose a value of n before choosing a value of c.
- This means it's unprovable

###### Q12. Given that $f(n) =$ IF even(n) Then n + 3 ELSE $n^2 + 5$, state the Big-Oh behaviour and prove it from the definition 
f(n) = n + 3
		$n^2 + 5$
We work with $n^2 + 5$ as big Oh is looking at the worst case
$n^2 + 5$.
Let's say f(n) = O($n^2$)
Pick n0, c s.t. $n^2 + 5$ <= c$(n^2)$ forall n >= $n_0$
Let's pick c = 6
$n^2 + 5 <= 6n^2$
Let's pick n0 = 1
1 + 5 <= 6
6 <= 6
This holds
Hence: f(n) = O($n^2$)
