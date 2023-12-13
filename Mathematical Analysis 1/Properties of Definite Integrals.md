## Index
**Go Back To** [[The Riemann Integral]]

**NOTE**: The integral gives the area *with sign*.
![[Pasted image 20231212233037.png]]
## Theorem
If a function $f$ is continuous, then it is also *integrable*.

To prove this theorem we should now about *uniform continuity*:
You can see the full proof on *lecture20.pdf*
## What is Uniform Continuity
You can find the exact definition on *lecture20.pdf* or simply searching on the internet. However it's basically this:

Think two points $x_1$ and $x_2$ on the function $f$, then let's define $\delta = |x_1 - x_2|$ and an $\epsilon$ value that is constant.
If we can come up with a such $\epsilon$ that is always bigger than the $\delta$ value, we call that function *uniformly continuous*.
For example $f(x) = \frac{1}{x}$ is not a uniformly continuous function because as we approach $x \to 0$ difference between two points increases infinitely. So we can't establish an $\epsilon$ that is always bigger than those two points.

**NOTE:** If a function is uniformly continuous then it is also continuous but if a function is continuous it may not be uniformly continuous just like $f(x) = \frac{1}{x}$.
## Properties
### Just A Note
We defined $\int_a^bf(x)dx$ when $b > a$, If $a > b$:
$$
\int_a^bf(x)dx := -\int_b^af(x)dx
$$
And if $a = b$:
$$
\int_a^bf(x)dx := 0
$$
### Property 1 (Additivity)
If $a \leq c \leq b$:
$$
\int_a^bf(x)dx = \int_a^cf(x)dx + \int_c^bf(x)dx
$$
![[Pasted image 20231213000358.png]]
### Property 2 (Linearity)
If $f$ and $g$ are integrable and $\alpha$, $\beta \in \mathbb{R}$:
$$
\int_a^b(\alpha f(x) + \beta g(x))dx = \alpha \int_a^bf(x)dx + \beta \int_a^bg(x)dx
$$
### Property 3 (Positivity)
$$
f(x) \geq 0, \ \ \forall x\in(a,b) \Longrightarrow \int_a^bf(x)dx \geq 0
$$
If $\int_a^bf(x)dx = 0$ for the above function then $f \equiv 0$.
### Property 4 (Monotonicity)
If $f(x) \leq g(x) \ \ \forall x \in (a, b)$:
$$
\int_a^bf(x)dx \leq \int_a^bg(x)dx
$$
### Property 5
If $f$ is integrable then $|f|$ is also integrable and:
$$
\bigg|\int_a^bf(x)dx \bigg| \leq \int_a^bf(x)dx
$$
![[Pasted image 20231213002852.png]]