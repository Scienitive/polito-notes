## Index
**Go Back To** [[Integral Calculus]]
**Move Further To**
- [[Primitive Functions of Rational Functions]]
## Definition
If $F'(x) = f(x)$ for every x then $F$ is a *primitive function (anti-derivative)* of $f$.

Differentiation: $f(x) \longrightarrow f'(x)$
Primitive: $f'(x) \longrightarrow f(x)$

**NOTE:** A primitive is not unique since $(F(x)+c)' = F'(x) = f(x)$ for any constant $c \in \mathbb{R}$.
Also this means that if $F$ is a primitive you can find *all* other primitives by $F(x)+c$ for $c \in \mathbb{R}$.

**NOTE:** Not all elementary functions have an elementary primitive function. So it may be impossible to find a primitive for a function.

This is the notation we use for primitive functions:
$$
\int f(x)dx \Longleftrightarrow F(x)
$$
## Primitive Functions of Elementary Functions
1. $\int x^adx = \frac{x^{a+1}}{a+1}+c$
2. $\int \frac{1}{x}dx = \int \frac{dx}{x} = \mathrm{log}|x|+c$
3. $\int \mathrm{sin}(x)dx = -\mathrm{cos}(x)+c$
4. $\int \mathrm{cos}(x)dx = \mathrm{sin}(x)+c$
5. $\int e^xdx = e^x+c$
6. $\int \frac{dx}{1+x^2} = \mathrm{arctan}(x)+c$
7. $\int \frac{dx}{\sqrt{1-x^2}} = \mathrm{arcsin}(x)+c$
8. $\int -\frac{dx}{\sqrt{1-x^2}} = \mathrm{arccos}(x)+c$
## Rules For Primitive Functions
### Linearity $$
\int (af(x) + bg(x))dx = a\int f(x)dx + b\int g(x)dx
$$
### Integration by Parts
Integration by Parts is the consequence of the [[Differential Calculus#^cfa238|Product Rule]] in derivatives.
$$
\int f(x)g'(x)dx = f(x)g(x) - \int f'(x)g(x)
$$
An easy way to do Integration by Parts is using a DI method:
Let's say our example is $\int x^2\mathrm{sin}(3x)dx$

| Sign | D | I | 
| :-: | :-: | :-: |  
| + | $x^2$ | $\mathrm{sin}(3x)$ |
| - | $2x$ | $-\frac{1}{3}\mathrm{cos}(3x)$ |
| + | $2$ | $-\frac{1}{9}\mathrm{sin}(3x)$ |
| - | $0$ | $\frac{1}{27}\mathrm{cos}(3x)$ |

$$
\int x^2\mathrm{sin}(3x)dx = -\frac{1}{3}x^2\mathrm{cos}(3x) + \frac{2}{4}x\mathrm{sin}(3x) + \frac{2}{27}\mathrm{cos(3x)} + c
$$
For more information about the DI method, checkout this [Video](https://www.youtube.com/watch?v=2I-_SV8cwsw)
### Integration by Substitution
Integration by Substitution is the consequence of the [[Differential Calculus#^f4a6b6|Chain Rule]] in derivatives.
$$
\int f(\varphi(x))\varphi'(x)dx = F(\varphi(x)) + c
$$
To use this rule we do something called *u-substitution*:
1. Create a variable $u$
2. Differentiate it and then multiply it with $dx$ to get to $du$
3. Write $dx$ in terms of $du$
4. Write the integral in the $u$-world.
5. See if you can come up with the integral.
6. If you can, then you found the answer. Don't forget to convert $u$ to $x$-representative of it.
For more information about the u-substitution, checkout this [Video](https://www.youtube.com/watch?v=3eWxzBbsS9o)