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
	- Search in Continuous vs Discrete Space
	- Problem Classes
	- Combinatorial Optimisation Problems
	- Search Paradigms
	- Example optimisation techniques
- Heuristic Search / Optimisation
	- Heuristic Search Methods
	- Revisited Bin Packing Problem Instance
	- Travelling Salesman problem (TSP)
		- Heuristic Examples for TSP
			- Nearest Neighbour (NN) Algorithm
			- A Constructive Stochastic Local Search Algorithm for TSP
			- Pairwise exchange (2-opt)
			- A Perturbative Stochastic Local Search Algorithm for TSP
	- Need for Search methodologies
	- Drawbacks of Heuristic Search
- Pseudo-random numbers
	- Deterministic vs Stochastic Heuristic Search
	- Pseudo-random numbers
		- Definition
		- Problems
		- Example
	- Exercises
		- 1
		- 2
		- 3
		- 4
		- 