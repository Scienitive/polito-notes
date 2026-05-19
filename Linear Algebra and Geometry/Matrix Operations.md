## Matrix Addition
Simply add both matrices elements together to create another matrix.
![[Pasted image 20240313161027.png]]
### Properties of Matrix Addition
 - $A + B = B + A$
 - $A + (B + C) = (A + B) + C$
 - $A + 0_{m,n} = A \to$ So this means the zero matrix is the unique neutral element.
 - $^t(A + B) =\ ^tA +\ ^tB$
## Scalar Multiplication
Simply multiply every entry of the matrix with the scalar number.
![[Pasted image 20240313161636.png]]
### Properties of Scalar Multiplication
- $\alpha_1(\alpha_2A) = (\alpha_1 \alpha_2)A$
- $(\alpha_1 \alpha_2)A = \alpha_1 A + \alpha_2 A$
- $\alpha A = 0_{m,n} \Longleftrightarrow$ either $\alpha = 0$ or $A = 0_{m,n}$
- $^t(\alpha A) = \alpha (^tA)$
![[USEFUL EQUATIONS FOR THE ONE-DIMENSIONAL MOTION OF A PARTICLE.png]]
## Matrix Multiplication
Let's define two matrices:
$A \in \mathbb{R}^{m,p}$
$B \in \mathbb{R}^{p,n}$
Product of these two matrices will be:
$AB \in \mathbb{R}^{m,n}$
And can be computed like this:
![[Pasted image 20240315212450.png]]
![[Pasted image 20240315212503.png]]
**REMARK:** So from this we can understand that $AB \neq BA$.
**REMARK 2:** A matrix can be multiplied by itself if and only if row and column size are equal (if it's a square matrix)
**REMARK 3:** Two non-zero matrices product can produce a zero matrix.
![[Pasted image 20240315214257.png]]
### Properties of Matrix Multiplication
- $A(BC) = (AB)C$
- $\alpha (AB) = (\alpha A)B = A(\alpha B)$
- $(A+B)C = AC + BC$
- $^t(AB) =\ ^tB^tA$