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
### Step 1 (Factorization of $Q(x)$)
You need to factorize the $Q(x)$ polynomial.

Let's say $Q(x) = x^3-x^2+x-1$:
The factorization of $Q(x) = (x-1)(x^2+1)$

### Step 2 (Partial Fraction Expansion)
This step only works when $\frac{P(x)}{Q(x)}, \ \ {\mathrm{deg}(P) < \mathrm{deg}(Q)}$. So if you have the contrary you should do [[#Reduction]] to achieve this.

In this step for every factor that you get from the previous step you do this:
#### For every first degree factor $(x-a)_m$:
Rewrite the $\frac{P(x)}{Q(x)}$ like this:
$$
\frac{c_1}{(x-a)_1} + \frac{c_2}{(x-a)_2} + \ ... \ + \frac{c_m}{(x-a)_m}
$$
#### For every second degree factor $(x^2 + 2pq + q)_m$:
Rewrite the $\frac{P(x)}{Q(x)}$ like this:
$$
\frac{c_1x+d_1}{(x^2+2pq+q)_1} + \frac{c_2x+d_2}{(x^2+2pq+q)_2} + \ ... \ + \frac{c_mx+d_m}{(x^2+2pq+q)_m}
$$
### Step 3 (Identification of $c$ values)
For explaining this let's go over with an example:
$$
\frac{8x+1}{x^2+x-2} = \frac{8x+1}{(x-1)(x+2)} = \frac{c_1}{x-1} + \frac{c_2}{x+2}
$$
In above example we apply the Step 1 and Step 2 to a function to reach this point.
After this point we should add the all $c$ terms:
$$
\frac{8x+1}{(x-1)(x+2)} = \frac{c_1(x+2)+c_2(x-1)}{(x-1)(x+2)} = \frac{c_1x + 2c_1 + c_2x - c_2}{(x-1)(x+2)} =
$$
$$
\frac{x(c_1+c_2) + 2c_1 - c_2}{(x-1))(x+2)}
$$
After reaching this kind of equation. You should realize that:
$$
8x+1 = x(c_1+c_2) + 2c_1 - c_2
$$
So for this to be true:
- $c_1 + c_2 = 8$
- $2c_1 - c_2 = 1$
And from here you can get $c_1 = 3$ and $c_2 = 5$ so:
$$
\frac{8x+1}{(x-1)(x+2)} = \frac{3}{x-1} + \frac{5}{x+2}
$$
### Step 4 (Primitive Functions of Partial Fraction Expansion)
$$
\int \frac{8x+1}{(x-1)(x+2)}dx = \int \frac{3dx}{x-1} + \int \frac{5dx}{x+2}
$$