Contents:
[[AI Methods]]

#### Local Search Meta Heuristics and Move Acceptance Methods
##### Single Point Based Iterative Search - Revisited
![[Pasted image 20230220112039.png]]
- This is a high level pseudocode for these heuristics
- It is possible to accept non-improving moves
##### Move Acceptance Methods - A Taxonom
![[Pasted image 20230220112046.png]]
- It could be stochastic or non-stochastic
##### Parameter Setting Mechanisms in Move Acceptance
![[Pasted image 20230220112105.png]]
- Static, Dynamic and Adaptive parameter setting are all valid
##### Non-stochastic Basic Move Acceptance Methods
![[Pasted image 20230220112113.png]]
- based on memory, late acceptance makes a comparison to solution quality fro L steps before
##### Late Acceptance Algorithm
###### Pseudocode
![[Pasted image 20230220112133.png]]

###### Sample run
![[Pasted image 20230220112149.png]]
- If there is an improvement we accept it
![[Pasted image 20230220112155.png]]
- Our current solution becomes that solution
![[Pasted image 20230220112202.png]]

![[Pasted image 20230220112211.png]]
- They all get the perfect solution, but it's very clear by their graph curves which one we would prefer.
##### Non-stochastic Threshold Move Acceptance - minimising
![[Pasted image 20230220112225.png]]
- You decide on the threshold and that threshold changes in time
##### Non-stochastic Threshold Move Acceptance - Examples
![[Pasted image 20230220112237.png]]
- We use a fixed value with static approaches
##### Great Deluge - minimisation
![[Pasted image 20230220112317.png]]
- We decide on the decay rate, but the graph should be similar.
- You linearly decrease the value of fitness.
##### Extended Great Deluge - minimisation
![[Pasted image 20230220112335.png]]
- In time, the value is changed
- You can see the system relaxing it's threshold at the plateaus on the graph
##### Stochastic Move Acceptance
###### Idea
![[Pasted image 20230220112345.png]]

###### Examples
![[Pasted image 20230220112450.png]]

##### Simulated Annealing
![[Pasted image 20230220112501.png]]
- Nature inspired algorithm
- 
##### Analogy
![[Pasted image 20230220112511.png]]

##### Local Search Metaheuristic Algorithm
![[Pasted image 20230220112518.png]]

##### Accepting Moves using SA
![[Pasted image 20230220112527.png]]

##### Cooling / Annealing
![[Pasted image 20230220112541.png]]

##### SA Cooling Schedule
![[Pasted image 20230220112552.png]]

![[Pasted image 20230220112559.png]]

![[Pasted image 20230220112605.png]]

![[Pasted image 20230220112616.png]]

##### Behaviour of Simulating Annealing - An Example
![[Pasted image 20230220112634.png]]

##### Simulating Annealing with Geometric Cooling
![[Pasted image 20230220112644.png]]

##### Exercise
![[Pasted image 20230220112657.png]]

##### Running of SA
![[Pasted image 20230220112709.png]]

![[Pasted image 20230220112714.png]]

#### Parameter Setting Issues and Tuning Methods
##### Metaheuristics
![[Pasted image 20230220112746.png]]

###### Examples of Parameters
![[Pasted image 20230220112807.png]]

##### Parameter Types
![[Pasted image 20230220112819.png]]

##### Parameter Setting Methods
![[Pasted image 20230220112830.png]]

##### Classification
![[Pasted image 20230220112845.png]]

##### Parameter Tuning Methods
![[Pasted image 20230220112859.png]]

##### Automated Parameter Tuning
![[Pasted image 20230220112908.png]]

##### Design of Experiments (DoE)
![[Pasted image 20230220112916.png]]

##### Fractional Factorial Designs
![[Pasted image 20230220112927.png]]

##### Design of Experiments - Sampling
![[Pasted image 20230220112934.png]]

##### Random Sampling
![[Pasted image 20230220112941.png]]

##### Latin Hypercube Sampling
![[Pasted image 20230220112950.png]]

##### Orthogonal Sampling
![[Pasted image 20230220112958.png]]

##### Taguchi Orthogonal Arrays Method for Parameter Tuning
###### I
![[Pasted image 20230220113007.png]]

###### II
![[Pasted image 20230220113016.png]]

###### Main Steps
![[Pasted image 20230220113037.png]]

###### Software Packages
![[Pasted image 20230220113048.png]]

###### Planning
![[Pasted image 20230220113058.png]]

###### Conduct
![[Pasted image 20230220113108.png]]

###### Conduct Experiments
![[Pasted image 20230220113117.png]]

![[Pasted image 20230220113125.png]]

###### Analysis - Main Effects Plot
![[Pasted image 20230220113134.png]]

###### Validation: Confirmation Run
![[Pasted image 20230220113143.png]]

#### Summary
![[Pasted image 20230220113221.png]]

![[Pasted image 20230220113229.png]]

![[Pasted image 20230220113237.png]]



