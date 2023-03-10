Contents:
[[AI Methods]]
#### Performance Comparison of Stochastic Search Algorithms
##### Which Stochastic Search Algorithm Performs better for Solving Problem X?
![[Pasted image 20230215095457.png]]
- We want to implement the most efficient algorithm
- High quality and near-optimal is the usual goal
![[Pasted image 20230215095621.png]]
- Our evaluations are very much so circumstantial; there is no guarantee one method is absolutely better than another
- In this instance, for inst1 we can say Algorithm A is the best, but that's weak as we haven't tested any other instances
##### Statistical tests, null hypothesis and p-values
![[Pasted image 20230215095657.png]]
- We should do a statistical test of the results to check our conclusion is supported more widely, or if our conclusion is wrong
- A p-value lets us compare the performance variation between algorithms.
- Ideally we want a low p-value below 0.05
- If it's bellow 0.05 we can usually say our hypothesis is true
##### Which Stochastic Search Algorithm Performs better for Solving Problem X? (cont'd)
![[Pasted image 20230215095858.png]]
- Our observation is only valid for instance 1
##### Statistical Tests
![[Pasted image 20230215095829.png]]
- We can compare 1 algorithm to n other algorithms
- We could do multiple comparisons where we compare pairs of algorithms together
- The point is, researchers expect to do at least one of these tests
- An example of assumptions for parametric statistics is assuming a normal distribution
- We don't really care what's happening in the background, as long as we get our p-value and necessary information.
##### Box Plots
![[Pasted image 20230215095953.png]]
- Box plots show distribution side by side
- The outliers are visualised as well; which helps as while one algorithm can have a worse average, it could have a better minimum / maximum
##### Notched Box Plots
![[Pasted image 20230215100007.png]]

##### Problem X (cont'd)
![[Pasted image 20230215100026.png]]
- We can not make a general conclusion as the subset of instances we have still doesn't represent all the instances as a whole.
![[Pasted image 20230215100038.png]]

![[Pasted image 20230215100046.png]]

##### Performance Analysis using plots - other methods
![[Pasted image 20230215100117.png]]
- We can use box plots to show more data for each point
- We are ranking the algorithms as objectively as possible
- We could compare performances across different domains as they are all normalised to values of 0 or 1
#### Metaheuristics
##### What is a Metaheuristic?
![[Pasted image 20230215110433.png]]
- A genetic algorithm is a metaheuristic with components designed for a *specific* problem
	- Acts as a framework for a designing an algorithm
- You cannot reuse a genetic algorithm for one problem for another problem
- 
##### Metaheuristics
![[Pasted image 20230215110452.png]]
- Population based search methods have multiple solutions for conductive search
##### Main Components of a Metaheuristic Search Method (r.v)
![[Pasted image 20230215110504.png]]
- We could experiment on the results
- What changes between heuristics is the guidelines for how they work.
##### Mechanisms for escaping from local optima
![[Pasted image 20230215110537.png]]
- The algorithm realises that it cannot make any improvements to the solution for a long time, so we continue our iterations using a different solution, or restarting all together.
![[Pasted image 20230215110544.png]]
- We could allow worsening solutions to try find another path which lets us move forward
##### Termination Criteria
![[Pasted image 20230215110556.png]]
- We can decide on the conditions; changing it dynamically as our algorithms could vary in termination time
- If all the constraints of a solution are satisfied it's feasible, otherwise it's infeasible
##### Feasibility Example
![[Pasted image 20230215110607.png]]

##### How to deal with infeasible solutions
![[Pasted image 20230215110620.png]]
- We need to make sure we punish constraint violation
#### Local Search Metaheuristics and Iterated Local Search
##### Stochastic Local Search - Single Point Based Iterative Search (Local Search Metaheuristics)
![[Pasted image 20230215110641.png]]
- 
##### The Art of Searching
![[Pasted image 20230215110649.png]]

##### Iterated Local Search (ILS)
![[Pasted image 20230215110702.png]]
- Very general pseudocode, but we choose the components
- We create a solution, first apply perturbation and then the perturbed solution has the local search solution applied to it (hill climbing).
- We then choose whether to accept the solution or not
![[Pasted image 20230215110713.png]]
- An example would be doing a bitflip 10 times or 100 times
- or do a hill climbing pass once or 10 times.
- The perturbation strength is what we use to refer to this
- We want to find an optimal perturbation strength
![[Pasted image 20230215110721.png]]

##### Exercise: Designing an ILS Algorithm for MAX-SAT
![[Pasted image 20230215110842.png]]
- Need to satisfy all of this
##### Applying an ILS algorithm to a MAX-SAT Problem Instance - Exercise
![[Pasted image 20230215110732.png]]
- This is initialisation
![[Pasted image 20230215110739.png]]
- These are the steps; using random bit flip in this case.
- We keep going till termination criteria is met.
![[Pasted image 20230215110744.png]]

##### Designing another ILS for MAX-SAT
![[Pasted image 20230215110858.png]]
- We use Davis instead of steepest descent.
- Even with one component change, we can definitely expect differences.
##### ILS for TSP
![[Pasted image 20230215110907.png]]

##### ILS Guidelines
![[Pasted image 20230215110915.png]]

![[Pasted image 20230215110920.png]]
- We can apply methods for tuning
#### Tabu Search
##### Tabu Search 
![[Pasted image 20230215120643.png]]

##### Tabu Search Algorithm
![[Pasted image 20230215120649.png]]
- The tabu list array gets updated based on how the solution is.
##### Overview
![[Pasted image 20230215120658.png]]
- Forbidding strategy
	- What do we put in the array?
- Freeing Strategy
	- When do we take something out of the array?
- Short-term strategy
	- How do we select our trial solutions
##### Fundamentals
![[Pasted image 20230215120741.png]]

![[Pasted image 20230215120748.png]]

![[Pasted image 20230215120755.png]]

##### Tabu Search for MAX-SAT
![[Pasted image 20230215120808.png]]
- For each variable we can store the search step when it's value last changed within the for loop
##### Iteration of Tabu Search for MAX-SAT
![[Pasted image 20230215120814.png]]

![[Pasted image 20230215120825.png]]

![[Pasted image 20230215120842.png]]

##### Practical Considerations
![[Pasted image 20230215120857.png]]
- Similarly to perturbative strength, we don't want something too high or too low.
#### Introduction to Scheduling
##### Scheduling
![[Pasted image 20230215120914.png]]
- It's all about allocating certain resources to people / tasks
- We want to optimize our objectives
##### Framework and Notation
![[Pasted image 20230215120924.png]]
- We have n jobs and m machines
- We are performing operation of job j on machine i
##### Classification of Scheduling Problems - Notation
![[Pasted image 20230215120943.png]]
- The objective is the minimise and maximise relevant characteristics
##### Sample Machine Characteristics
![[Pasted image 20230215120954.png]]
- The processes time will vary for Qm 
##### Sample Job Characteristics
![[Pasted image 20230215121004.png]]
- We need to consider these characteristics
- 
![[Pasted image 20230215121015.png]]

##### Sample Optimality Criteria
![[Pasted image 20230215121025.png]]

##### Scheduling Notation Examples
![[Pasted image 20230215121035.png]]

##### A single Machine Scheduling Problem
![[Pasted image 20230215121045.png]]
- This should be sufficient notation for illustrating performance.
- Tardiness is 0 if our job completes on time
##### Computing Weighted Tardiness
![[Pasted image 20230215121053.png]]
- Each job requires some processing time
- If the order changes, the shortest processing time changes
- max(x,y) returns the largest value between x and y
##### Home Exercise
![[Pasted image 20230215121120.png]]

![[Pasted image 20230215121112.png]]

![[Pasted image 20230215121130.png]]