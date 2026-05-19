## What Are Determinants
Determinant of a matrix is a number that we associate to any *square matrix*.
## Submatrices
Given a matrix $A$ we can choose to delete some rows and columns to obtain a new matrix that is a *submatrix* of the original one.
$\bar{A}_{ij}$ means, subtract the $i$'th row and $j$'th column from $A$.
![[Pasted image 20240317132242.png]]
## Determinant
Determinant of a square matrix with $n$ rows and columns is denoted like $det(A)$ or $|A|$ and can be defined like this:
- If $n = 1 \to$ $det(A) = a_{1,1}$
- Else:
$$
det(A) = (-1)^{1+1} \cdot a_{1,1} \cdot det(\bar{A}_{11}) \ +\  ... \ + (-1)^{1+n} \cdot a_{1,n} \cdot det(\bar{A}_{1n})
$$
![[Pasted image 20240317133701.png]]
### Laplace Expansion
The above definition is the laplace expansion on the *first row*. But we can create this expansion on any row or any column on the matrix.
![[Pasted image 20240317134437.png]]
- Where $A_{ij} = (-1)^{i+j} \cdot \bar{A}_{ij}$


**NOTE:** Usually when doing laplace expansions you'd want to select a row or a column that has lots of zeros. Because that will make the calculation a lot easier.
### Shortcut For 2x2 Matrices
For this matrix:
![[Pasted image 20240317133922.png]]
$$
det(A) = ad - bc
$$
### Shortcut For 3x3 Matrices (Sarrus Rule)
![[Pasted image 20240317133825.png]]
## Properties of Determinants
### Effects of Elementary Row Operations on Determinant
- $R_i \to R_i + \alpha R_j \Longleftrightarrow det(A') = det(A)$
- $R_i \to \alpha R_i \Longleftrightarrow det(A') = \alpha \cdot det(A)$
- $R_i \leftrightarrow R_j \Longleftrightarrow det(A') = -det(A)$
### Other Properties
- $det(^tA) = det(A)$
- In the matrix, if there is a row or a column of all zeros then: $det(A) = 0$
- If $rk(A) < n \Longleftrightarrow det(A) = 0$
- If $rk(A) = n \Longleftrightarrow det(A) \neq 0$
- $det(AB) = det(A) \cdot det(B)$
- $det(A + B) \neq det(A) + det(B)$
- $det(\lambda A) = \lambda^{n} \cdot det(A)$
- If $A$ is an odd size skew-symmetric matrix, $det(A) = 0$

> Continue to [[Inverse Matrix#^b28ea4]] from here