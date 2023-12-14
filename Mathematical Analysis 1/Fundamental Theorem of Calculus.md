## Index
**Go Back To** [[The Riemann Integral]]
[Nice Video](https://www.youtube.com/watch?v=NLU9U8-wJrM)
## Theory
If $f: I \to \mathbb{R}$ is continuous and $F$ is a primitive function of $f$, then for $(a, b) \in I$:
$$
\int_a^bf(x)dx = F(b) - F(a)
$$
## Notation
$$
F(b) - F(a) = F(x)\bigg|_a^b
$$
So an example would be:
$$
\int_0^2x^2dx = \frac{x^3}{3}\bigg|_0^2 = \frac{8}{3} - \frac{0}{3} = \frac{8}{3}
$$
## Consequences of Fundamental Theorem of Calculus
### Integration by Parts
$$
\int_a^bf(x)g'(x)dx = f(x)g(x)\bigg|_a^b - \int_a^bf'(x)g(x)dx
$$
### Integration by Substitution (u-substitution)
[Nice Video](https://www.youtube.com/watch?v=7hCsQOKOYS8)
$$
\int_a^bf(\varphi(x))\varphi'(x)dx = \int_{\varphi(a)}^{\varphi(b)}f(u)du
$$
**NOTE:** When doing Integration by Substitution on definite integrals you don't need to go back from $u$-world to $x$-world at the end because either way you're going to end up with the same result.
#### If $\varphi$ is bijective
We can also conclude:
$$
\int_a^bf(u)du = \int_{\varphi^{-1}(a)}^{\varphi^{-1}(b)}f(\varphi(x))\varphi'(x)dx
$$
So if $\varphi$ is bijective you can also go back. This is rarely useful but sometimes it can be needed.
### Odd and Even Integrals
If $f: [a, -a] \to \mathbb{R}$ is integrable:
#### If $f$ is odd
$$
\int_{-a}^af(x)dx = 0
$$
#### If $f$ is even
$$
\int_{-a}^af(x)dx = 2\int_0^af(x)dx
$$
You can understand why these are true from this image:
![[Pasted image 20231214052239.png]]
**NOTE:** You can find four good examples in *lecture20.pdf*
## Theory
If $\varphi : (-r, r) \to \mathbb{R}$ is continuous and $\varphi(x) = o(x^s), \ x \to 0, \ s \geq 0$ then:
$$
\int_0^x\varphi(t)dt = o(x^{s+1}), \ \  x \to 0
$$
$$
\int_0^xo(t^s)dt = o(x^{s+1}), \ \  x \to 0
$$