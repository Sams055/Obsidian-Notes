Contents:
[[AI Methods]]

### Implementation
#### Davis' Bit Hill Climbing Algorithm (DBHC)
```java
package com.aim.lab01;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Random;
//import java.util.stream.IntStream;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
//import uk.ac.nott.cs.aim.helperfunctions.ArrayMethods;
import uk.ac.nott.cs.aim.satheuristics.SATHeuristic;


public class DavissBitHC extends SATHeuristic {

	public DavissBitHC(Random random) {
		
		super(random);
	}

	/**
	  * DAVIS's BIT HILL CLIMBING LECTURE SLIDE PSEUDO-CODE
	  *
	  * bestEval = evaluate(currentSolution);
	  * perm = createRandomPermutation();
	  * for(j = 0; j < length[currentSolution]; j++) {
	  * 
	  *     bitFlip(currentSolution, perm[j]); 		//flips j^th bit from permutation of solution producing s' from s
	  *     tmpEval = evaluate(currentSolution);
	  *
	  *     if(tmpEval < bestEval) { 				// if there is improvement (strict improvement)
	  *
	  *         bestEval = tmpEval; 				// accept the best flip
	  *         
	  *     } else { 								// if there is no improvement, reject the current bit flip
	  *
	  *          bitFlip(solution, perm[j]); 		//go back to s from s'
	  *     }
	  * }
	  *
	  * @param problem The problem to be solved.
	  */
	public void applyHeuristic(SAT problem) {
		
		// TODO - implement a single pass of Davis's Bit Hill Climbing
		double bestEval = problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX);
		ArrayList<Integer> perm = createRandomPermutation(problem.getNumberOfVariables()); 
		for(int j = 0; j < problem.getNumberOfVariables(); j++) {
			problem.bitFlip(perm.get(j), CURRENT_SOLUTION_INDEX); 
			double tmpEval = problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX);
			if (tmpEval <= bestEval) {
				bestEval = tmpEval;
			} else {
				problem.bitFlip(perm.get(j), CURRENT_SOLUTION_INDEX); 
			}
		}
	} //
	
	public ArrayList<Integer> createRandomPermutation(int length) {
		ArrayList<Integer> randArr = new ArrayList<Integer>();
		for (int i = 0; i < length; i++)
			randArr.add(i);
		Collections.shuffle(randArr, random);
		return randArr;
	}

	public String getHeuristicName() {

		return "Davis's Bit HC";
	}

}

```
#### Steepest Descent Hill Climbing Algorithm (SDHC)
``` java
package com.aim.lab01;


import java.util.Random;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
import uk.ac.nott.cs.aim.satheuristics.SATHeuristic;


public class SteepestDescentHC extends SATHeuristic {

	public SteepestDescentHC(Random random) {
		
		super(random);
	}

	/**
	  * STEEPEST DESCENT HILL CLIMBING LECTURE SLIDE PSEUDO-CODE
	  *
	  * bestEval = evaluate(currentSolution);
	  * improved = false;
	  * 
	  * for(j = 0; j < length[currentSolution]; j++) {
	  * 
	  *     bitFlip(currentSolution, j); 				//flips j^th bit of current solution
	  *     tmpEval = evaluate(currentSolution);
	  *
	  *     if(tmpEval < bestEval) { 					// remember the bit which yields the best value after evaluation
	  *
	  *         bestIndex = j;
	  *         bestEval = tmpEval; 					//record best achievable solution objective value
	  *         improved = true;
	  *     }
	  *
	  *     bitFlip(currentSolution, j); 				//go back to the initial current solution
	  * }
	  *
	  * if(improved) { bitFlip(currentSolution, bestIndex); }
	  *
	  * @param problem The problem to be solved.
	  */
	public void applyHeuristic(SAT problem) {
		
		// TODO - implement a single pass of Steepest Descent Hill Climbing
		double bestEval = problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX);
		boolean improved = false;
		int bestIndex = 0;
		for(int j = 0; j < problem.getNumberOfVariables(); j++) {
			problem.bitFlip(j, CURRENT_SOLUTION_INDEX);
			double tmpEval = problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX);
			if (tmpEval < bestEval) {
				bestIndex = j;
				bestEval = tmpEval;
				improved = true;
			}
			problem.bitFlip(j, CURRENT_SOLUTION_INDEX);
		}
		if (improved) {
			problem.bitFlip(bestIndex,CURRENT_SOLUTION_INDEX);
		}
	}

	public String getHeuristicName() {
		
		return "Steepest Descent HC";
	}

}

```
### Exercises
#### 1
##### Graph
![[Pasted image 20230310143905.png]]
##### Explanation
DBHC performs better, being able to reach an optimum in under 28 iterations which SDHC cannot
#### 2
##### Graph
![[Pasted image 20230310144119.png]]
##### Explanation
Davis still has the edge with a best solution of 90 over SDHC's 92, however, this can be considered statistically insignificant.
This is most likely due to SDHC having the time to reach it's optimum; 1 second was not enough time to reach it's optimum before.
#### 3
##### Graph
###### 1 second
![[Pasted image 20230310143526.png]]

###### 5 seconds
![[Pasted image 20230310143448.png]]

###### 10 seconds
![[Pasted image 20230310143642.png]]

###### 20 seconds
![[Pasted image 20230310143809.png]]

##### Explanation
For Instance 9, DBHC still takes the lead in terms of finding the best possible objective value for the best possible, however on average, SDHC actually performs better across all trials. This is most likely due to DHBC reaching lower local optimums in general due to a higher tendency to explore
