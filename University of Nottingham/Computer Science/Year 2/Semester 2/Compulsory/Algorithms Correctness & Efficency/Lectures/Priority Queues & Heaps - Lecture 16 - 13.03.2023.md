Contents:
[[Algorithms, Correctness & Efficiency]]

### ADT and CDT
#### ADT and CDT
![[Pasted image 20230313094542.png]]

#### in Java
![[Pasted image 20230313094557.png]]

#### utility
![[Pasted image 20230313094605.png]]

#### Priority Queue ADT
![[Pasted image 20230313094615.png]]
- We can use a key and a value to remove values based on key 
#### Total Order Relations
![[Pasted image 20230313094623.png]]

#### Comparator
![[Pasted image 20230313094632.png]]

#### Simple Implementations, CDT, of a Priority Queue
![[Pasted image 20230313094640.png]]
- Since it's unsorted, we have no choice, we have to scan the whole lot to find the minimum key
- Trying to avoid this by using cacheing will just make it harder to get to the next key

#### General Remark
![[Pasted image 20230313094648.png]]

#### Aim
![[Pasted image 20230313094719.png]]

### Heaps
#### Heaps
![[Pasted image 20230313094736.png]]
- Read it top to bottom, left to right.
#### Note on Terminology
![[Pasted image 20230313094748.png]]

#### Exercise
![[Pasted image 20230313094758.png]]

![[Pasted image 20230313094808.png]]

![[Pasted image 20230313094817.png]]

![[Pasted image 20230313094825.png]]

#### Height of a heap
![[Pasted image 20230313094909.png]]
- Height is no more than log(n)
#### Heaps and Priority Queues
![[Pasted image 20230313095031.png]]

#### Insertion into a Heap
![[Pasted image 20230313095040.png]]
- We want to fix the heap order property
#### Upheap
![[Pasted image 20230313095100.png]]

#### Exercises
![[Pasted image 20230313095134.png]]

#### Removal from a Heap
![[Pasted image 20230313095153.png]]

#### Downheap
![[Pasted image 20230313095203.png]]

#### Exercise
![[Pasted image 20230313095210.png]]

![[Pasted image 20230313095216.png]]

![[Pasted image 20230313095224.png]]

![[Pasted image 20230313095233.png]]

![[Pasted image 20230313095237.png]]

![[Pasted image 20230313095244.png]]

![[Pasted image 20230313095250.png]]

![[Pasted image 20230313095306.png]]

![[Pasted image 20230313095312.png]]

![[Pasted image 20230313095317.png]]

![[Pasted image 20230313095324.png]]

![[Pasted image 20230313095329.png]]

#### Array Heap Implementation
![[Pasted image 20230313095344.png]]

#### Implementing Priority Queue with a Heap
![[Pasted image 20230313095352.png]]

#### Heap-Sort
![[Pasted image 20230313095400.png]]

![[Pasted image 20230313095410.png]]

#### Conclusion
![[Pasted image 20230313095421.png]]

#### Important
![[Pasted image 20230313095435.png]]

### Minimal Expectation
![[Pasted image 20230313095444.png]]
