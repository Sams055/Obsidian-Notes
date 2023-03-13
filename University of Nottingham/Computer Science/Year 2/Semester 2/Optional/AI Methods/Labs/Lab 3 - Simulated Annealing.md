Contents:
[[AI Methods]]

### Implementation
#### Simulated Annealing
``` java
package com.aim.lab03;


import java.util.ArrayList;
import java.util.Random;

import uk.ac.nott.cs.aim.domains.chesc2014_SAT.SAT;
import uk.ac.nott.cs.aim.searchmethods.SinglePointSearchMethod;


public class SimulatedAnnealing extends SinglePointSearchMethod {
	
	private CoolingSchedule oCoolingSchedule;
	
	public SimulatedAnnealing(CoolingSchedule schedule, SAT problem, Random random) {
		
		super(problem, random);
		
		this.oCoolingSchedule = schedule;
	}

	/**
	 * ================================================================
	 * NOTE: In the same way as last week's exercise, you only need
	 *       to implement the code WITHIN the loop for runMainLoop().
	 *       Everything else is handled by the framework/Lab_03_Runner.
	 * ================================================================
	 * 
	 * PSEUDOCODE for Simulated Annealing:
	 *
	 * INPUT : T_0 and any other parameters of the cooling schedule
	 * s_0 = generateInitialSolution();
	 * Temp <- T_0;
	 * s_{best} <- s_0;
	 * s' <- s_0;
	 *
	 * REPEAT
	 *     s' <- randomBitFlip(s);
	 *     delta <- f(s') - f(s);
	 *     r <- random \in [0,1];
	 *     IF delta < 0 OR r < P(delta, Temp) THEN
	 *         s <- s';
	 *     ENDIF
	 *     s_{best} <- updateBest(); // NOTE: this step is already handled by the framework!
	 *     Temp <- advanceTemperature(); // DO NOT FORGET THIS STEP!!!
	 *     
	 * UNTIL termination conditions are satisfied;
	 *
	 * RETURN s_{best};
	 * 
	 * 
	 * REMEMBER That the solutions in the CURRENT_SOLUTION_INDEX and BACKUP_SOLUTION_INDEX
	 * 	should be the same before returning from 'runMainLoop()'!
	 * 
	 * Here, P is the probability function e^(-delta/T)
	 */
	protected void runMainLoop() {

		// TODO implementation of Simulated Annealing
		// using 'oCoolingSchedule' as the cooling schedule
		int bit = this.random.nextInt(this.problem.getNumberOfVariables());
		this.problem.bitFlip(bit);
		double delta = this.problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX) - this.problem.getObjectiveFunctionValue(BACKUP_SOLUTION_INDEX);
		double r = this.random.nextDouble(1);
		if (delta < 0 || r < Math.exp((-delta)/this.oCoolingSchedule.getCurrentTemperature())) {
			this.problem.bitFlip(bit, BACKUP_SOLUTION_INDEX);
		}
		else {
			this.problem.bitFlip(bit);
		}
		this.oCoolingSchedule.advanceTemperature();
	}
	
	
		
	public String toString() {
		return "Simulated Annealing with " + oCoolingSchedule.toString();
	}
}

```
#### Geometric
``` java
package com.aim.lab03;

/**

*

* @author Warren G. Jackson

*

*/

public class GeometricCooling implements CoolingSchedule {

/**

* Maintain the state of the current temperature

*/

private double dCurrentTemperature;

/**

* The $\alpha$ parameter of the cooling schedule.

* Recall from the lectures what a "reasonable" setting should be but be prepared to experiment to find a "good" value!

*/

private final double dAlpha;

/**

*

* @param initialSolutionFitness The objective value of the initial solution.

*/

public GeometricCooling(double initialSolutionFitness) {

double c = 1.0d; // set to 100% of the initial solution cost for now

this.dCurrentTemperature = c * initialSolutionFitness;

// TODO You will need to find a suitable value for alpha

// through prior knowledge and experimentation!

this.dAlpha = 0.5d;

}

@Override

public double getCurrentTemperature() {

return this.dCurrentTemperature;

}

/**

* DEFINITION: T_{i + 1} = alpha * T_i

*/

@Override

public void advanceTemperature() {

// TODO update the value of the current temperature, 'dCurrentTemperature'

this.dCurrentTemperature *= dAlpha;

}

public String toString() {

return "Geometric Cooling";

}

}
```
#### Lundy and Mees's
``` java
package com.aim.lab03;

/**

*

* @author Warren G. Jackson

*

*/

public class LundyAndMees implements CoolingSchedule {

/**

* Maintain the state of the current temperature

*/

private double dCurrentTemperature;

/**

* The $\beta$ parameter of the Lundy and Mees cooling schedule.

* Recall from the lectures what a "reasonable" setting should be but be prepared to experiment to find a "good" value!

*/

private final double dBeta;

/**

*

* @param initialSolutionFitness

* The objective value of the initial solution. Maybe useful (or

* not) for some setting?

*/

public LundyAndMees(double initialSolutionFitness) {

double c = 1.0d;

this.dCurrentTemperature = c * initialSolutionFitness;

// TODO You will need to find a suitable value for beta

// through prior knowledge and experimentation!

this.dBeta = 0.5d;

}

@Override

public double getCurrentTemperature() {

return dCurrentTemperature;

}

/**

* DEFINITION: T_{i + 1} = T_i / ( 1 + beta * T_i )

*/

@Override

public void advanceTemperature() {

// TODO update the value of the current temperature, 'dCurrentTemperature'

this.dCurrentTemperature = (this.dCurrentTemperature / (1 + (dBeta * this.dCurrentTemperature)));

}

@Override

public String toString() {

return "Lundy and Mees";

}

}
```
### Basic Output
#### Geometric
$\alpha = 0.5$
##### Graph
![[Pasted image 20230313131925.png]]

#### Lundy and Mees's
$\beta = 0.5$
##### Graph
![[Pasted image 20230313132123.png]]

### Exercises
#### 1
##### What do we already know?
- From the lectures, we concluded that the best value of alpha is somewhere between 0.9 - 0.99
##### Graph
###### Low Cooling Value
$\alpha = 0.1$
![[Pasted image 20230313133001.png]]

###### High Cooling Value
$\alpha = 0.9$
![[Pasted image 20230313133148.png]]

###### Ideal Cooling value
$\alpha = 0.96$ 
![[Pasted image 20230313133928.png]]

##### Conclusion
- Anything below 0.9 produces subpar results
- The best value of $\alpha$ is 0.96, having the best average of 28 and the best value of 24
- The range is expected, within 0.9-0.99, and shows the typical behaviour of simulated annealing, that is a higher probability of exploration in the beginning when the probability of accepting worse solutions is higher, dwindling as the geometric nature exponentially lowers such a probability to only accepting better moves.
#### 2
##### What do we already know?
- The lecture suggests that the ideal value for $\beta = 0.0001$  
##### Graph
###### Low Cooling Value
$\beta = 0.1$
![[Pasted image 20230313134715.png]]

###### High Cooling Value
$\beta = 0.9$
![[Pasted image 20230313134549.png]]
###### Ideal Cooling Value
$\beta = 0.0001$
![[Pasted image 20230313134832.png]]

##### Conclusion
- Lundy performs better with a lower beta value
- The ideal value of $\beta$ is 0.0001 which matches our prediction from the lecture
- The graph behaves the way it does because Lundy Mees seems to causes a much higher probability to be prolonged for more iterations, thus making the graph show higher and more aggressive areas where it continually accepts worsening solutions.
#### 3
##### What do we already know?
##### Graph
##### Conclusion

## Old
Lundy:
![[Pasted image 20230223145125.png]]
Ideal Alpha = Beta - [0.0001]
![[Pasted image 20230223145958.png]]
Geometric:
![[Pasted image 20230223145547.png]]
Ideal alpha = 0.9 - 0.99 
Exercise



something
![[Pasted image 20230307130223.png]]
above = 0.5


![[Pasted image 20230307130406.png]]

![[Pasted image 20230307130420.png]]

![[Pasted image 20230307130430.png]]