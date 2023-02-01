Contents:
[[AI Methods]]

### Objectives:
-   Be aware of basic terminology in heuristic search/optimisation for intelligent decision support
-   Be able to discuss why there is a need for heuristic search/optimisation techniques in decision support
-   Understand the difference between real valued and discrete (combinatorial) optimisation 
-   Understand different heuristic search paradigms and be able to identify typology of a given heuristic
-   Understand use of pseudo-random number generators and importance of replicating experiments

### Admin:
- Course Details
	- Activities
		- [Moodle Page](https://moodle.nottingham.ac.uk/course/view.php?id=107559)
		- 2 hour f2f lecture for 12 weeks
		- Formative quizzes every week
		- Discussion forums
	- Assessment
		- 50% Exam
		- 50% coursework
			- 20% - 5 assessed quizzes
				- in-lab
				- top 4 marks will be taken
				- 5% for each quiz
				- Each quiz will have 4-5 multiple choice, fill in the blanks or True/False questions
		- 
			- 30% - mini project in Java
				- Report
				- Demo

- Content
	- Learn modern heuristic search / optimisation techniques
	- Lean fuzzy systems at the introductory level

- Everything shown, said or done in the lectures or labs is examinable
- Provisional topic list
	 ![[Pasted image 20230201102334.png]]
### Lecture:
- Preliminaries
	- Definitions
		- Decision Support
			-  Used in decision making contexts
			- Multi-disciplinary
				Can be used for:
					AI
					Operations research
					Decision Theory
					Decision Analysis
					Statistics	
		- Systems
			- Closed systems are independent of their environment
			- Open systems are dependent on their environment
			- System effectiveness refers to the degree of which goals are achieved
			- System efficiency is a measure of the use of resources to achieve output
				- e.g. speed
		- Problem and Problem Instance
			- ![[Pasted image 20230201110658.png]]
			- Problem Classes
				- ![[Pasted image 20230201110729.png]]
				- 
	- Solving Problems by searching
		- Search for paths to goals
			- efficiently find actions to go from an initial state to a given goal
			- central to AI problems
			- Typical algorithms include
				- Depth First Search (DFS)
				- Breadth First Search (BFS)
				- Uniform Cost Search (UCS)
				- Branch and bound
				- A*
		- Search for solutions
			- More general than searching for paths to goals
			- Efficiently finding a solution to a problem in a large space of candidate solutions
			- Subsumes the first type, since a path through a search tree can be encoded as a candidate solution
	- Global Optimisation
		- Task of finding the best set of admissible conditions to achieve your objective, formulated in mathematical terms
		- The fundamental problem of optimisation is to arrive at the best possible decision / solution in any given set of circumstances
		- In most case "the best" (optimal) is unattainable

	- Global and Local Optimum
		- Global Optimum is a solution better than all other solutions (best)
		- Local Optimum is a solution better than all solutions in a certain neighbourhood
			![[Pasted image 20230201110145.png]]
		- The graph shows these optimums
	- Solving an optimisation problem
		- ![[Pasted image 20230201110527.png]]
		- 
	- Search in Continuous vs Discrete Space
		- ![[Pasted image 20230201110543.png]]
		- 
		- ![[Pasted image 20230201110607.png]]
		-  
	- Combinatorial Optimisation Problems
		- ![[Pasted image 20230201110803.png]]
		- 
	- Optimisation / Search Methods
		- ![[Pasted image 20230201110840.png]]
		- 
	- Search Paradigms
		- Single Point (trajectory) based search 
		- Multi-point (population) based search
		- Perturbative
			- Complete solutions
		- Constructive
			- Partial Solutions
		- Relationships
			- ![[Pasted image 20230201111004.png]]
			- 
	- Example optimisation techniques
		- ![[Pasted image 20230201111031.png]]
		- 
		- Bin Packing Problem Instance
			- ![[Pasted image 20230201111055.png]]
			- 
			- Solution
				- ![[Pasted image 20230201111144.png]]
				- 
				- 
				- 
				- 
				- 
				- 
				- 
				- 
				- 
				- 
				- ![[Pasted image 20230201111156.png]]

		- Performance Comparison
			- ![[Pasted image 20230201111246.png]]

		- ![[Pasted image 20230201111353.png]]
		- 
- Heuristic Search / Optimisation
	- Heuristic Search Methods
		-  A heuristic is a rule of thumb method derived from human intuition.
		⚫ A heuristic is a problem dependent search method which seeks good, i.e. near-optimal solutions, at a reasonable cost (e.g. speed) without being able to guarantee optimality. 
		⚫ Good for solving ill-structured problems, or complex well-structured problems (large-scale combinatorial problems that have many potential solutions to explore).
	- Revisited Bin Packing Problem Instance
		- ![[Pasted image 20230201111620.png]]
		- How would you do it?
		- ![[Pasted image 20230201111644.png]]
		- Largest item first fit heuristic
			- ![[Pasted image 20230201111706.png]]
			- 
	- Case Study : Travelling Salesman problem (TSP)
		- ![[Pasted image 20230201111927.png]]
		- 
		- Heuristic Examples for TSP
			- Nearest Neighbour (NN) Algorithm
				- ![[Pasted image 20230201112137.png]]
				- ![[Pasted image 20230201112147.png]]
				- ![[Pasted image 20230201112153.png]]
				- ![[Pasted image 20230201112201.png]]
				- ![[Pasted image 20230201112207.png]]
				- ![[Pasted image 20230201112214.png]]
				- ![[Pasted image 20230201112223.png]]
				- 
			- A Constructive Stochastic Local Search Algorithm for TSP
				- ![[Pasted image 20230201112253.png]]
				- 
			- Pairwise exchange (2-opt)
				- ![[Pasted image 20230201112314.png]]
				- ![[Pasted image 20230201112324.png]]
				- ![[Pasted image 20230201112333.png]]
				- ![[Pasted image 20230201112343.png]]
				- ![[Pasted image 20230201112357.png]]
				- 
			- A Perturbative Stochastic Local Search Algorithm for TSP
				- ![[Pasted image 20230201112416.png]]
				- 
	- Need for Search methodologies
		- ![[Pasted image 20230201111958.png]]
		- 
	- Drawbacks of Heuristic Search
		- ![[Pasted image 20230201112431.png]]
		- 
- Pseudo-random numbers
	- Deterministic vs Stochastic Heuristic Search
		-  Deterministic heuristic search algorithms provide the same solution when run on the given problem instance regardless of how many times.       
		- Stochastic algorithms contain a random component and may return a different solution at each time they are run on the same instance 
		- Multiple trials/runs should be performed for the experiments/simulations 
		- Being able to repeat/replicate those multiple trials/runs in the experiments/simulations is crucial in science, and 
		- This also enables average performance comparison of different stochastic heuristic search algorithms applying statistical tests
	- Pseudo-random numbers
		- Definition
			- A long sequence of numbers that is produced using a deterministic process but which appear to be random.
			- Note that most computers and programming languages have support to produce pseudorandom numbers, and often with seeding
			- ![[Pasted image 20230201112613.png]]
			- 
		- Problems
			- ![[Pasted image 20230201112638.png]]
			- 
		- Example
			- Middle Square Method
				- This is an early pseudo-random number generator
				- ![[Pasted image 20230201112724.png]]
				- 
	- Exercises
		- 1
			- ![[Pasted image 20230201112750.png]]
			- 
		- 2
			- ![[Pasted image 20230201112800.png]]
			- 
		- 3
			- ![[Pasted image 20230201112816.png]]
			- 
		- 4
			- ![[Pasted image 20230201112831.png]]
			- 