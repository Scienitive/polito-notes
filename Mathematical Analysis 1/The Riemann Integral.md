## Index
**Go Back To** [[!Mathematical Analysis 1]]
**Move Further To**
- [[Properties of Definite Integrals]]
- [[The Integral Mean Value Theorem]]
- [[Fundamental Theorem of Calculus]]
- [[Improper Integrals]]
## Step Functions
Intuitive idea of The Riemann Integrals is to approximate the are with the sum-of-rectangle areas of *upper* and *lower* **step functions**.
![[Pasted image 20231212212046.png]]
- Blue lines represent the upper step function.
- Red lines represent the lower step function.

**NOTE:** Step functions are constant in the interval where they look flat.
### Integral of a step function is:
$$
\sum_{i=1}^{n}c_i\Delta x_i
$$
- $\Delta x_i$ represents the $x_i - x_{i-1}$, which are the points where a step function line ends and another one starts. So basically $\Delta x_i$ represents the length of a step.
- $c_i$ represents the value of the step function when $x$ is between $x_i$ and $x_{i-1}$.
## Upper and Lower Riemann Sums
Let's define:
- $m_i$ as $\mathrm{inf}f(x)$ on the interval $I_i$ where this interval represents the width of one step function line.
- $M_i$ as $\mathrm{sup}f(x)$ on the interval $I_i$ again, where this interval represents the same thing.
Then:
### Lower Riemann Sum
$$
s(\mathcal{P}) = \sum_{i=1}^{n}m_i\Delta x_i
$$
### Upper Riemann Sum
$$
S(\mathcal{P}) = \sum_{i=1}^{n}M_i\Delta x_i
$$
![[Pasted image 20231212214416.png]]
Then we can say that $s(\mathcal{P}) \leq S(\mathcal{P}) \ \forall \mathcal{P}$
**NOTE:** $\mathcal{P}$ represents the partitions here. $\mathcal{P} = \{x_0, x_1, ..., x_n\}$ where $x_i$'s are all the points where the step lines end and start.

If we add another point to are partition:
$\mathcal{P}' = \mathcal{P} \cup \{x'\}$
Then we conclude this result:
$$
s(\mathcal{P}) \leq s(\mathcal{P}') \leq S(\mathcal{P}') \leq S(\mathcal{P})
$$
![[Pasted image 20231212215141.png]]
## Upper and Lower Integrals
Based on above information we can define these:
### Lower Integral
$$
\underline{\int_I}f = \underset{\mathcal{P}}{\mathrm{sup}}(s(\mathcal{P}))
$$
### Upper Integral
$$
\overline{\int_I}f = \underset{\mathcal{P}}{\mathrm{inf}}(S(\mathcal{P}))
$$
## The Riemann Integral
A function is (Riemann) Integrable if $\underline{\int} = \overline{\int}$ is true. If it's true:
$$
\int_a^bf(x)dx = \underline{\int}f = \overline{\int}f
$$
This is the integral of $f$ over $I = [a, b]$
## Theorem
$f$ is integrable on $I$ if and only if $\forall \epsilon > 0 \ \exists \mathcal{P}$:  $S(\mathcal{P}) - s(\mathcal{P}) < \epsilon$.
![[Pasted image 20231212221644.png]]
You can find more information about this theorem and it's proof on *lecture19.pdf*'s last sections.
