## Power Series
![[Pasted image 20250128203738.png]]
## Fourier Series
$$
\int_{0}^{2\pi}sin(nx)dx = 0
$$
$$
\int_{0}^{2\pi}cos(nx)dx = 0 \ \ \ \ \mathrm{for} \ n \neq 0
$$
$$
\int_{0}^{2\pi}sin(nx)cos(mx)dx = 0 \ \ \ \ \mathrm{for \ any} \ n,m
$$

$$
\int_{0}^{2\pi}sin(nx)sin(mx)dx =
\begin{bmatrix}
0 \to n \neq m \\
\pi \to n = m \neq 0
\end{bmatrix}
$$
$$
\int_{0}^{2\pi}cos(nx)cos(mx)dx =
\begin{bmatrix}
0 \to n \neq m \\
\pi \to n = m \neq 0
\end{bmatrix}
$$
### General Formula
$$
S_f(x) = a_0 + \sum_{n = 1}^{\infty}a_ncos(\frac{n \pi x}{T/2}) + \sum_{n = 1}^{\infty}b_nsin(\frac{n \pi x}{T/2})
$$
### First Term
AKA average value of $f$ over $[0, 2\pi]$
$$
a_0 = \frac{1}{2\pi}\int_{0}^{2\pi}f(x)dx
$$
For $T$-periodic functions we can generalize it to:
$$
a_0 = \frac{1}{T}\int_{-T/2}^{T/2}f(x)dx
$$
### $cos$ Terms
$$
a_n = \frac{1}{\pi}\int_{0}^{2\pi}f(x)cos(nx)dx
$$
For $T$-periodic functions we can generalize it to:
$$
a_n = \frac{2}{T}\int_{-T/2}^{T/2}f(x)cos(\frac{n \pi x}{T/2})dx
$$
### $sin$ Terms
$$
b_n = \frac{1}{\pi}\int_{0}^{2\pi}f(x)sin(nx)dx
$$
For $T$-periodic functions we can generalize it to:
$$
b_n = \frac{2}{T}\int_{-T/2}^{T/2}f(x)sin(\frac{n \pi x}{T/2})dx
$$
### Fourier Convergence Property
$$
S_f(x) = \frac{f(x^-) + f(x^+)}{2}
$$
### Symmetry Properties
![[Pasted image 20250129022258.png]]