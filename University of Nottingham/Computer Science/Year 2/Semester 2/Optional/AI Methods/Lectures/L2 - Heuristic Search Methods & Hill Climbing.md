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
- 
###### Main Components
- ![[Pasted image 20230208103828.png]]
- 
###### Representation (Encoding of a solution) - Characteristics
- ![[Pasted image 20230208103838.png]]
- 
###### Representation 
- ![[Pasted image 20230208103847.png]]
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
###### Best Improvement (Steepest descent/ascent) Hill-climbing
###### Exercise - Applying best improvement to a MAX-SAT problem instance
###### First Improvement (next descent/ascent) Hill-climbing
###### Exercise - Apply First Improvement to a MAX-SAT Problem Instance
###### Davis's (Bit) Hill-climbing
###### Exercise - Applying Davis's Bit Hill Climbing to a MAX-SAT Problem Instance
###### Random Mutation Hill-Climbing
###### Applying Random Mutation Hill Climbing to a MAX-SAT Problem Instance
###### Hill Climbing Algorithm - Improving vs Non-worsening
###### Exercise - Applying Best Improvement to a MAX-SAT Problem Insrtance (Accepting non-worsening Moves)
###### Hill Climbing - When to stop
###### Hill Climbing versus Random Walk
###### Strengths of Hill Climbing
###### Weaknesses of Hill Climbing
###### Home Exercise
##### Performance Analysis
###### Which Stochastic Search Algorithm Performs Better for Solving Problem X?
###### Performance Analyisis Using Plots - Other Methods