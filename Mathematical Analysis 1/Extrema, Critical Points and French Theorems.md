## Index
**Go Back To** [[Differential Calculus]]
## Definition
In order to be local maximum point, you need to be the maximum number for a certain neighbourhood. $\forall x \in I_r(x_0) \cap \mathrm{dom}(f)$ : $f(x) \leq f(x_0)$

In order to be *strict* local maximum point, you need to be the *only* maximum number for a certain neighbourhood $\forall x \in I_r(x_0) \cap \mathrm{dom}(f)$ : $f(x) < f(x_0)$

If $f'(x_0) = 0$, Then $x_0$ is a *critical point* of $f$

**NOTE:** Extremum means minimum or maximum.
## Points Where Derivative Doesn't Exist
#### 1) Corner Points
$$
f'_-(x_0) \neq f'_+(x_0)
$$
![[Drawing 2023-12-11 19.26.59.excalidraw]]
#### 2) Vertical Tangent
$$
f'_-(x_0) = f'_+(x_0) = \pm \infty
$$
![[Drawing 2023-12-11 19.31.03.excalidraw]]
#### 3) Cusp Points
$$
f'_-(x_0) = - \infty \ \ \ \ f'_+(x_0) = + \infty
$$
![[Drawing 2023-12-11 19.32.49.excalidraw]]
### Theorem 1 (Fermat)
If the function $f$, has a local minimum or maximum point at point $x$ and $f'(x)$ exists:
Then, $f'(x) = 0$.

**NOTE:** However this does not mean that if $f'(x) = 0$ then $x$ must be a local maximum or minimum point in $f$.
#### Where to look for extremum points:
- Critical points
- Points where $f$ is not differentiable
- Boundary points of $\mathrm{dom}(f)$
### Theorem 2 (Rolle)
In a continuous function $f$ if two points $x$ and $y$ has the same value:
Then there is going to be at least one point $z$ where $f'(z) = 0$.

![[Drawing 2023-12-11 18.32.48.excalidraw]]

### Theorem 3 (Lagrange, Mean Value Theorem)
In a continuous function $f$ if you select two points $x$ and $y$:
Then there is going to be at least one point $z$ where $f'(z) =$ secant line of $x$ and $y$.
$$
\exists z \in (x, y)\ \ \ f'(z) = \frac{f(y) - f(x)}{y - x}
$$

![[Drawing 2023-12-11 18.36.35.excalidraw]]
### Theorem 4 (Cauchy)
Suppose two functions $f$ and $g$ are continuous and differentiable at points $a$ and $b$. Also $g'(x) \neq 0$:
Then
$$
\exists z \in (x, y)\ \ \ \frac{f'(z)}{g'(z)} = \frac{f(y) - f(x)}{g(b) - g)(x)}
$$