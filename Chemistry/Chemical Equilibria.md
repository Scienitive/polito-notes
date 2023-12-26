## Index
**Go Back To** [[!Chemistry]]
## Definition
*Equilibrium* is a state in which there are no observable changes as time goes by.
$$
N_{2(g)} + 3H_{2(g)} \rightleftarrows 2NH_{3(g)}
$$
*Chemical Equilibrium* is achieved when:
- The rates of the forward and reverse reactions are equal.
- The concentrations of the reactants and products remain constant.
## Equilibrium Constant $(K)$
There are *two* types of equilibrium constants:
- $K_p \to$ Equilibrium constant used when equilibrium concentrations are expressed in *atmospheric pressure*.
- $K_c \to$ Equilibrium constant used when equilibrium concentrations are expressed in *molarity*.

Let's consider this reaction:
$$
A_{(g)} + 2B_{(g)} \rightleftarrows 3C_{(g)} + 4D_{(g)}
$$
### $K_p$
You use $K_p$ when you just deal with *gasses*.
$$
K_p = \frac{(P_C)^3 \cdot (P_D)^4}{(P_A)^1 \cdot (P_B)^2}
$$
- Pressures $(P)$ are referred to equilibrium.
- $K_p$ is constant at constant temperature.
- $K_p$ is unitless.
- Always $\frac{\mathrm{products}}{\mathrm{reactants}}$
### $K_c$
You use $K_c$ when you also deal with some substances that are aqueous solutions.
$$
K_c = \frac{[C]_{eq}^3 \cdot [D]_{eq}^4}{[A]_{eq}^1 \cdot [B]_{eq}^2}
$$
- Molar Concentrations $[\alpha]$ are referred to equilibrium.
- $K_c$ is constant at constant temperature.
- $K_c$ is unitless.
- Always $\frac{\mathrm{products}}{\mathrm{reactants}}$
### $K$ (more general version)
$$
K = \frac{(a_C)^3 \cdot (a_D)^4}{(a_A)^1 \cdot (a_B)^2}
$$
### Important Notes
![[Pasted image 20231226062515.png]]

**NOTE:** When dealing with substances that are in the form of *pure solid* or *pure liquid*, you can ignore them when calculating $K$:
![[Pasted image 20231226062917.png]]

**NOTE:** When a reaction involves *fully dissociated* ionic compounds in solution, the equilibrium constant should be written for the *net ionic equation*, by using the activity for each type of ion:
![[Pasted image 20231226063156.png]]
## The Thermodynamic Origin of Equilibrium Constants
$$
\Delta G = \sum \big(nG_{\mathrm{products}} - nG_{\mathrm{reactants}}\big)
$$
- $\Delta G$ refers to products and the reactants at a specified stage of the reaction, and reflects the *current* composition of the reaction mixture.
$$
\Delta G\degree = \sum \big(nG\degree_{\mathrm{products}} - nG\degree_{\mathrm{reactants}}\big)
$$
- $\Delta G\degree$ refers to products and the reactants in their standard states and can be calculated from the standard Gibbs free energies of formation.
![[Pasted image 20231226073435.png]]
### Reaction Quotient $(Q)$
Reaction quotient has the same formulas with $K$, but unlike $K$ the values don't have to be taken at *equilibrium*.
### $\Delta G_r$
$$
\Delta G_r = \Delta G_r\degree + RT\ \mathrm{ln}(Q)
$$
At *equilibrium*:
- $Q = K$
- $\Delta G_r = 0$
- $\Delta G_r\degree \neq 0$
- $\Delta G_r\degree = -RT\ \mathrm{ln}(Q) = -RT\ \mathrm{ln}(K)$
	- $\Delta G_r\degree < 0 \Rightarrow K > 1$, So this means *products* are favored at equilibrium.
	- $\Delta G_r\degree > 0 \Rightarrow K < 1$, So this means *reactants* are favored at equilibrium.
### The Extent of Reaction
![[Pasted image 20231226080324.png]]
### The Direction of Reaction
- $Q < K \to$ The reaction has a tendency to proceed towards products.
- $Q = K \to$ $\Delta G_r = 0$, so the reaction is at equilibrium.
- $Q > K \to$ The reverse reaction is spontaneous and the products tend to decompose into the reactants.
## Relating $K_p$ and $K_c$
$$
K_c = K_p \cdot \bigg(\frac{1}{RT}\bigg)^{\Delta n}
$$
This also mean when $\Delta n = 0 \to$ $K_c = K_p$
## The Response of Equilibria to Changes in Conditions
A shift in the equilibrium may be caused:
- By adding or removing substances.
- By a variation of $V$ and $P$.
- By a variation of $T$.
### Adding or Removing Substances
- If you add more reactants, then the reaction will favor products and vice versa...
- Also if you remove more reactants, then the reaction will favor reactants and vice versa...
### Variation of $V$ and $P$
- Increasing $P$ (which means also: decreasing $V$) $\to$ fewer gas moles
	- So the reaction will shift to the side with fewer gas moles.
- Increasing $V$ (which means also: decreasing $P$) $\to$ more gas moles
	- So the reaction will shift to the side with more gas moles.
 **NOTE:** If $\Delta n = 0$, increasing or decreasing $V$ or $P$ will have no effect at all.
### Variation of $T$
For *endothermic* reactions:
- $N_2O_4 + \mathrm{heat} \rightleftarrows 2NO_2$
- Increasing heat will favor products and decreasing it will favor reactants.
For *exothermic* reactions:
- $2NO_2 \rightleftarrows N_2O_4 + \mathrm{heat}$
- Increasing heat will favor reactants and decreasing it will favor products.
## Catalysts and Equilibrium
Adding a Catalyst:
- Does not change $K$.
- Does not shift the position of an equilibrium system.
- System will reach equilibrium sooner.
![[Pasted image 20231226084054.png]]