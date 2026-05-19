![[Pasted image 20240627161947.png]]
Big O $(O) \to$ Worst case scenario
Big Omega $(\Omega) \to$ Best case scenario
Big Theta $(\Theta) \to$ Average case scenario
![[Pasted image 20240628012037.png]]

![[Pasted image 20240627194014.png]]
Every tree has a root value (which is the first one here) and in the array every index has the root value of it's tree.

![[Pasted image 20240627194443.png]]
![[Pasted image 20240627194451.png]]
![[Pasted image 20240627195707.png]]
![[Pasted image 20240627195725.png]]
![[Pasted image 20240627195742.png]]
Weighted Quick Union (fuck it)
![[Pasted image 20240628030327.png]]


![[Pasted image 20240627203930.png]]
![[Pasted image 20240627221434.png]]
### Insertion Sort
- Complexity: $O(N^2)$
- Number of swaps in the worst case: $O(N^2)$
- Number of comparisons in the worst case: $O(N^2)$
### Bubble Sort (Exchange Sort)
- Complexity: $\Theta (N^2)$
- Number of swaps in the worst case: $O(N^2)$
- Number of comparisons in the worst case: $\Theta (N^2)$
- Optimized bubble sort: If no swaps in the internal loop break the outer loop because we're done.
### Selection Sort
- Not Stable
- Complexity: $\Theta (N^2)$
- Number of swaps in the worst case: $O(N)$
- Number of comparisons in the worst case: $\Theta (N^2)$
![[Pasted image 20240627230414.png]]
### Shell Sort
- Not Stable
![[Pasted image 20240627231004.png]]
### Counting Sort
- Stable when done from right to left (left to right doesn't guarantee stability)
- Non in-place algorithm. Requires additional memory space.
- Complexity: $\Theta (N)$
### Radix Sort
- Stable
- Not in-place algorithm.
- Complexity: $\Theta (N)$
### Merge Sort
- There is two version:
	- Bottom-up Merge Sort
	- 2-way Merge Sort
- Stable
- Not in-place
- Complexity: $O(NlogN)$