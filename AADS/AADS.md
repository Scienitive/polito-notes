## BST
![[Pasted image 20250122233113.png]]
![[Pasted image 20250123001410.png]]
Pre order is the normal way. 
![[Pasted image 20250123001453.png]]
In order is from min -> max directly.
![[Pasted image 20250123001610.png]]
This is a bit weird but you can understand
![[Pasted image 20250123001700.png]]
it's all about where the print statement is
![[Pasted image 20250123002051.png]]
## Hash
### Double Hashing
![[Pasted image 20250126233719.png]]
### Quadratic Probing
![[Pasted image 20250126234151.png]]
### Linear Probing
![[Pasted image 20250126235613.png]]
## Heaps
![[Pasted image 20250123014006.png]]
## Theory Questions Analyzed
- BST (Order)
- Hash Table (Quadratic Probing)
- Heap
- Graphs {4}

- Quicksort analyze
- combinatorics principle.
- Powerset

- Learn Quicksort (and how to write it) and merge sort
- Make sure you can do the BST theory questions
- Make sure you can do the Hash Table theory questions
- Make sure you can do the Heap theory questions
## Graphs
### Breadth First Search
![[Pasted image 20250126214452.png]]
You start from one node and visit it's neighbour nodes each time... 
- the **predecessor** of a node refers to the node from which the current node was discovered or visited. It essentially indicates the "parent" of the node in the BFS traversal.
### Depth First Search
![[Pasted image 20250126220030.png]]
You start from one node and randomly select a path. Do the same for all nodes selected and when it has no way to go further without revisiting already visited nodes it backtracks to find other paths. That way it traverses all paths.
**NOTE:** Both BTS and DFS have O(V+E) time complexity.
#### Edge Classification
- **TREE:** If you're discovering the node for the first time that edge.
- **BACK:** If you're rediscovering the node because it was ancestor.
- **FORWARD:** If you're rediscovering the node but it's not ancestor.
- **CROSS:** If the edge let's you go from one tree to another.
### Topological Sort?
## Code
![[Pasted image 20250123060949.png]]
File, error and reading file with lines.
**NOTE:** This way buffer also includes newline character
*LEARN HOW TO USE qsort() function*