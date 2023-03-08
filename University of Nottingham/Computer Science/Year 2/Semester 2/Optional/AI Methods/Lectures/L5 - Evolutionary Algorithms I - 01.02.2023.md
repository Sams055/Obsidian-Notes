Contents:
[[AI Methods]]

### Part 1
#### Evolutionary Algorithms (EAs)
![[Pasted image 20230301112438.png]]

![[Pasted image 20230301112606.png]]
- The genetic algorithms are the most popular ones
#### Genetic Algorithms
##### Pseudocode
![[Pasted image 20230301113430.png]]
- Binary arguments (2)
- We need to find a way to choose our two candidate solutions from the population
- That's our reproduction
- We're going to select parents for the operations
##### Components
###### Basic
![[Pasted image 20230301113657.png]]
We want variety, hence we can't use a deterministic heuristic
###### Representation
![[Pasted image 20230301113929.png]]
- It is possible that each individual structure has multiple chromosomes (tabloid) but we aren't covering that
- People refer tot he objective value as the fitness value
###### Initialisation
![[Pasted image 20230301114117.png]]
- Random initialisation is usually good with this
##### Example - MAX-SAT initialisation
![[Pasted image 20230301114224.png]]

![[Pasted image 20230301114246.png]]
- We need 4 individuals and 6 entries
- These are coming from the pseudo-random number generator
- All of these will have to be converted into a binary string.
- e.g. if >=0.5 = 1 & <0.5 = 0
#### GA Components
##### Fitness Calculation
![[Pasted image 20230301114420.png]]
- We will choose parents based on fitness values
##### MAX-SAT Fitness Calculation
![[Pasted image 20230301114715.png]]

##### Reproduction
![[Pasted image 20230301114704.png]]

#### Fitness Proportionate Selection - Roulette Wheel Selection
![[Pasted image 20230301114914.png]]

#### Roulette wheel Selection
![[Pasted image 20230301115257.png]]

#### Tournament Selection
![[Pasted image 20230301115346.png]]
- We choose the one with the best fitness
![[Pasted image 20230301115451.png]]

##### MAX-SAT Example
#### Recombination - crossover
![[Pasted image 20230301115612.png]]

#### MAX-SAT 1PTX
![[Pasted image 20230301115654.png]]
- 2 point crossover
#### Other Crossover Operators
![[Pasted image 20230301115733.png]]

#### Mutation
![[Pasted image 20230301121117.png]]
- The standard way of applying a mutation is creating an operator that let's us go over all the alleles/variables with a probability of mutating a gene/variable
- How you decide which bit to flip requires us to go through each of the genes/variables one by one
- Mutation rate is a parameter; we need to find the best setting
#### More on Mutation
##### Example of Mutation
![[Pasted image 20230301121818.png]]

![[Pasted image 20230301121829.png]]

#### Replacement Strategy
![[Pasted image 20230301121854.png]]
- Alpha controls the number of the population that needs to be replaced
- We keep the populations size fixed
- We just choose n of that population for the next generation
- Assuming alpha is a value less than n, we can sort the current generation, delete the worst ones and form a new one.
- At every generation, we want improvement from the fitness value

![[Pasted image 20230301122347.png]]
- We keep the top condition the same; two offspring replace two individuals from the old generation
#### Example - Transgenerational GA Replacement (no elitism)
![[Pasted image 20230301122421.png]]
- This is the worst case scenario where we copy every individual for the new generation.
- This isn't very useful

#### Example - TGA Replacement (with elitism)
![[Pasted image 20230301122517.png]]

![[Pasted image 20230301122629.png]]

#### A steady state GA (with elitism)
#### Termination Criteria
![[Pasted image 20230301122735.png]]

#### Convergence
![[Pasted image 20230301122749.png]]
- Gene convergence means most members of the population become alike
- Population convergence means ALL individuals are alike (though they can have different fitness)
- Phenotypic convergence: all individuals have same fitness (don't care about genes)
#### Key Features of EAs
![[Pasted image 20230301123028.png]]
- We ideally want to conduct a search across a search space with multiple points / starting solutions
- Implicit Parallelism is important
### Memetic Algorithms
#### Memetic Algorithms
![[Pasted image 20230301123502.png]]

![[Pasted image 20230301123511.png]]
- They have exploitation and exploration capabilities
- Memetic algorithms are faster and more accurate than GAs on some problems
Generic Approach:
![[Pasted image 20230301123544.png]]

#### Memetic Algorithms (MAs)
![[Pasted image 20230301123820.png]]
##### Example
![[Pasted image 20230301124028.png]]
- General Approach
- Select 2 candidate solutions / individuals
- Hand them over to crossover operator
- crossover operator generates 2 new solutions / children
- Borrow the gene values and decide to mutate or not
- Apply hill climbing if memetic algorithm




