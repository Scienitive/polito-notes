## Index
**Go Back To** [[!Mathematical Analysis 1]]
## Definition
Taylor expansions are polynomials that approximates how a function behaves like around some point.

$P_0(x)$: Taylor polynomial of order zero.
$P_1(x)$: Taylor polynomial of order one.
$P_n(x)$: Taylor polynomial of order $n$.

To find Taylor expansion of the function $f$ at the value $c$, here is the formula:
$$
P_n(x) = f(c) + f'(c)(x-c)^1 + \frac{f''(c)(x-c)^2}{2!} + \frac{f'''(c)(x-c)^3}{3!} + \ ...
$$
Using the sigma notation:
$$
P_n(x) = \sum_{n=0}^{\infty}\frac{f^{(n)}(a)}{n!}(x-a)^n
$$
## Maclaurin Expansions
Maclaurin expansions are Taylor expansions at the point of $x_0 = 0$.
For example, Maclaurin polynomial of $f(x) = e^x$:
- $P_0(x) = 1$
- $P_1(x) = 1 + x$
- $P_2(x) = 1 + x + \frac{1}{2}x^2$
- $P_3(x) = 1 + x + \frac{1}{2}x^2 + \frac{1}{3!}x^3$
- $P_n(x) = 1 + x + \frac{1}{2}x^2 +\ ...\ + \frac{1}{n!}x^n$
## Theorem (Taylor's Formula with Peano's Remainder)
$$
f(x) = Q_n(x) + o((x-x_0)^n), \ \ x \to x_o
$$
If the above is true for the function $f$:
Then $Q_n$ must be the Taylor polynomial of $f$.
## Theorem (Taylor's Formula with Lagrange's Remainder)
$$
f(x) = P_n(x) + \frac{f^{(n+1)}(\xi(x))\cdot(x-x_0)^{n+1}}{(n+1)!}
$$
The right side of $P_n(x)$ is the error term just like the above theorem. $\xi(x)$ is a function that has a value between $x_0$ and $x$.
## Maclaurin Expansions of Elementary Functions
**NOTE:** If $f$ is an even function then $f^{(2k+1)}(x)$ is odd and $f^{(2k)}(x)$ is even. In other words, when $f$ is an even function differentiating the function odd times results in an odd function and differentiating it even times results in an even function. This also means $f^{(2k+1)}(0) = 0$ because all odd functions have the value of $0$ at $0$.
If $f$ is an odd function then the reverse is true: $f^{(2k+1)}(x)$ is even and $f^{(2k)}(x)$ is odd. This means $f^{(2k)}(0) = 0$.

1. $e^x \Longrightarrow 1 + x + \frac{1}{2}x^2 + \ ...\ + \frac{1}{n!}x^n + o(x^n)$
2. $\mathrm{sin}(x) \Longrightarrow x - \frac{1}{3!}x^3 + \frac{1}{5!}x^5 + \ ...\ + \frac{(-1)^n}{(2n+1)!}x^{2n+1} + o(x^{2n+2})$
3. $\mathrm{cos}(x) \Longrightarrow 1 - \frac{1}{2!}x^2 + \frac{1}{4!}x^4 + \ ...\ + \frac{(-1)^n}{(2n)!}x^{2n} + o(x^{2n+1})$
4. $\mathrm{log}(1+x) \Longrightarrow x - \frac{1}{2}x^2 + \frac{1}{3}x^3 + \ ...\ + \frac{1}{n}x^n + o(x^n)$
5. $(1+x)^a \Longrightarrow 1 + ax + \frac{a(a-1)}{2}x^2 + \ ...\ + \frac{a(a-1)...(a-(n-1))}{n!}x^n + o(x^n)$
6. $\mathrm{arctan}(x) \Longrightarrow x - \frac{x^3}{3} + \frac{x^5}{5}+ \ ...\ + \frac{(-1)^n}{2n+1}x^{2n+1} + o(x^{2n+2})$
## Applications of Taylor Expansions
Let $f(x) = P_n(x) + o(x^n), \ \ x \to 0$
Let $g(x) = Q_n(x) + o(x^n), \ \ x \to 0$

$f(x) \pm g(x) = P_n(x) \pm Q_n(x) + o(x^n), \ \ x \to 0$
$f(x) \cdot g(x) = P_n(x) \cdot Q_n(x) + o(x^n), \ \ x \to 0$
For $\frac{f(x)}{g(x)}$ it's better to use Long Division.
For compositions $(fog)$ check the pdf's, it's complicated.
## Local Behavior of Function
Given Taylor Expansion: $f(x) = a_0 + a_1(x-x_0) + \ ...\ + o((x-x_0)^n)$
If $a_0 = a_1 = a_{n-1} = 0 \neq a_m$ Then:
$$
f(x) = a_n(x-x_0)^n + o((x-x_0)^n), \ \ x \to x_o
$$
$a_n(x-x_0)^n$ is the principal part of the function with respect to $(x-x_0)^n$
## Theorem
Suppose $f: \mathbb{R} \to \mathbb{R}$ is differentiable to order $n \geq 2$ at $x_0 \in \mathbb{R}$ and $0 = f'(x_0) = f^{(m-1)}(x_0) \neq f^{(m)}(x_0), \ \ 2 \leq m \leq n$

1. If $m$ is even then $x_0$ is a local extremum point.
	- Local maximum point if $f^{(m)}(x_0) < 0$
	- Local minimum point if $f^{(m)}(x_0) > 0$
2. If $m$ is odd then $x_0$ is an inflection point.
	- Descending if $f^{(m)}(x_0) < 0$
	- Ascending if $f^{(m)}(x_0) > 0$