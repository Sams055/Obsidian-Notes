Contents:
[[AI Methods]]

Implementation:
``` Java
protected void runMainLoop() {

// TODO

this.problem.copySolution(BACKUP_SOLUTION_INDEX, CURRENT_SOLUTION_INDEX);

for (int i = 0; i < iIntensityOfMutation; i++) {

this.oMutationHeuristic.applyHeuristic(this.problem);

}

for (int i = 0; i < iDepthOfSearch; i++) {

this.oLocalSearchHeuristic.applyHeuristic(this.problem);

}

if (this.problem.getObjectiveFunctionValue(CURRENT_SOLUTION_INDEX) <= this.problem.getObjectiveFunctionValue(BACKUP_SOLUTION_INDEX)){

this.problem.copySolution(CURRENT_SOLUTION_INDEX, BACKUP_SOLUTION_INDEX);

} else {

this.problem.copySolution(BACKUP_SOLUTION_INDEX, CURRENT_SOLUTION_INDEX);

}

}
```

``` java
public void applyHeuristic(SAT oProblem) {

// TODO

int val = random.nextInt(oProblem.getNumberOfVariables());

oProblem.bitFlip(val, BACKUP_SOLUTION_INDEX);

oProblem.copySolution(BACKUP_SOLUTION_INDEX, CURRENT_SOLUTION_INDEX);

}
```
![[Pasted image 20230216143352.png]]

0, 1 < configuration
![[Pasted image 20230216144738.png]]

0, 1 <= configuration
![[Pasted image 20230216150029.png]]

