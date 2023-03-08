Contents:
[[AI Methods]]

### Part 1
#### Curiosities
- When does a genetic algorithm perform better than a memetic algorithm?
- Is the choice of meme important? e.g. hill climibng/local search algorithm?
- Which meme has a better performance in a memetic algorithm?
- Can we combine multiple memes to obtain synergy and improved performance?
### Benchmark Functions
##### Why to use benchmark (test) functions for optimisation
![[Pasted image 20230308110559.png]]
- People design their own algorithms and compare / compete using benchmark tests

##### Classification of benchmark (test) functions
![[Pasted image 20230308110718.png]]
- These are how we classify and find differences between benchmark functions
#### Unimodal function sphere function example
![[Pasted image 20230308111034.png]]
- We sum each variable value, and we have n variables
- We have ranges so it does not extend to infinity
- We can split everything into their variable terms e.g. $x_1^2, x_2^2, x_3^2$ etc.
#### Delta Evaluation in function optimisation
![[Pasted image 20230308111222.png]]
- We compute a new solution by using delta
#### Unimodal function: step function
![[Pasted image 20230308111401.png]]

#### Multimodal function rastrigin's function
![[Pasted image 20230308111532.png]]
- This is continuous, which is the main difference from the step function
#### Multimodal function Ackley's function
![[Pasted image 20230308111627.png]]
- We cannot separate x and y into 2 separate functions
#### Example of sphere function optimisation
![[Pasted image 20230308111650.png]]
- All the $x_i$ change
#### Sphere Function Optimisation - Representation
![[Pasted image 20230308111736.png]]
- We could use minor encoding
- We could have more than one decoding algorithm, but this is one example of doing so
![[Pasted image 20230308111917.png]]

#### Sphere Function Optimisation - Fitness Evaluation (decoding)
![[Pasted image 20230308111930.png]]
- It's just like using a hash
#### More on Function optimization
![[Pasted image 20230308112047.png]]
- We can just use our previous encoding scheme, divided by 1000
#### Weakness of EAs
#### Summary
### Part 2
#### Case Studies

#### Binary vs Gray Encoding
- Grey code basically means we don't let the bits shift by any more than 1 bit
- e.g. normally in a truth table we go:
00
01
10
11
- In greycode, 01 to 10 involves switching both bits; which we don't want. 
00
01
11
10
- or
11
10
00
01
- It is very useful for things like Karnaugh maps, and in this case, making it easier to traverse a search landscape
#### Components of EA's and Settings
- Memes (using bit-flip)
	- SDHC (best improvement)
	- NDHC (first improved)
- Poor performing moves
	- If we use logical operators such as AND 0, for bit flipping, it's considered biased and therefore poor performing hill climbing methods
#### Termination and Performance Comparison Criteria
- Runs are terminated using similar conditions to other algorithms e.g. CPU time exceeded or fitness met
- For performance indicators we use:
	- Success rate
	- Average number of evaluations/configurations
	- Bar chart plots showing the average no. of evaluations in log scale for each algorithm
		- If the success rate is 100%
		- If not 100% the chart is not drawn
#### Results
- The sphere benchmark test produces good results for all the algorithms
- Rosenbrock, Step and Quartic with noise work for some and don't work for others
- Only in the sphere function can you have a memetic algorithm be outperformed by a genetic algorithm
#### Summary
- MA0 (SDHC) is the best meme choice for F4, F13 and F14. (noisy + deceptive)
- MA1 (NDHC) is the best meem choice for F6-F8. (multimodal)
- MA3 (DBHC) is the best meme choice for F2, F3, F5, F10, F12. (functions with plateaus)
- For functuiuons F1, F11 (unimodal) and F9, GA performs slightly better than the memetic algorithm MA1, though the performance difference is insignificant
- Overall, MA2 (RMHC) and MA3 (DBHC) turn out to be the worst and the best meme, respectively among MA0 - MA3
### Part 3
#### Binary Representation for Encoding Permutation
- Binary representation and classical random initialisation, crossover, and mutation operators are not suitable for encoding permutation
	- Could cause illegal permutations for TSP
#### Partially Mapped Crossover (PMX)
- Builds offspring by
	- Choosing a subsequence of a tour from one parent
		- choose two random cut points to server as swapping boundaries
		- swap segments between cut points
	- preserving the order and position of as many cities as possible from other parent
- Exploits important similarities in the value and ordering simulataneously
- PMX 
#### Order Crossover (OX)
- Builds offspring by
	- choosing a subsequence of a tour from one parent
	- preserving relative order of cities from other parent
- Exploits the property that ordering of cities is important, not positions
- Say parent has order 9-3-4-5-2-1-8-7-6
- Say offspring has 4-5-6-7
- Remove offspring values from parents and insert into offspring in the order the parent's remaining values are ordered in
#### Cycle Crossover (CX)
- Randomly select a starting point in p1: 1
- Copy cities form p1 until a cycle is obtained while mapping from p1 to each corresponding city in p2
####
####
####
####
####
####
####
####
####
####
####
####