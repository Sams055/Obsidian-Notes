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
- 
- ![[Pasted image 20230208103854.png]]
- ![[Pasted image 20230208103911.png]]
- ![[Pasted image 20230208103923.png]]
- ![[Pasted image 20230208103931.png]]
- ![[Pasted image 20230208103938.png]]
- 
###### Maximum Satisfiability Problem - Real-world Applications
- ![[Pasted image 20230208103954.png]]
- 
###### Exercise for MSP
- ![[Pasted image 20230208104020.png]]
- 
###### MAX-SAT Problem - Candidate Solution representation
- ![[Pasted image 20230208104038.png]]
- 
###### MAX-SAT problem - Search Space Size
- ![[Pasted image 20230208104050.png]]
- 
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

###### Example Neighbourhood for Binary Representation
![[Pasted image 20230208104329.png]]

###### Example Neighbourhood for Integer/Value Representation
![[Pasted image 20230208104339.png]]

###### Example Neighbourhood for Permutation Representation
![[Pasted image 20230208104349.png]]

![[Pasted image 20230208104356.png]]

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
