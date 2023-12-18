## Index
**Go Back To** [[!Chemistry]]
## Ideal Gas
### Important Formulas
- $P = \frac{F}{A}$
- $PV = nRT$
- If $n$ is constant: $\frac{P_1V_1}{T_1} = \frac{P_2V_2}{T_2}$
- If $P$ and $T$ constant: $\frac{V}{n} = V_n \ (\mathrm{molar \ volume}) = \mathrm{constant}$
- $n = \frac{m}{MM}$ where $m =$ mass of the gas, $MM =$ molar mass.
- $MM = m \cdot N_A$ where $m =$ mass of the particle.
- $\rho_{gas} = \frac{P \cdot MM}{RT}$, density of a gas formula.
- There are more formulas below...
### Important Constants
- Ideal Gas Constant: $R = 0.0821\frac{atm\cdot \ell}{mol \cdot K} = 8.314\frac{J}{mol \cdot K}$
- Avogadro's Number: $N_A = 6.022 \cdot 10^{23}$
### Properties of Gasses
- Gases have an indefinite shape.
- Gases have low densities.
- Gases can can be compressed.
- Gases can expand.
- Gases mix completely with other gases in the same container.
### Ideal Gas Definition
1) Gas particles have no volume.
2) There are no interactions among the particles. 
3) Collisions are elastic (no loss of energy).
4) Gas particles have random motions.
#### Ideal Gas Law
$$
PV = nRT
$$
**NOTE:** Ideal gas law is more accurate when $P \to 0$.
**NOTE:** When working with Ideal Gas Formula remember to use $K$ for $T$ instead of $\degree C$.
### Standard Conditions
1) **SATP:** $25 \degree C$ and $1$ bar.
2) **STP:** $0 \degree C$ and $1$ atm.
### More About Ideal Gasses
You can find total pressure and total volume like this:
$$
P_{tot} = P_1 + P_2 + P_3 + \ ...
$$
$$
V_{tot} = V_1 + V_2 + V_3 + \ ...
$$

Mole fraction:
$$
x_i = \frac{\mathrm{moles \ gas_i}}{\mathrm{total \ number \ of \ moles}}
$$
Volume percentage is simply mole fraction times 100:
$$
\%\mathrm{Volume} = x_i \cdot 100
$$

To find *Partial Pressure* and *Partial Volume* of a gas inside a mixture:
$$
P_i = x_i \cdot P_{tot}
$$
$$
V_i = x_i \cdot V_{tot}
$$
Density of a mixture:
$$
\rho_{mix} = \frac{P \cdot \overline{MM}}{RT}
$$
$\overline{MM}$ is average molar mass of a mixture and it can be found like:
$$
\overline{MM} = x_1 \cdot MM_1 + x_2 \cdot MM_2 + x_3 \cdot MM_3 + \ ...
$$
## Molecular Motion
### Effusion
Effusion is gas leaking from one space to another through a pinhole.
*Rate of effusion* $\propto \sqrt{\frac{T}{MM}} \Longrightarrow$ *Average speed* $\propto \sqrt{\frac{T}{MM}}$

*Speed of root mean square* is an important thing and can be found like this:
$$
V_{rms} = \sqrt{\frac{3RT}{MM}} = \sqrt{\frac{3k_BT}{m}}
$$
$k_B = \frac{R}{N_A}$ is the Boltzmann Constant.
### Speed Distribution of a Gas
![[Pasted image 20231217165528.png]]
![[Pasted image 20231217165617.png]]
### Average Kinetic Energy of a Gas
Average K.E. for 1 molecule:
$$
KE = \frac{1}{2}m(V_{rms})^2 = \frac{3}{2}k_BT
$$
*Average K.E for 1 mole*:
$$
\frac{3}{2}k_BT \cdot N_A = \frac{3}{2}RT
$$
**NOTE:** So, temperature is directly proportional to K.E. in ideal gasses.
## Real Gasses
When the pressure is high, ideal gas laws fails. That's why we need to use real gasses at those situations.
### Compression Factor
$$
Z = \frac{V_{real}}{V_{ideal}}
$$
![[Pasted image 20231217171045.png]]
### Real Gas Formula
$$
(P + \frac{an^2}{V^2}) \cdot (V - nb) = nRT
$$
$a$ and $b$ re two constants defined for each gas.
For an ideal gas both $a$ and $b$ values are $0$ and $Z = 1$.
$(P + \frac{an^2}{V^2})$ accounts for *attraction*.
$(V - nb)$ accounts for *repulsion*.
So when $a > b \to Z < 1$ and this means the attraction is strong.
When $a < b \to Z > 1$ and this means the repulsion is strong.