Contents
[[Algorithms, Correctness & Efficiency]]
### Admin

#### Summary
- This half of ACE covers:
	- Algorithms
		- Step-by-step procedure for solving a problem in a finite amount of time
	- Data Structures
		- Lists
		- Binary Trees
		- Heaps
		- Hashmaps
		- Graphs
		- and more!
	- Efficiency
		- We will start with methods to analyse, classify and describe the efficiency of algorithms
			- Needed in order to be able to select "best algorithms"




#### Rough Comments
- This will be less formal than IFR
	- Some definitions and proofs are still formal and should be treated as such
		- Perhaps think of how you could convert them to lean
	- Some portions are less formal: 
		- Interpretations 
		- Every day usage
		- e.g. What would a software development team want to know?
#### Assessment
- 12.5% of the module is coursework
	- Coursework 1
		- 01/03 or 08/03
	- Coursework 2
		- 22/03 or 29/03
	- Coursework 3
		- 03/05 or 10/05
	- <b>NO LATE SUBMISSIONS</b>
	- <b>Three Papers</b> During Wednesday Labs
		- in-class
		- on-paper
		- exam-conditions
		- 30-40 minutes
		- Final mark is your best 2 papers out of 3
- 50% written exam
	- Summer exam session (May / June)
	- Two hours
	- in-person
	- on-paper



#### Tutorials
- One 1-hour tutorial per person
- ADE sessions will just be some weeks (not all)
	- We will be notified on moodle and by email
- These are essentialf or understanding the material, and will help with eh C/Ws, etc.
#### Labs
- Labs will be sessions for doing some formative exercises and getting help as needed in preparation for the C/Ws.
	- ADE Sessions will just be some weeks (not all)
		- Will be notified on moodle and by email
#### Exercises & Hints
- There will be exercises in the slides
- Do them as they will be a vital part of an exam question
- If stuck on an algebra question, then generate your own examples and simply insert small numbers
	- e.g. a=2
### Content
#### What are Algorithms?
	![[Pasted image 20230130111555.png]]

Examples:
	![[Pasted image 20230130111621.png]]


#### What are Data Structures?
	![[Pasted image 20230130111700.png]]
	
Examples:
	Dictionary
		![[Pasted image 20230130111753.png]]
	Google's first (production) server
		![[Pasted image 20230130111850.png]]

#### Aims of the ADE portions
Aim
	![[Pasted image 20230130112354.png]]
	
Objectives
	![[Pasted image 20230130115603.png]]
	
#### Why care about efficiency?
![[Pasted image 20230130115649.png]]
	
![[Pasted image 20230130115708.png]]
	
#### Problem Oriented Approach
![[Pasted image 20230130115735.png]]
	
#### Example Task
![[Pasted image 20230130115801.png]]
	
![[Pasted image 20230130115811.png]]
	
![[Pasted image 20230130115820.png]]
	
![[Pasted image 20230130115837.png]]
	
![[Pasted image 20230130115859.png]]
	
![[Pasted image 20230130115913.png]]
	
![[Pasted image 20230130115924.png]]
- Let's use big(O) notation to express the calculations and base the solution on the array access
- If you think about it, the way the array is accessed is almost identical to bubblesort
- This means our big(O) is O($n^2$)
- if n is $10^9$ then $n^2 = (10^9)^2 = 10^{18}$ 
- O($10^{18}$)
#### Interview Question
![[Pasted image 20230130115948.png]]
	
#### Rough Context within "Programming"
![[Pasted image 20230130120023.png]]
	
#### Rough Contents of the ADE portion
![[Pasted image 20230130120051.png]]
	
#### Maths needed includes:
![[Pasted image 20230130120102.png]]
	Revise logs as they will come up a lot
Properties of Inequalities:
![[Pasted image 20230130120228.png]]
	
Properties of Exponents:
![[Pasted image 20230130120248.png]]
	
Properties of Logarithms:
![[Pasted image 20230130120306.png]]
	
Geometric and Arithmetic Series:
![[Pasted image 20230130120324.png]]
	
#### Summary
![[Pasted image 20230130120419.png]]
	


