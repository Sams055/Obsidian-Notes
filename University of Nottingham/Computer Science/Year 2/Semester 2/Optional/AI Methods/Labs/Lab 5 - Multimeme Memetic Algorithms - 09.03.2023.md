Contents:
[[AI Methods]]

### Implementation
#### Multimeme
``` java
package com.aim.lab05;

import java.util.Random;

import com.aim.lab05.dependencies.BitMutation;
import com.aim.lab05.dependencies.DBHC_IE;
import com.aim.lab05.dependencies.DBHC_OI;
import com.aim.lab05.dependencies.MemeplexInheritanceMethod;
import com.aim.lab05.dependencies.PTX1;
import com.aim.lab05.dependencies.SDHC_IE;
import com.aim.lab05.dependencies.SDHC_OI;
import com.aim.lab05.dependencies.TournamentSelection;
import com.aim.lab05.dependencies.TransGenerationalReplacementWithElitism;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.Meme;
import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
import uk.ac.nott.cs.aim.satheuristics.genetics.CrossoverHeuristic;
import uk.ac.nott.cs.aim.satheuristics.genetics.PopulationHeuristic;
import uk.ac.nott.cs.aim.satheuristics.genetics.PopulationReplacement;
import uk.ac.nott.cs.aim.searchmethods.PopulationBasedSearchMethod;

public class MultiMeme extends PopulationBasedSearchMethod {

	/**
	 * The innovation rate setting
	 */
	private final double innovationRate;
	
	private final CrossoverHeuristic crossover;
	private final BitMutation mutation;
	private final PopulationReplacement replacement;
	private final TournamentSelection selection;
	
	private final MemeplexInheritanceMethod inheritance;
	
	private final Random random;

	/**
	 * The possible local search operators to use.
	 */
	private final PopulationHeuristic[] lss; 
	
	// Constructor used for testing. Please do not remove!
	public MultiMeme(SAT problem, Random random, int populationSize, double innovationRate, CrossoverHeuristic crossover, 
			BitMutation mutation, PopulationReplacement replacement, TournamentSelection selection, MemeplexInheritanceMethod inheritance,
			PopulationHeuristic[] lss) {
		
		super(problem, random, populationSize);
		
		this.innovationRate = innovationRate;
		this.crossover = crossover;
		this.mutation = mutation;
		this.replacement = replacement;
		this.selection = selection;
		this.inheritance = inheritance;
		this.lss = lss;
		this.random = random;
	}
	
	public MultiMeme(SAT problem, Random random, int populationSize, double innovationRate) {
		
		this(
			problem,
			random,
			populationSize,
			innovationRate,
			new PTX1(problem, random), // crossover
			new BitMutation(problem, random), // mutation 
			new TransGenerationalReplacementWithElitism(), // replacement 
			new TournamentSelection(populationSize, random, problem), // parent selection
			new SimpleInheritanceMethod(problem, random), // memeplex inheritance
			new PopulationHeuristic[] { // create mapping for local search operators used for meme in meme index 1
				new DBHC_OI(problem, random), // [0]
				new DBHC_IE(problem, random), // [1]
				new SDHC_OI(problem, random), // [2]
				new SDHC_IE(problem, random)  // [3]
			}
		);
	}

	/**
	 * MMA PSEUDOCODE:
	 * 
	 * INPUT: PopulationSize, MaxGenerations, InnovationRate
	 * 
	 * generateInitialPopulation();
	 * FOR 0 -> MaxGenerations
	 * 
	 *     FOR 0 -> PopulationSize / 2
	 *         select parents using tournament selection with tournament size = 3
	 *         apply crossover to generate offspring
	 ####### BEGIN IMPLEMENTING HERE #######
	 *         inherit memeplex using simple inheritance method
	 *         mutate the memes within each memeplex of each child with  probability dependent on the innovation rate
	 *         apply mutation to offspring with intensity of mutation set for each solution dependent on its meme option
	 *         apply local search to offspring with choice of operator dependent on each solution�s meme option
	 *     ENDFOR
	 *     do population replacement
	 ####### STOP IMPLEMENTING HERE #######
	 * ENDFOR
	 * return s_best;
	 */
	public void runMainLoop() {
		
		// set tournament size equal to 3
		final int tSize = 3;

		// TODO implementation of MMA
		for(int i = 0; i < POPULATION_SIZE; i+=2) {
			
			// select two parents. we don't care if they are the same this week
			int p1 = selection.tournamentSelection(tSize);
			int p2 = selection.tournamentSelection(tSize);

			// calculate child indices
			int c1 = i + POPULATION_SIZE;
			int c2 = c1 + 1;
			
			// apply crossover
			crossover.applyHeuristic(p1, p2, c1, c2);

			// TODO implementation of multimeme part
			// ...
			this.inheritance.performMemeticInheritance(p1, p2, c1, c2);
			this.performMutationOfMemeplex(i);
			this.applyMutationForChildDependentOnMeme(c1, 0);
			this.applyMutationForChildDependentOnMeme(c2, 0);
			this.applyLocalSearchForChildDependentOnMeme(c1, 1);
			this.applyLocalSearchForChildDependentOnMeme(c2, 1);
		}
		
		// perform replacement
		replacement.doReplacement(problem, POPULATION_SIZE);
	}
	
	/**
	 * Applies mutation to the child dependent on its current meme option for mutation.
	 * Mapping of meme option to IOM: IntensityOfMutation <- memeOption;
	 * 
	 * @param childIndex The solution memory index of the child to mutate.
	 * @param memeIndex The meme index used for storing the meme relating to the intensity of mutation setting.
	 */
	public void applyMutationForChildDependentOnMeme(int childIndex, int memeIndex) {
		
		// TODO implementation of mutation embedding intensity of mutation from memes
		// ..
		this.mutation.setMutationRate(this.problem.getMeme(childIndex, memeIndex).getMemeOption());
		this.mutation.applyHeuristic(childIndex);
	}
	
	/**
	 * Applies the local search operator to the child as specified by its current meme option.
	 * 
	 * @param childIndex The solution memory index of the child to mutate.
	 * @param memeIndex The meme index used for storing the meme relating to the local search operator setting.
	 */
	public void applyLocalSearchForChildDependentOnMeme(int childIndex, int memeIndex) {
		
		// TODO implementation of local search dependent on memes
		// ...
		this.lss[this.problem.getMeme(childIndex, memeIndex).getMemeOption()].applyHeuristic(childIndex);
	}
	
	/**
	 * Applies mutation to each meme within the memeplex of the specified solution with probability
	 * dependent on the innovation rate.
	 * 
	 * HINT: mutation does not mean bit flip; it only means in this case 
	 * 		that you should MODIFY the current value of the meme option
	 * 		subject to the above definition.
	 * 
	 * @param solutionIndex The solution memory index of the solution to mutate the memeplex of.
	 */
	public void performMutationOfMemeplex(int solutionIndex) {
		
		// TODO implementation of mutation of memeplex
		// ...
		for (int i = 0; i < this.problem.getNumberOfMemes(); i++) {
			if (this.random.nextDouble() <= this.innovationRate) {
				this.problem.getMeme(solutionIndex, i).setMemeOption(this.problem.getMeme(solutionIndex, i).getTotalOptions());
			}
		}
	}
	
	public String toString() {
		
		return "Multimeme Memetic Algorithm";
	}
	
}

```
#### SimpleInheritanceMethod
``` java
package com.aim.lab05;

import java.util.Random;

import com.aim.lab05.dependencies.MemeplexInheritanceMethod;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.Meme;
import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;

public class SimpleInheritanceMethod implements MemeplexInheritanceMethod {

	private final SAT problem;
	private final Random random;
	
	public SimpleInheritanceMethod(SAT problem, Random random) {
		
		this.problem = problem;
		this.random = random;
	}
	
	/**
	 * Copies the memetic material of the parents to the children
	 * using the Simple Inheritance Method.
	 * 
	 * @param parent1 The solution memory index of parent 1.
	 * @param parent2 The solution memory index of parent 2.
	 * @param child1 The solution memory index of child 1.
	 * @param child2 The solution memory index of child 2.
	 * 
	 * Simple Inheritance Method PSEUDOCODE:
	 * 
	 * INPUT: parent1, parent2, child1, child2
	 * IF f( parent1 ) == f( parent2 ) THEN
	 * 
	 *     inherit = random \in { parent1, parent2 }
	 *     child1.memeplex <- inherit.memeplex;
	 *     child2.memeplex <- inherit.memeplex;
	 *     
	 * ELSEIF f( parent1 ) < f( parent2 ) THEN
	 * 
	 *     child1.memeplex <- parent1.memeplex;
	 *     child2.memeplex <- parent1.memeplex;
	 *     
	 * ELSE // parent2 is best
	 * 
	 *     child1.memeplex = parent2.memeplex;
	 *     child2.memeplex = parent2.memeplex;
	 *     
	 * ENDIF
	 * return;
	 */
	@Override
	public void performMemeticInheritance(int parent1, int parent2, int child1, int child2) {
		
		// TODO - implementation of simple inheritance method
		// ...
		if (this.problem.getObjectiveFunctionValue(parent1) == this.problem.getObjectiveFunctionValue(parent2)) {
			int inherit;
			if(this.random.nextInt(1) == 0) {
				inherit = parent1;
			} else {
				inherit = parent2;
			}
			for (int j = 0; j < this.problem.getNumberOfMemes(); j++) {
				this.problem.getMeme(child1, j).setMemeOption(problem.getMeme(inherit, j).getMemeOption());
				this.problem.getMeme(child2, j).setMemeOption(problem.getMeme(inherit, j).getMemeOption());
			}
		} else if (this.problem.getObjectiveFunctionValue(parent1) < this.problem.getObjectiveFunctionValue(parent2)) {
			for (int j = 0; j < this.problem.getNumberOfMemes(); j++) {
				this.problem.getMeme(child1, j).setMemeOption(problem.getMeme(parent1, j).getMemeOption());
				this.problem.getMeme(child2, j).setMemeOption(problem.getMeme(parent1, j).getMemeOption());
			}
		} else {
			for (int j = 0; j < this.problem.getNumberOfMemes(); j++) {
				this.problem.getMeme(child1, j).setMemeOption(problem.getMeme(parent2, j).getMemeOption());
				this.problem.getMeme(child2, j).setMemeOption(problem.getMeme(parent2, j).getMemeOption());
			}
		}
		
	} 
}


```

### Base Output
![[Pasted image 20230309145201.png]]

![[Pasted image 20230309145247.png]]

![[Pasted image 20230309145256.png]]

### Exercises
#### Exercise 1
##### Instance 1
###### Graph
![[Pasted image 20230309153620.png]]
###### Console
![[Pasted image 20230309153414.png]]

##### Instance 7
###### Graph
![[Pasted image 20230309153744.png]]


###### Console
![[Pasted image 20230309153910.png]]

##### Instance 9
###### Graph
![[Pasted image 20230309153947.png]]

###### Console
![[Pasted image 20230309154013.png]]

##### Answer
Meme 0:
1: 0 - 4 - 2 - 1 - 3
7: 2 - 1 - 0 - 3 - 4
9: 3 - 2 - 0/4 - 1
Allele 2 has the best mutation, closely followed by Allele 0
These are: 
- Improving or Equal - Davis
- Improving Only - Steepest

Meme 1:
1: 1 - 0 - 2 - 3
7: 1 - 0 - 2 - 3
9: 1 - 0 - 2 - 3
Allele 1 has by far the best mutation
This is:
- Improving or Equal - Davis
#### Exercise 2
##### Console 1
![[Pasted image 20230309155249.png]]

##### Console 7 
![[Pasted image 20230309155324.png]]

##### Console 9
![[Pasted image 20230309155359.png]]

##### Answer
The Alleles perform much more similarly to each other
Lots of exploration, not much exploitation
#### Exercise 3
##### Console 1
![[Pasted image 20230309155643.png]]

##### Console 7
![[Pasted image 20230309155734.png]]

##### Console 9
![[Pasted image 20230309155811.png]]

##### Answer
The Alleles are massively different
Very extreme mutations with emphasis on a single algorithm
High exploitation, low exploration
## Conclusion
Low values of innovation = higher exploitation
High values of innovation = higher exploration

fuck


