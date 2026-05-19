## Formula
![[Pasted image 20250124042225.png]]
## Properties
### Linearity
$$
\mathcal{L}\big(a \cdot f(t) + b \cdot g(t)\big) = \int_{0}^{\infty} \big(a \cdot f(t) + b \cdot g(t)\big)e^{-st} \, dt
$$
$$
= a \int_{0}^{\infty} f(t)e^{-st} \, dt + b \int_{0}^{\infty} g(t)e^{-st} \, dt
$$
So if you're taking Laplace transformation of two functions summed you can split them into two laplace transformation equations.
### Derivative
#### First derivative
$$
\mathcal{L}\big(f'(t)\big) = s\mathcal{L}\big(f(t)\big) - f(0)
$$
#### Second derivative
$$
\mathcal{L}\big(f''(t)\big) = s\mathcal{L}\big(f'(t)\big) - f'(0)
$$
$$
\mathcal{L}\big(f''(t)\big) = s^2\mathcal{L}\big(f(t)\big) - sf(0) - f'(0)
$$
### Multiplying with Exponential (Modulation)
We know that:
$$
\mathcal{L}\big(cos(2t)\big) = \frac{s}{s^2+4} = F(s)
$$
If you need to take derivative of a function multiplied with an exponential:
$$
\mathcal{L}\big(e^{3t}\cdot cos(2t)\big) = \frac{(s-3)}{(s-3)^2+4} = F(s-3)
$$
So you can change the $s$ to $s-3$ in that case and everything will work out.
### Translation in time
$$
\mathcal{L}\big(f(t-a)\cdot u(t-a)\big) = e^{-as}F(s) = e^{-as}\mathcal{L}\big(f(s)\big)
$$
![[Pasted image 20250124050338.png]]
**NOTE:** It's $H$ in the exam instead of $u$
### Scaling $t$ variable (Scaling in time)
$$
\mathcal{L}\big(f(at)\big) = \frac{1}{a}F(\frac{s}{a})
$$
### Convolution
$$
\mathcal{L}\big((f * g)(t)\big) = F(s)G(s)
$$
## Inverse Laplace
### Partial Fraction Method
![[Pasted image 20250124051824.png]]
**NOTE:** Like you see when doing partial fractions you create constant terms for every term in the dominator but... if there is a term that is powered by 2 like $(s-1)^2$ you need to make constant terms for both $(s-1)$ and $(s-1)^2$
## Laplace Table
![[Pasted image 20250124052722.png]]