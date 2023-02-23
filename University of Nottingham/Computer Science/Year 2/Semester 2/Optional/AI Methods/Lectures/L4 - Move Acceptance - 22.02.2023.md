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
##### Analogy
![[Pasted image 20230220112511.png]]

##### Local Search Metaheuristic Algorithm
![[Pasted image 20230220112518.png]]
- The best solution so far is what we initialise.
- We compute the change in the fitness value
- Get a random value between 0 and 1 for preparedness
- we can accept based on a probability P ($\Delta$ T)
- this is based on metropolis criterion
##### Accepting Moves using SA
![[Pasted image 20230220112527.png]]

##### Cooling / Annealing
![[Pasted image 20230220112541.png]]
- Temperature decreases as time goes by.
- As we decrease the temperature, the probability of acceptance also decreases
##### SA Cooling Schedule
![[Pasted image 20230220112552.png]]

![[Pasted image 20230220112559.png]]
- We need to come up with a suitable starting temperature to meet the conditions
![[Pasted image 20230220112605.png]]
- The value we supply for substitution is a design choice
![[Pasted image 20230220112616.png]]
- We can choose how the iterations are changed / set as a design choice as well.
##### Behaviour of Simulating Annealing - An Example
![[Pasted image 20230220112634.png]]
- We can observe different behaviour at different times.
##### Simulating Annealing with Geometric Cooling
![[Pasted image 20230220112644.png]]
- We are not staying at a certain temperature for a certain number of iterations; we just change the temperature every time.
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
- We are going to focus on Numerical and Behavioural parameters
##### Parameter Setting Methods
![[Pasted image 20230220112830.png]]
- Parameter tuning is similar to machine learning. 
- Make a subset of instances and experiment on our parameters by using tests and results and finding the perfect parameters in advance
- Another approach is parameter control which let's us do this in real time.
##### Classification
![[Pasted image 20230220112845.png]]
- Parameter tuning is *Strongly* recommended
- An algorithm performs better with tuning almost always
##### Parameter Tuning Methods
![[Pasted image 20230220112859.png]]
- We can use intuition, trial and error, a setting, or all of the above
- We made the search space smaller with sequential tuning
##### Automated Parameter Tuning
![[Pasted image 20230220112908.png]]

##### Design of Experiments (DoE)
![[Pasted image 20230220112916.png]]
- They have levels
- The levels can represent things like the settings of the process
- Important outcomes are the best parameter settings
##### Fractional Factorial Designs
![[Pasted image 20230220112927.png]]
- Factorial design means we consider all combinations of settings
- Fractional Factorial design means we can use fewer runs while still getting valuable conclusions
##### Design of Experiments - Sampling
![[Pasted image 20230220112934.png]]

##### Random Sampling
![[Pasted image 20230220112941.png]]
- Random x's
##### Latin Hypercube Sampling
![[Pasted image 20230220112950.png]]
- We can easily visualise this with hypercubes
##### Orthogonal Sampling
![[Pasted image 20230220112958.png]]
- We ensure there is only 1 sample in a row and a column to ensure an appropriate ensemble is formed.
##### Taguchi Orthogonal Arrays Method for Parameter Tuning
###### I
![[Pasted image 20230220113007.png]]

###### II
![[Pasted image 20230220113016.png]]

###### Main Steps
![[Pasted image 20230220113037.png]]
- Once we've got the right orthogonal array, we can conduct the experiments with the selected values.
###### Software Packages
![[Pasted image 20230220113048.png]]

###### Planning
![[Pasted image 20230220113058.png]]
- This would be huge if we didn't choose a subset (taguchi array)
###### Conduct
![[Pasted image 20230220113108.png]]

###### Conduct Experiments
![[Pasted image 20230220113117.png]]
- Conduct the experiments with all the parameter settings
![[Pasted image 20230220113125.png]]

###### Analysis - Main Effects Plot
![[Pasted image 20230220113134.png]]

###### Validation: Confirmation Run
![[Pasted image 20230220113143.png]]

#### Summary
![[Pasted image 20230220113221.png]]

![[Pasted image 20230220113229.png]]

![[Pasted image 20230220113237.png]]



