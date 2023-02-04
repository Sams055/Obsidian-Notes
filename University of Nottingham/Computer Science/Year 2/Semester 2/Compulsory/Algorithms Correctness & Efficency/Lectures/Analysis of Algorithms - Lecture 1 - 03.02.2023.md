Contents
[[Algorithms, Correctness & Efficiency]]

#### Running Time
![[Pasted image 20230130121012.png]]
- This is setting the scene for big(O) notation
- You will usually have many different inputs with many different runtimes, and we'd be taking the key data points such as:
	- The best
	- The average
	- The worst
- We will usually focus on the "worst case"

#### Experimental Studies
![[Pasted image 20230130121102.png]]
- How do we characterise the plot? 
- a graph is a power law if we increase the $x$ in $x^y$ and $y$ is constant
- a graph is an exponential if we increase the $y$ in $x^y$ and $x$ is constant
#### Limits of Experiments
![[Pasted image 20230130121142.png]]
- Implementing the algorithm may be difficult or time-consuming
- How do you know your inputs are good?
- It is a lot of effort to compare two algorithms directly
#### Limitations of Theory
![[Pasted image 20230130121154.png]]
- Analysis of run-times of algorithms can be difficulty
- Worst case can be very pessemistic 
#### Theory vs Experiment
![[Pasted image 20230130121212.png]]
- Need to make sure the null hypothesis isn't violated during the experiment
- There's a lot of approximations in difficult theory
- People may change the approximations during the experiment which is bad
#### Theoretical Analysis
![[Pasted image 20230130121227.png]]
- If you just do random testing and someone finds a problem, we'll get complaints.
  Make sure however you analyse/test the program, that as many good inputs get tested as possible
#### Pseudocode Recap
![[Pasted image 20230130121240.png]]
- What's actually going on?
![[Pasted image 20230130121254.png]]
- How many of the primitive operations do we do?
- They usually aren't precisely defined.
#### Primitive Operations
![[Pasted image 20230130121325.png]]
- Adding / subtracting is much faster than multiplying / dividing, hence they aren't so precise
#### The Random Access Machine (RAM) Model
![[Pasted image 20230130121402.png]]
- The CPU has a bank of memory cells
- This is essentially programming with a 1D array
#### Limitations of RAM model
![[Pasted image 20230130121414.png]]
- We can't expect to hold truly massive numbers
- We could use packages to deal with these big numbers, but we'll just ignore that entirely
- If you add 2 numbers, you count it as one
- 1 + 1 takes as long as 381513 + 243542
- In other words, we don't care about the number size
#### Counting Primitive Operations
![[Pasted image 20230130121426.png]]
- Lets find the number of primitive operations
![[Pasted image 20230130121441.png]]
- We go round the loop (n-1) times
- We multiply by 2 as we have 2 primitive operations
	- Looking for $A[i]$
	- currentMax variable assignment
- Hence, we have $2(n-1)$ operations on that line
![[Pasted image 20230203161825.png]]
- We use 1 primitive operation to set i to 1
- 
![[Pasted image 20230203161847.png]]

#### Counting is underspecified
	![[Pasted image 20230203161945.png]]

![[Pasted image 20230203161954.png]]

#### Correctness vs. Efficiency
	![[Pasted image 20230203162027.png]]

#### Estimated Running Time
	![[Pasted image 20230203162053.png]]

#### Remarks
	![[Pasted image 20230203162124.png]]

#### Growth Rate of Running Time
![[Pasted image 20230203162152.png]]

#### Exercise
![[Pasted image 20230203162246.png]]

![[Pasted image 20230203162259.png]]

![[Pasted image 20230203162324.png]]

![[Pasted image 20230203162334.png]]

![[Pasted image 20230203162341.png]]

![[Pasted image 20230203162421.png]]

![[Pasted image 20230203162427.png]]

![[Pasted image 20230203162442.png]]

![[Pasted image 20230203162504.png]]

![[Pasted image 20230203162523.png]]

![[Pasted image 20230203162529.png]]

![[Pasted image 20230203162536.png]]

![[Pasted image 20230203162552.png]]

![[Pasted image 20230203162621.png]]

#### Remarks
![[Pasted image 20230203162647.png]]

#### Removing Details
![[Pasted image 20230203162707.png]]

#### Advanced Exercise
![[Pasted image 20230203162725.png]]
