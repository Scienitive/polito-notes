## Index
**Go Back To** [[!Mathematical Analysis 1]]
**Move Further To**
- [[Infinitesimal and Infinite]]
- [[Principal Part]]
## Definitions
$$
\lim_{x \to c} \frac{f(x)}{g(x)} = \ell
$$
- If $\ell$ is finite: $f = O(g)$ as $x \to c$
- If $\ell$ is finite and non-zero: $f \asymp g$ as $x \to c$
- $\ell$ = 1: $f \sim g$ as $x \to c$
- If $\ell$ = 0: $f = o(g)$ as $x \to c$
- If $\ell$ = $\pm \infty$: $g = o(f)$ as $x \to c$
## Properties
- $f \sim g \Longleftrightarrow f = g + o(g)$
- $o(\lambda f) = o(f)$ and $\lambda o(f) = o(f)$
	-  This is true for any constant $\lambda \neq 0$
- $f = o(1)$ means that $f$ converge to $0$ when $x \to c$
	- $\lim_{x \to c}f(x) = \lim_{x \to c} \frac{f(x)}{1} = 0$
	- Similarly $f = O(1)$ means $f$ converges to a finite limit as $x \to c$
- The continuity of a function $f$ at a point $x_0$ can be expressed by means of the symbol $o$
	- $f(x) = f(x_0) + o(1)$ as $x \to x_o$
	- $\lim_{x \to x_0}(f(x) - f(x_o)) = 0$
## Algebra of little o
- $o(x^n) \pm o(x^m) = o(x^{\mathrm{min}(n,m)})$ as $x \to 0$
- $o(x^n) \pm o(x^m) = o(x^{\mathrm{max}(n,m)})$ as $x \to \pm \infty$
- $o(\lambda x^n) = o(x^n)$ for each $\lambda \in \mathbb{R} \setminus \{0\}$
- $g(x)o(x^n) = o(x^n)$ if g is bounded in a neighbourhood of $x = 0$ as $x \to 0$
- $o(x^m)o(x^n) = o(x^{m + n})$ as $x \to 0$
- $(o(x^n))^k = o(x^{kn})$ as $x \to 0$
## Fundamental Limits as $x \to 0$
- $\mathrm{sin}(x) \sim x \Longleftrightarrow \mathrm{sin}(x) = x + o(x)$
- $1 - \mathrm{cos}(x) \asymp x^2 \Longleftrightarrow 1 - \mathrm{cos}(x) = \frac{1}{2}x^2 + o(x^2)$
- $\mathrm{log}(1+x) \sim x \Longleftrightarrow \mathrm{log}(1+x) = x + o(x)$
- $e^x - 1 \sim x \Longleftrightarrow e^x = 1 + x + o(x)$
- $(1+x)^a - 1 \sim ax \Longleftrightarrow (1+x)^a = 1 + ax + o(x)$
## Theorem 1
$f_1 \sim f$ and $g_1 \sim g$ as $x \to c$, Then:
$$
\lim_{x \to c}f(x)g(x) = \lim_{x \to c}f_1(x)g_1(x)
$$
$$
\lim_{x \to c}\frac{f(x)}{g(x)} = \lim_{x \to c}\frac{f_1(x)}{g_1(x)}
$$
## Theorem 2
$f_1 = o(f)$ and $g_1 = o(g)$ as $x \to c$, Then:
$$
\lim_{x \to c}(f(x) + f_1(x))(g(x) + g_1(x)) = \lim_{x \to c}f(x)g(x)
$$
$$
\lim_{x \to c}\frac{f(x) + f_1(x)}{g(x) + g_1(x)} = \lim_{x \to c}\frac{f(x)}{g(x)}
$$