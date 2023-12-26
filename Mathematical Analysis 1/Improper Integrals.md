## Index
**Go Back To** [[The Riemann Integral]]
## Definition
So far we have studied integrals of *bounded functions* on a *bounded interval*.
What happens if:
1) We integrate on $[a, +\infty)$ (Unbounded Domain)
2) We integrate an unbounded function
## Unbounded Domain
$$
\int_a^{+\infty}f(x)dx = \lim_{b \to +\infty}\int_a^bf(x)dx
$$
- If this limit exists and it's finite then $f$ is integrable on $[a, +\infty)$ and the improper integral *converges*.
- If the limit is $\pm \infty$, the improper integral *diverges*.
- If the limit does not exits, the improper integral is *indeterminate*.
![[Pasted image 20231219003125.png]]
### Theorem (Comparison Test)
Let $f$ and $g$ be two functions that has the domain $[a, +\infty)$ and $0 \leq f(x) \leq g(x)$
Then we can conclude these statements:
- $0 \leq \int_a^{+\infty}f(x)dx \leq \int_a^{+\infty}g(x)dx$
	- $\int_a^{+\infty}g(x)dx$ converges $\Longrightarrow \int_a^{+\infty}f(x)dx$ converges
	- $\int_a^{+\infty}f(x)dx$ diverges $\Longrightarrow \int_a^{+\infty}g(x)dx$ diverges
### Theorem
Let $f$ and $|f|$ be two functions that has the domain $[a, +\infty)$.
- $\int_a^{+\infty}|f(x)|dx < +\infty$ so it means it converges.
Then we can say:
$|\int_a^{+\infty}f(x)dx| \leq \int_a^{+\infty}|f(x)|dx$
So left side also converges.
In that situation $f$ is called *absolutely integrable*.
## Unbounded Functions
$$
\int_a^bf(x)dx = \lim_{c \to b^-}\int_a^cf(x)dx
$$
$$
\int_a^bf(x)dx = \lim_{c \to a^+}\int_c^bf(x)dx
$$
- If this limit exists and it's finite then $f$ is integrable on $[a, +\infty)$ and the improper integral *converges*.
- If the limit is $\pm \infty$, the improper integral *diverges*.
- If the limit does not exits, the improper integral is *indeterminate*.