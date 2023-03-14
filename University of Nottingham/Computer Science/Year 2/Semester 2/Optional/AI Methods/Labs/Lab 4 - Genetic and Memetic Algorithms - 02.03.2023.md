Contents:
[[AI Methods]]

### Implementation
#### Memetic Algorithm
``` java
package com.aim.lab04;

import java.util.Random;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
import uk.ac.nott.cs.aim.satheuristics.genetics.CrossoverHeuristic;
import uk.ac.nott.cs.aim.satheuristics.genetics.PopulationHeuristic;
import uk.ac.nott.cs.aim.satheuristics.genetics.PopulationReplacement;
import uk.ac.nott.cs.aim.searchmethods.PopulationBasedSearchMethod;

/**
 * Memetic Algorithm ( local search should to be added per the exercise(s) ).
 * 
 * @author Warren G. Jackson
 *
 */
public class MemeticAlgorithm extends PopulationBasedSearchMethod {

	private final CrossoverHeuristic crossover;
	private final PopulationHeuristic mutation;
	private final PopulationHeuristic localSearch;
	private final PopulationReplacement replacement;
	private final TournamentSelection selection;
	
	public MemeticAlgorithm(SAT problem, Random rng, int populationSize, CrossoverHeuristic crossover, 
			PopulationHeuristic mutation, PopulationHeuristic localSearch, PopulationReplacement replacement) {
		
		super(problem, rng, populationSize);
		
		this.crossover = crossover;
		this.mutation = mutation;
		this.localSearch = localSearch;
		this.replacement = replacement;
		this.selection = new TournamentSelection(problem, rng, populationSize);
	}

	/**
	  * Memetic Algorithm pseudocode
	  * Note there is no exact pseudocode since the purpose of this
	  * exercise is that you experiment with applying local search
	  * in different places of the MA.
	  *
	  * BASIC PSEUDO CODE (GA) not MA
	  * (population already initialised)
	  * 
	  * FOR 0 -> populationSize / 2
	  *		select unique parents using tournament selection
	  *			- if the parents are the same, then select parent 2 as the following parent;
	  *     apply crossover to generate offspring
	  *     apply mutation to offspring
	  * ENDFOR
	  *
	  * do population replacement
	  *
	  */
	public void runMainLoop() {

		// TODO implementation of a Memetic Algorithm	
		// note that the heuristics/operators are initialised as member variables at the top of this class!
		// Do NOT re-create your own.
		int tSize = 3;
		int p1, p2;
		for (int i = 0; i < this.POPULATION_SIZE; i += 2) {
			p1 = this.tournamentSelection(tSize);
			p2 = this.tournamentSelection(tSize);
			while (p1 == p2) {
				p2 = this.tournamentSelection(tSize);
			}
			this.crossover.applyHeuristic(p1, p2, i, i+1);
			this.mutation.applyHeuristic(i);
			this.mutation.applyHeuristic(i+1);
			this.localSearch.applyHeuristic(i);
			this.localSearch.applyHeuristic(i+1);
		}
		this.replacement.doReplacement(this.problem, this.POPULATION_SIZE / 2);
	}
	
	public int tournamentSelection(int tournamentSize) {
		
		return selection.tournamentSelection(tournamentSize);
	}
	
	@Override
	public String toString() {
		
		return "Memetic Algorithm";
	}
}


```
#### Java 
### Basic Output
### Exercises
#### 1
##### Graph
###### GA
![[Pasted image 20230314124125.png]]

![[Pasted image 20230314124147.png]]

![[Pasted image 20230314124037.png]]
###### MA
![[Pasted image 20230314124358.png]]

![[Pasted image 20230314124420.png]]
![[Pasted image 20230314124721.png]]

##### Conclusion
The Memetic Algorithm performs better, most likely due to the enhanced exploitation it provides.
#### 2
##### Graph
##### Conclusion
- The best place for the local search is within the loop, after the mutations.
- I believe this is because it allows us to perform more local searches, allowing us to find more solutions, which gives us more oppurtunity to find an optimal solution
#### 3
##### Graph
##### Conclusion


## Old
1250 - 16
![[Pasted image 20230307132131.png]]

![[Pasted image 20230307132257.png]]

5000 generations - 4 populations
![[Pasted image 20230307132715.png]]

2500 generations - 8 population
![[Pasted image 20230307133314.png]]
