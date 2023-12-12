## Index
**Go Back To** [[!Mathematical Analysis 1]]
**Move Further To**
- [[Extrema, Critical Points and French Theorems]]
- [[Derivatives of Increasing and Decreasing Functions]]
## Definition
$$
f'(x_0) = \lim_{\Delta x \to 0}\frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}
$$
If this limit exists, Then $f$ is *differentiable* at $x_0$ and $f'(x_0)$ is the *derivative* of $f$ at $x_0$.

**NOTE:** A differentiable function is more *smooth* than a continuous function. So for example: $f(x) = |x|$ this function is continuous everywhere but is not differentiable at $x = 0$. Because, when you try to differentiate it from left and right you get different results so $f'_+(0) \neq f'_-(0)$ and this means the function is not differentiable at 0.

**NOTE:** If a function is differentiable at some point then it must be continuous at that point. But the reverse is not 100% true. Like the $f(x) = |x|$ example.
## Derivatives of Some Elementary Functions
1. $f(x) = ax + b \Longrightarrow f'(x) = a$
2. $f(x) = x^a \Longrightarrow f'(x) = ax^{a-1}$
3. $f(x) = \mathrm{sin}(x) \Longrightarrow f'(x) = \mathrm{cos}(x)$
4. $f(x) = \mathrm{cos}(x) \Longrightarrow f'(x) = -\mathrm{sin}(x)$
5. $f(x) = a^x \Longrightarrow f'(x) = a^x\mathrm{log}(a)$
6. $f(x) = \mathrm{tan}(x) \Longrightarrow f'(x) = \mathrm{sec}^2(x)$
7. $f(x) = \mathrm{arctan}(x) \Longrightarrow f'(x) = \frac{1}{1 + x^2}$
8. $f(x) = \mathrm{arcsin}(x) \Longrightarrow f'(x) = \frac{1}{\sqrt{1 - x^2}}$
9. $f(x) = \mathrm{arccos}(x) \Longrightarrow f'(x) = -\frac{1}{\sqrt{1 - x^2}}$
10. $f(x) = \mathrm{log}(x) \Longrightarrow f'(x) = \frac{1}{x}$
## Algebraic Rules
1. $(f \pm g)'(x) = f'(x) \pm g'(x)$
2. $(fg)'(x) = f'(x)g(x) + f(x)g'(x)$ ^cfa238
3. $(f/g)'(x) = \frac{f'(x)g(x) - f(x)g'(x)}{g^2(x)}$
4. $(fog)'(x) = f'(g(x)) \cdot g'(x)$ **<= Chain Rule** ^f4a6b6
## Higher Order Derivatives
Let $k \in \mathbb{N}$. $f \in C^k(\mathbb{R})$ means that, you can take the derivative of $f$ up to (and including) $k$ times.
So:
- $f \in C^1(\mathbb{R}) \Longrightarrow$ You can only take the first derivative of this function. 
- $f \in C^\infty(\mathbb{R}) \Longrightarrow$ You can take the derivatives of this function infinitely. 