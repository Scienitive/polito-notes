## What is a Matrix
Matrices can be defined as "An array of real numbers arranged in $m$ rows and $n$ columns."
![[Pasted image 20240313152911.png]]
### Some Special Cases and Remarks
- The matrix $0_{m,n} \in \mathbb{R}^{m,n}$ whose entries are all $0$ is called *zero matrix*.
- If $m = n$, the matrix is called *square matrix*.
- If $m = 1$, the matrix is called *row matrix*.
- If $n = 1$, the matrix is called *column matrix*.
## Opposite of a Matrix
![[Pasted image 20240313153335.png]]
Simply multiplying every entry of a matrix with $-1$ gives us the *opposite* of it.
## Matrix Equality
![[Pasted image 20240313153524.png]]
For two matrix to be equal there are two rules:
- They have to be the same size.
- Every $a_{i,j}$ should be equal to $b_{i,j}$ for all $i$ and $j$ that is available.
## Transpose of a Matrix
**NOTATION:** If you have a matrix $A$, transpose of it would be $^tA$.
Transpose of a matrix is simply turning every $a_{i,j}$ into $a_{j,i}$. So that means basically you're changing rows and columns.
![[Pasted image 20240313154424.png]]
### Properties of the Transpose of a Matrix
- $^t(^tA) = A$
- $^t(-A) = -(^tA)$
## Diagonal Matrices
If a matrix has all $0$ entries on the places that are not in the main diagonal, that means that matrix is a *diagonal matrix*.
![[Pasted image 20240313154921.png]]
### Special Cases
- The zero matrix $0_{n,n}$ is diagonal.
- **IMPORTANT:** The diagonal matrix whose diagonal entries are all $1$ is called *identity matrix* and is denoted with $I_n$.
![[Pasted image 20240313155213.png]]
## Triangular Matrices
There are four types of triangular matrices:
1) **Upper Triangular:** If all entries below the main diagonal are zero.
2) **Lower Triangular:** If all entries above the main diagonal are zero.
3) **Strictly Upper Triangular:** If it's upper triangular and the diagonal entries are also zero.
4) **Strictly Lower Triangular:** If it's lower triangular and the diagonal entries are also zero.
![[Pasted image 20240313155620.png]]
## Symmetric and Skew Symmetric Matrices
- **Symmetric:** If $^tA = A$ so $a_{i,j} = a_{j,i}$ for all available $i$ and $j$.
- **Skew Symmetric:** If $^tA = -A$ so $a_{i,j} = -a_{j,i}$ for all available $i$ and $j$. Skew Symmetric is also called *anti-symmetric*.
![[Pasted image 20240313160029.png]]