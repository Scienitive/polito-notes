## Systems of Linear Equations
- A linear equation in the $n$ unknowns $x_1, x_2, ..., x_n$, with coefficients $\mathbb{K}$, is an equation of form:
$$
a_1x_1 + a_2x_2 + ... + a_nx_n = b
$$
- A system of $m$ linear equations in the $n$ unknowns $x_1, x_2, ..., x_n$, with coefficients $\mathbb{K}$, is a set of $m$ linear equations of the form:
![[Pasted image 20240315222122.png]]
So basically a system of linear equation is this:
![[Pasted image 20240315222209.png]]
## Matrices Associated to a Linear System
![[Pasted image 20240315224812.png]]
![[Pasted image 20240315224824.png]]
![[Pasted image 20240315224846.png]]
## Homogenous and Compatible Linear Systems
A linear system $AX = B$
- Homogenous if the matrix $B = 0_{m,1}$.
- Compatible (consistent) if it has at least one solution.
**NOTE:** A homogenous system is *always* compatible, because it always has the solution $X = 0_{n, 1}$,

> Continue to [[Row Echelon Form]] from here.
## Solving Linear Systems
^4d339e
If we have two matrices $A$ and $B$, their row echelon forms $A'$ and $B'$ can be used when solving linear systems:
$$
AX = B \to A'X = B'
$$
These two systems are equivalent.
### Rouche-Capelli Theorem
Let's consider this linear system of equations $AX = B$ with augmented matrix $(A|B)$ where $A \in \mathbb{K}^{m,n}$ and $B \in \mathbb{K}^{m, 1}$:
1) The system is compatible if and only if $rk(A) = rk(A|B)$.
2) If the system is compatible, it's solution depends on $n - rk(A)$ free parameters (have $n - rk(A)$ degree of freedom).
3) If the system is compatible and $X_0$ is a particular solution, then all other solutions are of the form $X = X_0 + Y$, where $Y$ belongs to the set of solutions of the associated homogenous system $AX = 0_{m,1}$,

> Continue to [[Inverse Matrix#^d544e0]] from here