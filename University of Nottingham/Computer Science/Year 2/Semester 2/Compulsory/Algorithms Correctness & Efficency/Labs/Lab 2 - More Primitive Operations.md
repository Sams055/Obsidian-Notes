Contents:
[[Algorithms, Correctness & Efficiency]]

``` java
static int p(int[] A) {  
    int n = A.length;                      c += 3;  
    int[] B = new int[n];                  c += n;  
  
    int sum = 0;                           c += 1;  
    int max = 0;                          c += 1 ;  
    for (int p=0; p < n; p++) {           c += 6 ;  
        int k = A[p];                      c += 3 ;  
        sum += k;                         c += 4;  
        B[p] = sum;                        c += 4;  
        int m = 0;                         c += 1 ;  
        int s;                            c += 1 ;  
        s = ( n%2 == 0 ? sum : k );         c += 6 ;  
        while ( s >= 2 ) {                c += 2 ;  
            s /= 2;                        c += 3 ;  
            m++;                           c += 3 ;  
        }  
  
        if ( m > max ) {                  c += 3 ;  
            max = m;                      c += 2 ;  
        }  
    }  
    c += 1; // for 'p=0'  
    A = B;                              c += 2;  
    c += 1; // for the 'return'  
    return max;  
}
```

Visualisation
![[Pasted image 20230215102504.png]]

![[Pasted image 20230215103529.png]]
the big-Oh would be the top line
the big-Omega would be the bottom line

Larger Visualisation:
![[Pasted image 20230215103852.png]]

Logarithmic Graph:
![[Pasted image 20230215105140.png]]
