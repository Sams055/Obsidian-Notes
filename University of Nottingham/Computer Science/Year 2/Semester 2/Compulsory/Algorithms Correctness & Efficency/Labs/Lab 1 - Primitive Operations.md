Contents:
[[Algorithms, Correctness & Efficiency]]

##### A.
``` Java
static int arrayMax(int[] A) {  
    int n = A.length;  
    if ( n == 0 ) {return -1;}  
    
    // start counting primitive operations from here  
    int currentMax = A[0];                  c += 2 ;  
    for (int p=1; p < n; p++) {  
        c += 0; // for 'anything else'  
        if ( A[p] > currentMax ) {       how many primitives operations in total = 2(n-1)  
            currentMax = A[p];          c += 2;  
        }  
        c += 3; // for 'for loop comparison and increment' 
    }  
    c += 1; // for doing ???  
  
    c += 1; // for the 'return'  
    return currentMax;  
}
```
##### B.
maxN = 10
numRuns = 1
maxVal = 1000
![[Pasted image 20230208093927.png]]
![[Pasted image 20230208093938.png]]
- Problem is that we don't have enough data to properly measure this given we are working with random values

maxN = 30
numRuns = 5
![[Pasted image 20230208094136.png]]

There is much clearer correlation here
We can see on the graph that you could draw a linear line which bounds all of the scatterplot values
Given the number of primitive operations (2 + n(2 + 2 + 3) + 2) = 7n + 4 in the worst case for the loop
for n = 5, we would get 39, which if we look on the graph just fits all the data points.
We can say f(n) = 7n + 3 is the line which acts as a bound for the datapoints
The best run time would be 3n + 4, which as can be seen from the graph, just barely encompassed all the data points

##### C.
![[Pasted image 20230208141236.png]]
The apparent scaling is impossible to tell; however this is to be expected as we are using random values and so the data isn't expected to have an identifiable pattern.

##### D.
![[Pasted image 20230208141715.png]]
Graph:
![[Pasted image 20230208142901.png]]
As can be seen, the graph follows a log(n) pattern
