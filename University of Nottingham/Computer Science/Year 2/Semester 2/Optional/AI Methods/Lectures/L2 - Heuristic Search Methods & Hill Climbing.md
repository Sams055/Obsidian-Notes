Contents:
[[AI Methods]]

Objectives:
	1. Main components of (meta/hyper/perturbative) heuristic search/optimisation methods – Representation 
	2. Neighbourhoods 
	3. Evaluation Function 
	4. Hill climbing methods 
	5. Reading: Performance Analysis of Stochastic Local Search Methods – Preliminaries

##### Main Components
###### Search for an optimal solution
- ![[Pasted image 20230208103816.png]]
- When we do optimisation, we want to find an optimal or near-optimal solution in the search landscape
- Based on representation, the search landscape is all possible solutions for a problem instane
- Each nucleotides has 4 options and we have 3 nucleotides
	- So we have 4^3 == 64 possible solutions; this is our search landscape
- In a flowshop with 10 jobs and 7 machines, we want to sequence 10 jobs and find the optimal sequence with respect to some criteria
	- We are looking among 10! solutions; over 3 million
	- We ideally only want to take a sample of the 10! solutions for our algorithm

- The TSP diagram has >1000 cities, and there are so many solutions that occur with the combinatorial explosion
	- By reducing our sample size, we can find local optimums, even for a big problem like this
- Researches make use of benchmark functions to "discretise" a problem to find a local optimum
- We can compare these local optimums to others
###### Main Components
- ![[Pasted image 20230208103828.png]]
- We have candidate solutions and we need to represent them somehow
	- We can use encoding

- The neighbourhood relation is the main difference between algorithms, as this is how we identify which area we are searching
- We want to compare the quality of our solutions
	- How can we say solution A > solution B
	- This is our evaluation function
- We need an intial point to start searching from
###### Representation (Encoding of a solution) - Characteristics
- ![[Pasted image 20230208103838.png]]
- All solutions should be able to be represented with the encoding scheme we choose.
- We need to make sure there is a search path to all solutions in our search space (all solutions should be reachable from other solutions)
- A faster / easy to manipulate algorithm can provide better results
###### Representation 
- ![[Pasted image 20230208103847.png]]
- A thief steals items from a store
- Only 1 knapsack with capacity x
- We need to maximise the number of items we can fit in this problem
- We need to decide which items to take
- We could represent the problem with a binary string representing the price of each.
- our search space is based on the string length
- ![[Pasted image 20230208103854.png]]
- How can we take a tour and visit all the pubs in the city centre?
- We want to travel the shortest total distance
- ![[Pasted image 20230208103911.png]]
- All the variables can get discrete values
- The order which we stack the materials matters in terms of performance
- Instead of binary values, we have integers (in this case 1-5) to represent the layers
- ![[Pasted image 20230208103923.png]]
- How do we create the optimal DNA sequence?
- We can form this into an optimisation problem
- The planning instructions could be the optimal set of commands for a robot
- ![[Pasted image 20230208103931.png]]
- Your computer encodes such expressions into trees
- ![[Pasted image 20230208103938.png]]
- 
###### Boolean Satisfiability Problem
- This is the first problem proven to be NP-Complete
- h = (not(x0) or not(x1)) and (x1 or not(x2)) and (x0) and (x2)
- This is conjunctive normal  form
- 
###### Maximum Satisfiability Problem - Real-world Applications
- ![[Pasted image 20230208103954.png]]
- 
###### Exercise for MSP
- ![[Pasted image 20230208104020.png]]
- Is there such a truth assignment which maximises the number of clauses satisfied?
###### MAX-SAT Problem - Candidate Solution representation
- ![[Pasted image 20230208104038.png]]
- We have the variables represented in binary
- We say how many of the clauses in the expression are satisfied
- This works for binary
- but what happens if we have n variables or x clauses?
###### MAX-SAT problem - Search Space Size
- ![[Pasted image 20230208104050.png]]
- This is not satisfiable; 3 clauses can be satisied by any assignment
##### Evaluation / Objective Function
###### Evaluation Function
![[Pasted image 20230208104122.png]]

![[Pasted image 20230208104138.png]]

###### MAX-SAT Problem - Evaluation function
![[Pasted image 20230208104149.png]]
###### TSP - Evaluation function
![[Pasted image 20230208104200.png]]

###### Evaluation Function - Delta (Incremental) Evaluation
![[Pasted image 20230208104209.png]]

###### Delta Evaluation for TSP
![[Pasted image 20230208104223.png]]

![[Pasted image 20230208104243.png]]

![[Pasted image 20230208104250.png]]


##### Neighbourhoods
###### Neighbourhoods
![[Pasted image 20230208104315.png]]
- The move operator is an operator which will limit the scope of a search to certain bounds based on x
###### Example Neighbourhood for Binary Representation
![[Pasted image 20230208104329.png]]
- Bitflip
- Hamming distance is the number of bits which differ
	- e.g. in HD(011,010) there is only 1 differing bit
	- e.g. in HD(0101,0010) there are 3 differing bits
- Neighbourhood size is the size of the string as that's how many bits can be flipped
- This operator only flips one bit at a time
- We would have a larger hamming distance if the operator flipped more than one bit
###### Example Neighbourhood for Integer/Value Representation
![[Pasted image 20230208104339.png]]
- For each variable we are assigning a value
- If we referred back to the layers problem, we would have n layers and assign k as the number of different kinds of layers
- (k-1)n represents how we have n layers, and we have k different types of layers. 
- so say we had copper, silver and gold layers, and we have 6 layers total
	- The neighbourhood size would be (3-1)x6 = 12 neighbouring solutions 
###### Example Neighbourhood for Permutation Representation
![[Pasted image 20230208104349.png]]
- The pairwise operator only changes adjacent bits, hence we only have n-1 size
- The Insertion operator broadens the number of ways we can swap bits, hence the large size covering the whole set; n(n-1)
![[Pasted image 20230208104356.png]]
- Exchange is *any* two items
- The inversion operator reverses the sequence
##### Hill Climbing Algorithms
###### Search Paradigms - Perturbative Heuristics / Operators
![[Pasted image 20230208104418.png]]

###### Mutational Heuristic / Operator
![[Pasted image 20230208104426.png]]

###### Hill Climbing Heuristic / Operator
![[Pasted image 20230208104439.png]]

###### Hill Climbing Algorithm - Minimisation Problem
![[Pasted image 20230208104452.png]]

###### Hill Climbing Algorithm - Maximisation problem
![[Pasted image 20230208104500.png]]

###### Pseudocode of a Generic Hill Climbing Algorithm
![[Pasted image 20230208104509.png]]

###### More on Hill Climbing
![[Pasted image 20230208104516.png]]

###### Simple Hill Climbing Heuristics
![[Pasted image 20230208104537.png]]

###### Best Improvement (Steepest descent/ascent) Hill-climbing
![[Pasted image 20230208104548.png]]

###### Exercise - Applying best improvement to a MAX-SAT problem instance
![[Pasted image 20230208104559.png]]

###### First Improvement (next descent/ascent) Hill-climbing
![[Pasted image 20230208104607.png]]

###### Exercise - Apply First Improvement to a MAX-SAT Problem Instance
![[Pasted image 20230208104615.png]]

###### Davis's (Bit) Hill-climbing
![[Pasted image 20230208104622.png]]

###### Exercise - Applying Davis's Bit Hill Climbing to a MAX-SAT Problem Instance
![[Pasted image 20230208104632.png]]

###### Random Mutation Hill-Climbing
![[Pasted image 20230208104640.png]]

###### Applying Random Mutation Hill Climbing to a MAX-SAT Problem Instance
![[Pasted image 20230208104653.png]]

###### Hill Climbing Algorithm - Improving vs Non-worsening
![[Pasted image 20230208104702.png]]

###### Exercise - Applying Best Improvement to a MAX-SAT Problem Instance (Accepting non-worsening Moves)
![[Pasted image 20230208104716.png]]

###### Hill Climbing - When to stop
![[Pasted image 20230208104722.png]]

![[Pasted image 20230208104730.png]]

###### Hill Climbing versus Random Walk
![[Pasted image 20230208104756.png]]

###### Strengths of Hill Climbing
![[Pasted image 20230208104817.png]]

###### Weaknesses of Hill Climbing
![[Pasted image 20230208104827.png]]

![[Pasted image 20230208104835.png]]

###### Home Exercise
![[Pasted image 20230208104843.png]]

##### Performance Analysis
###### Which Stochastic Search Algorithm Performs Better for Solving Problem X?
![[Pasted image 20230208104901.png]]

![[Pasted image 20230208104909.png]]

![[Pasted image 20230208104915.png]]

![[Pasted image 20230208104924.png]]

###### Performance Analyisis Using Plots - Other Methods
![[Pasted image 20230208104932.png]]
