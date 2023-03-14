Contents:
[[AI Methods]]

### Implementation
#### Iterated Local Search
``` java
package com.aim.lab02;

import java.util.Random;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
import uk.ac.nott.cs.aim.satheuristics.SATHeuristic;
import uk.ac.nott.cs.aim.searchmethods.SinglePointSearchMethod;

	
public class IteratedLocalSearch extends SinglePointSearchMethod {

	// local search / intensification heuristic
	private SATHeuristic oLocalSearchHeuristic;
	
	// mutation / perturbation heuristic
	private SATHeuristic oMutationHeuristic;
	
	// iom parameter setting
	private int iIntensityOfMutation;
	
	// dos parameter setting
	private int iDepthOfSearch;
	
	/**
	 * 
	 * @param oProblem The problem to be solved.
	 * @param oRandom The random number generator, use this one, not your own!
	 * @param oMutationHeuristic The mutation heuristic.
	 * @param oLocalSearchHeuristic The local search heuristic.
	 * @param iIntensityOfMutation The parameter setting for intensity of mutation.
	 * @param iDepthOfSearch The parameter setting for depth of search.
	 */
	public IteratedLocalSearch(SAT oProblem, Random oRandom, SATHeuristic oMutationHeuristic, 
			SATHeuristic oLocalSearchHeuristic, int iIntensityOfMutation, int iDepthOfSearch) {
		
		super(oProblem, oRandom);
		
		this.oMutationHeuristic = oMutationHeuristic;
		this.oLocalSearchHeuristic = oLocalSearchHeuristic;
		this.iIntensityOfMutation = iIntensityOfMutation;
		this.iDepthOfSearch = iDepthOfSearch;
	}

	/**
	 * 
	 * Main loop for ILS. The experiment framework will continually call this loop until
	 * the allocated time has expired.
	 * 
	 * -- ITERATED LOCAL SEARCH PSEUDO CODE --
	 * 
	 * // syntactic step for the below pseudo code. The solutions in both CURRENT and 
	 * // BACKUP memory indices are invariantly the same at the start of each loop.
	 * s' <- s
	 * 
	 * // apply mutation heuristic "iIntensityOfMutation" times
	 * REPEAT intensityOfMutation TIMES:
	 *     s' <- mutation(s')
	 * 
	 * // apply local search heuristic "iDepthOfSearch" times
	 * REPEAT depthOfSearch TIMES:
	 *     s' <- localSearch(s')
	 * 
	 * // HINT: Remember that the solutions in the CURRENT and BACKUP memory indices should
	 * //       be the SAME after each application of the "runMainLoop()"!
	 *
	 * IF f(s') <= f(s) THEN
	 *     accept();
	 * ELIF
	 *     reject();
	 * FI
	 */
	protected void runMainLoop() {
		
		// TODO
		double prevEval = problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX);
		for (int i = 0; i < iIntensityOfMutation; i++) {
			this.oMutationHeuristic.applyHeuristic(this.problem);
		}
		for (int i = 0; i < iDepthOfSearch; i++) {
			this.oLocalSearchHeuristic.applyHeuristic(this.problem);
		}
		double newEval = problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX);
		if (prevEval < newEval){
			this.problem.copySolution(BACKUP_SOLUTION_INDEX, CURRENT_SOLUTION_INDEX);
		} else {
			this.problem.copySolution(CURRENT_SOLUTION_INDEX, BACKUP_SOLUTION_INDEX);
		}
		
	}
	
	public String toString() {
		return "Iterated Local Search";
	}
}

```
#### RandomMutation
```java
package com.aim.lab02;

import java.util.Random;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
import uk.ac.nott.cs.aim.satheuristics.SATHeuristic;

public class RandomMutation extends SATHeuristic {
	
	public RandomMutation(Random oRandom) {
		
		super(oRandom);
	}

	/**
	 * PSEUDO-CODE
	 * i <- random \in [0, N-1];
	 * s' <- flip(i, s);
	 * 
	 * @param oProblem The problem to be solved.
	 */
	@Override
	public void applyHeuristic(SAT oProblem) {
		
		// TODO
		int val = random.nextInt(oProblem.getNumberOfVariables());
		oProblem.bitFlip(val, BACKUP_SOLUTION_INDEX);
		oProblem.copySolution(BACKUP_SOLUTION_INDEX, CURRENT_SOLUTION_INDEX);
	}

	@Override
	public String getHeuristicName() {

		return "Single-perturbative Random Mutation";
	}

}
```
### Base Output
#### Graph
##### The abomination
![[Pasted image 20230310152640.png]]
##### The actual graph
![[Pasted image 20230310161314.png]]


Depth of Search = 0
Mutational Intensity = 1
#### Description
This is a monstrosity
my laptop screamed for this...
i hope you are happy
i am not
Configuration:
Don't FUCKING run this
### Exercise
#### 1
##### Graph
![[Pasted image 20230310151635.png]]
Depth of Search = 2, 
Intensity of Mutation = 2
##### Explanation
The 2,2 configuration performed much better than the 0,1 configuration. This is very likely due to a depth of search of 0 having no exploitation, and therefore never reaching an optimal solution.
The ideal solution is reached by having a good balance of exploitation and exploration which 2,2 accomplishes
#### 2
##### Graph
![[Pasted image 20230310153506.png]]
Depth of Search = 2,
Intensity of Mutation = 2
##### Explanation
The 2,2 configuration works even better when accepting non-worsening moves. This is most likely due to the extra exploration it allows 
##### However... this is not the best
##### Graph
![[Pasted image 20230310160533.png]]
Depth of search = 3,
Intensity of Mutation = 3
##### Explanation
The 3,3 configuration performs the best, most likely because it allows for more exploration and exploitation.
#### 3
##### Explanation
I think the reason why ILS performs better with non-worsening solutions is due to it already being a local search, and therefore being more focused on exploitation. Non-worsening moves provide better exploration than strictly improving moves, hence providing a better balance and therefore allowing us to reach optimal solutions we couldn't before



