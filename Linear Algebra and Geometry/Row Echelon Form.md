## Row Echelon Form
A matrix is in *row echelon form* if it satisfies this condition:
- For every non-zero row we can choose a non-zero entry such that the other rows that are below this entry has all zeros in that position.
**NOTE:** We call those entries *pivot*.
![[Pasted image 20240316105309.png]]
**NOTE:** You don't need to know about *strict row echelon form*.
**NOTE:** In a matrix in row echelon form the number of non-zero rows equals the number of pivots.
## Equivalent Systems
Two systems of equations are called *equivalent* if they have the same set of solutions.
## Elementary Row Operations
The elementary row operations are these:
- Add to given row of $A$ a multiple of different row. $(R_i \to R_i + \alpha R_j)$
- Multiply a given row of $A$ by a non-zero constant. $(R_i \to \alpha R_i)$
- Swap two rows of $A$. $(R_i \leftrightarrow R_j)$
## Row Equivalent Matrices
If two matrices become same when you perform finite sequence of *elementary row operations*, then we call them *row equivalent matrices*.

**NOTE:** The process of using elementary row operations to transform a matrix into an equivalent one in row echelon form is called *Gauss Reduction*.
## Rank of a Matrix
Given a matrix $A$, it's *rank* is the number of non-zero rows in any matrix $A'$ (row echelon form of $A$). And the rank is denoted by $rk(A)$.
## Elementary Column Operations
The same way we defined *elementary row operations* we can also define *elementary column operations*. They're nearly the same with the difference of one being related to rows and the other is related to columns.
I don't suggest using this type of operations because you can always *transpose* a matrix then perform *row operations*.

> Continue to [[Systems of Linear Equations#^4d339e]] from here.