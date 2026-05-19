## Symbols
![[Pasted image 20260427205613.png]]

## Coulomb's Law
This formula gives the force between two charges.
$F$ applies to both charges. As $\vec{F}_{1,2}$ and $\vec{F}_{2,1}$
$\hat{a}$ is the unit vector and it helps us to determine the direction of the force
**NOTE:** You should study dot product, vector product and understanding direction.
$$
\vec{F}_{1,2} = k\frac{q_1 \cdot q_2}{r^2} \cdot \hat{a}_{1,2}
$$

## Electric Field
$\vec{F}$ here comes from the Coulomb's law.
So basically when you calculate the $\vec{F}$ and divide that to the charge that you want, you'll find the Electric Field value at that point.
$q$ and $Q$ are representing different charges in this formula.
$$
\vec{E} = \frac{\vec{F}}{q} = k\frac{Q}{r^2} \cdot \hat{a}
$$
So $\vec{E}$ represents the electrostatic force per unit charge.
And it's visualized as lines of forces.
It is the force exerted on a small, positive test charge $(q)$

## Electric Flux
Electric Flux is a *scalar* measure of the total Electric Field lines passing through a given surface, representing the *flow* of the electric field.
$$
\Phi_{E} = \int{\vec{E} \cdot d\vec{A}}
$$
For a uniform field (where electric field strength is equal at all points of the field) the formula simplifies to:
$$
\Phi_{E} = EA\mathrm{cos}(\theta)
$$
Where $\theta$ is the angle between $\vec{E}$ and $\vec{A}$ (normal of the surface)
![[Pasted image 20260501124939.png]]
### For Closed Surfaces (Gauss's Law #1)
For any closed surface we can say that:
$$
\Phi_{E} = \frac{Q}{\epsilon_0}
$$
Where $Q$ represents the total charge inside the closed surface.
So the full formula of Gauss's Law #1 is:
$$
\Phi_{E} = \oint{\vec{E} \cdot d\vec{A}} = \frac{Q}{\epsilon_0}
$$
#### Symmetries for solving problems (Finding Electric Field at a point)

##### Spherical Symmetry
![[Pasted image 20260501130450.png]]
Let's say we have a thin hollow sphere with uniformly distributed charge $Q$.
We can make two assumptions based on that:
**r < R**:
The electric field is 0 because we select a Gaussian surface as sphere which has radius $r$.
And because of:
$$
\Phi_{E} = \oint{\vec{E} \cdot d\vec{A}} = \frac{Q}{\epsilon_0}
$$
We find that $Q = 0$ so $\vec{E}$ must be also 0.

*r > R*:
Now again we select a Gaussian surface as sphere which has radius $r$. But this time since $r > R$, inside the Gaussian surface $Q \neq 0$.
That means Electric Field is not zero and it's equal to:
$$
\vec{E} = \frac{Q}{4 \pi r^2 \epsilon_0}
$$
This result is no different if instead of a hollow sphere which has uniformly distributed charge, we have a point charge equal to $Q$. The result would be the same.
![[Pasted image 20260501131436.png]]

##### Flat Horizontal Plane Symmetry(?)
$$
\vec{E} = \frac{\sigma}{2 \epsilon_0}
$$
Here the $\sigma$ represents the charge density which is: $\sigma = \frac{Q}{A}$
For this equation to be true, we need infinitely large plane with uniformly distributed charge density.
And from this equation what we get is that the distance doesn't matter. No matter how far you are from the plane the electric field is the same.
This last conclusion might be a bit counter-intuitive but the plane is infinitely large, that makes the difference.

## Electrostatic Potential Energy $\to U$
$$
U = k \frac{q_1 \cdot q_2}{r}
$$
Electrostatic Potential Energy is the amount of *work* needed to be done to keep $q_1$ and $q_2$ at $r$ distance.
Because $q_1$ and $q_2$ are charges they either attract or repel each other. So to keep them fixed at distance $r$ some work has to be done.
## Electrostatic Potential $\to V$
$$
V_p = k \frac{q}{r}
$$
Electrostatic Potential is pretty similar to Electrostatic Potential Energy.
We basically divide the Electrostatic Potential Energy with one of the charges.
And it defines *the work per unit charge* that needs to be done to go from $\infty \to p$
$p$ represents a point in space here.