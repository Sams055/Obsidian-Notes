Contents:
[[AI Methods]]

Lab Sheet:
[[COMP2001 Lab 0 Exercise Sheet.pdf]]

All required files and a copy of the lab sheet are in your "Desktop/AIM" folder

- Exercise:
	- Let's try one seed
		- ![[Pasted image 20230202145219.png]]
		- ![[Pasted image 20230202145326.png]]
		- Single seed with f_best, CPU time & nominal time
	- Let's try multiple of the same seed
		- ![[Pasted image 20230202145535.png]]
		- ![[Pasted image 20230202145709.png]]
		- As can be seen, the seeds are all the same, having the same f_best (what we are looking for).
		- The difference in CPU time taken will occur regardless of the seeds due to things out of our control and should really only be considered when it's part of whats being measured.
		- The time taken for the nominal seconds is pre-defined to be 10 seconds, hence it never changes
	- Let's try a different single seed
		- ![[Pasted image 20230202150245.png]]
		- As can be seen from the output, the f_best is different; successfully simulating randomness.
	- Let's try multiple different seeds
		- ![[Pasted image 20230202150521.png]]
		- ![[Pasted image 20230202150602.png]]
		- As can be seen, having multiple different seeds produces multiple different results
		- This is how we simulate randomness using seeds