## Index
**Go Back To** [[Primitive Functions]]
## Definition
A method to compute $\int f(x)dx$, where:
$$
f(x) = \frac{P(x)}{Q(x)} = \frac{a_nx^n + \ ... \ + a_1x + a_0}{b_mx^m + \ ... \ + b_1x + b_0}, \ \ \ \binom{a_n \neq 0 \rightarrow \mathrm{deg}(P) = n}{b_m \neq 0 \rightarrow \mathrm{deg}(Q) = m}
$$
## Reduction
If $n \geq m$, before doing anything, it's always good to reduct the function:
$$
\frac{P(x)}{Q(x)} = D(x) + \frac{R(x)}{Q(x)}, \ \ \ \binom{\mathrm{deg}(D) = n-m}{\mathrm{deg}(R) = m-1}
$$
By using Long Division on $P(x)/Q(x)$ we obtain:
- $D(x)$ as the result of the division.
- $R(x)$ as the remainder of the division.
This makes computing the primitive function easier because $\int D(x)dx$ is very easy to compute and the $\int \frac{R(x)}{Q(x)}$ term is now ready for us to compute following the next instructions.
## Algorithm
