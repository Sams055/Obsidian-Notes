Q1. Prove 5 is O(1)
f(n) = 5
g(n) = 1

Pick c, n0 s.t. 5 <= c(1) forall n >= n0
Pick c, n0 s.t. 5 <= c forall n >= n0
c=5, n0=1 (anything)

Q2. Prove 4 is O(2)
f(n) = 4
g(n) = 2
Pick c, n0 s.t. 4 <= c(2) forall n >= n0
Pick c, n0 s.t. 2 <= c forall n >= n0 (divided by 2)
c = 2, n0 = 1 (trivially true - means we could put anything for n0)

Q3. Prove 2n+1 is O(3n)
f(n) = 2n+1
g(n) = 3n
Pick c, n0 s.t. 2n+1 <= c(3n) forall n >= n0
Pick c, n0 s.t. 2+1/n <= c(3) forall n >= n0 (we divided by n)
(Given n >= 1, (2 + 1/n) will never be greater than 3)
c = 1, n0 = 1 (trivially true - means we could put anything for n0)

Q4. Prove 2n+1 is O(n)
f(n) = 2n+1
g(n) = n
Pick c, n0 s.t. 2n+1 <= c(n) forall n >= n0
Pick c, n0 s.t. 2+1/n <= c forall n >= n0 (divided by n)
c = 3, n0 = 1 (trivially true - means we could put anything for n0)

Q5. 



