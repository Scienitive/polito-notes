## Invertible Matrices
**IMPORTANT NOTE:** When considering multiplicative inverses, we'll only consider *square matrices*.

A matrix $A \in \mathbb{R}^{n,n}$ is invertible if there exists $B \in \mathbb{R}^{n,n}$ such that $AB = BA = I_n$.
If this happens we can say that $B$ is inverse of $A$. So, $A^{-1} = B$.
**NOTE:** Not all matrices are invertible!
### Properties of Invertible Matrices
- $A$ is invertible if and only if the *transpose* $^tA$ is invertible, and $(^tA)^{-1} = B^{-1}A^{-1}$.
- Two matrices $A$ and $B$ is invertible if and only if the *product* $AB$ is invertible, and $(AB)^{-1} = B^{-1}A^{-1}$.
- Inverse of a matrix is *unique*. So if we find a matrix that "works" we can say it is *the* inverse.

> Continue to [[Systems of Linear Equations]] from here
## Computing the Inverse of a Matrix
^d544e0
**IMPORTANT:** A matrix $A \in \mathbb{K}^{n,n}$ is invertible if and only if $rk(A) = n$.
### Method 1
$$
AX = I_n \to I_nX = A^{-1}
$$
$$
(A|I_n) \to (I_n|A^{-1})
$$
Because these two systems are equivalent, If you perform elementary row operations on $(A|I_n)$ in a way that allows you to transform $A$ into $I_n$, whatever appears on the right side of $|$ will be $A^{-1}$.
![[Pasted image 20240316120400.png]]
![[Pasted image 20240316120411.png]]

> Continue to [[Determinants]] from here.
### Method 2
^b28ea4
#### Cofactor Matrix
Let $A$ be:
![[Pasted image 20240317144049.png]]
To obtain the cofactor matrix you should change it like this:
$$
a_{i,j} = (-1)^{i+j} \cdot det(\bar{A}_{ij})
$$
After changing all entries like this, what you obtain will be the cofactor matrix.
#### Adjugate Matrix
Adjugate matrix is simply the *transpose of cofactor matrix*.
#### The method
$$
A^{-1} = \frac{1}{det(A)} \cdot adj(A)
$$
## Important Conclusion
![[Pasted image 20240317144615.png]]

> Continue to [[Geometric Vectors]] from here.