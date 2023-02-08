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
- Based on representation, the search landscape is all possible solutions for a problem instance
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
- We use this to indicate the quality of our solution
- We usually use fitness for evolutionary algorithms
- Cost is used as a business measure
- The feedback it provides is integral to optimising the search process
![[Pasted image 20230208104138.png]]
- We need to run a simulation to figure out how much value we can get out of a solution
- However, this can get expensive
- We could use a parameter to change resolution of a simulation which can save / increase cost and quality of solution
- We don't need an exact evolution function, as long as it's approximately what we need, we are fine
###### MAX-SAT Problem - Evaluation function
![[Pasted image 20230208104149.png]]
- We don't have just 1 solution here
###### TSP - Evaluation function
![[Pasted image 20230208104200.png]]
- We have to go through all the permutations and calculate the distances between the cities, summing up the total distance travelled in our path
###### Evaluation Function - Delta (Incremental) Evaluation
![[Pasted image 20230208104209.png]]
- How do we make things faster?
- We don't need to calculate everything from scratch, we can just use the differences between solutions
- Can we make the calculation of the contribution of the change of representation any faster?
- This is $\Delta$ 
###### Delta Evaluation for TSP
![[Pasted image 20230208104223.png]]
- $\Delta$ = The change of the distance sum from the old model to the new model
![[Pasted image 20230208104243.png]]

![[Pasted image 20230208104250.png]]
- We may have to change our delta evaluation depending on our move operator
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
- Mutational operators let us explore the search space; can jump from one point in the search space to another
- Hill Climbing looks at a certain defined neighbourhood and picks the best one
###### Mutational Heuristic / Operator
![[Pasted image 20230208104426.png]]
- Mutational Heuristics are like blackboxes
- They accept a solution, and the output solution will  be some random modifications on the solution which could be worse than the previous solution
###### Hill Climbing Heuristic / Operator
![[Pasted image 20230208104439.png]]
- Systematic analysis of the neighbourhood solutions results in the output being the same or better than the input.
- Hill climbing algorithms ensure the output is never worse than the input
###### Hill Climbing Algorithm - Minimisation Problem
![[Pasted image 20230208104452.png]]
- For now, consider hill climbing as a local search algorithm
###### Hill Climbing Algorithm - Maximisation problem
![[Pasted image 20230208104500.png]]

###### Pseudocode of a Generic Hill Climbing Algorithm
![[Pasted image 20230208104509.png]]
- For now, we assume we are doing this fully randomly
- We generate each variable assignment randomly
###### More on Hill Climbing
![[Pasted image 20230208104516.png]]
- We pick an initial solution and then repeat to get better and better solutions.
- We could choose our initial starting point by any methods
###### Simple Hill Climbing Heuristics
![[Pasted image 20230208104537.png]]
- There is also shotgun hill climbing
###### Best Improvement (Steepest descent/ascent) Hill-climbing
![[Pasted image 20230208104548.png]]
- We flip a bit
- We evaluate the function
- If the function has improved, we need to remember this bit flip as our current best case scenario for the solution
###### Exercise - Applying best improvement to a MAX-SAT problem instance
![[Pasted image 20230208104559.png]]
- The number of initial unsatisfied clauses as 1
- We bitflip; if we find we have less unsatisfied clauses, we should remember what bit was flipped to get this solution.
- We did this with one pass; we could do multiple passes if we chose to do so
###### First Improvement (next descent/ascent) Hill-climbing
![[Pasted image 20230208104607.png]]
- In this strategy, we use our new improvement to find the next possible improvement, rather than returning to the initial state
###### Exercise - Apply First Improvement to a MAX-SAT Problem Instance
![[Pasted image 20230208104615.png]]
- As can be seen, we accept the first improvement and move on from said improvement
###### Davis's (Bit) Hill-climbing
![[Pasted image 20230208104622.png]]
- The problem with the previous algorithm is that we only start from the first bit, which can lead to us missing bits.
- We can use Random values to make this more fair.
###### Exercise - Applying Davis's Bit Hill Climbing to a MAX-SAT Problem Instance
![[Pasted image 20230208104632.png]]
- Could stop at 1,**2**,0,3 considering it's already at 0 unsatisfied solutions
###### Random Mutation Hill-Climbing
![[Pasted image 20230208104640.png]]

###### Applying Random Mutation Hill Climbing to a MAX-SAT Problem Instance
![[Pasted image 20230208104653.png]]

###### Hill Climbing Algorithm - Improving vs Non-worsening
![[Pasted image 20230208104702.png]]
- We can define the equality to accept anything that's non-worsening; includes alternative same quality solutions
###### Exercise - Applying Best Improvement to a MAX-SAT Problem Instance (Accepting non-worsening Moves)
![[Pasted image 20230208104716.png]]
- Accepts iteration 3, rather than iteration 2; accepts 3 despite 2 offering the same quality of solution.
- This is the difference between strict improvement and accepting anything that's not worse.
###### Hill Climbing - When to stop
![[Pasted image 20230208104730.png]]
- If the system returns a zero value, we have a perfect solution. We have to say perfect, not optimal, as this is a heuristic which will almost certainly not return the exact optimal solution
- No point applying improvements if there is no initial improvement from the first pass
![[Pasted image 20230208104722.png]]


###### Hill Climbing versus Random Walk
![[Pasted image 20230208104756.png]]
- Hill-climbing exploits the best available solution, but neglects exploring a large amount of the search space
- Random walk explores a large amount of the search space, but doesn't really check or exploit a promising region.
- We ideally want to balance the exploration and exploitation
###### Strengths of Hill Climbing
![[Pasted image 20230208104817.png]]
- Easy to implement
###### Weaknesses of Hill Climbing
![[Pasted image 20230208104827.png]]
- The flat region on the graph is a plateau, which means the solutions there have the same quality.
- We could get stuck in a plateau if our exploration parameter isn't strong enough
![[Pasted image 20230208104835.png]]
- Strictly hill climbing can cause us to get stuck
- We don't know where the global optimum is, so success and failure is only able to be based on our intial point, rather than the best point.
###### Home Exercise
![[Pasted image 20230208104843.png]]

##### Performance Analysis
###### Which Stochastic Search Algorithm Performs Better for Solving Problem X?
![[Pasted image 20230208104901.png]]
- We need to run them multiple times to understand the search behaviour
- We have an objective value at the end
![[Pasted image 20230208104909.png]]
- It's very clearly A performing the best in **this instance**
- We can't say it performs well on X in general unless that's a consistent conclusion across multiple instances
![[Pasted image 20230208104915.png]]

![[Pasted image 20230208104924.png]]
- A box plot works, but you can use other tools to represent the performance
###### Performance Analyisis Using Plots - Other Methods
![[Pasted image 20230208104932.png]]
- We can use a progress plot to show how the algorithms perform over time.
- We can observe that A is always choosing the best solution
- We can observe that B is choosing alternative solutions as well
