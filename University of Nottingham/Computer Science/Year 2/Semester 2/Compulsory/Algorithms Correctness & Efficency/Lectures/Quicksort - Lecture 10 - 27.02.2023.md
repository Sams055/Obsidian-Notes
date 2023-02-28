Contents:
[[Algorithms, Correctness & Efficiency]]

#### Quicksort
- Merge sort division is simple, and merging is complicated
- Merge is simple when A and B are sorted and known to be in disjoint ordered ranges
	- All of elements of A are smaller than all those of B
- If A and B are stored as consecutive sub-arrays, then merge actually needs no work at all:
	- Just "forget the boundary"
#### 2-way split
- Quicksort is a randomized sorted algorithm based on the divide-and-conquer paradigm:
	- Divide: pick a random element x (called pivot) and partition S into
		- L: elements less than x
			- Have to be careful it is not empty
		- GE: elements greater than or equal to x
		- 3 way split would split GE into G and E
	- Recure: sort L and GE
	- Conquer: join L, GE
#### In-place or extra workspace
- For sorting algorithms an important issue can be how much extra working space they need besides the space to store the input
- "In-Place" means we work on the initial array itself
#### Partitioning
- 