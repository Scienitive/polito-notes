## Q1
### Basic
$$
\vec{V} = \frac{\Delta x}{\Delta t}
$$
$$
\vec{a} = \frac{\Delta V}{\Delta t}
$$
Object 1's velocity with respect to Object 2:
$$
V_{rel} = V_1 - V_2
$$
### Energy and Force Formulas
Kinetic Energy Formula:
$$
KE = \frac{1}{2}mV^2
$$
Potential Energy Formula:
$$
PE = mgh
$$
Spring Potential Energy Formula:
$$
PE = \frac{1}{2}k (\Delta x)^2
$$
Spring Force Formula:
$$
F = -kx
$$
**NOTE:** Unit of $k$ is $N/m$

Friction Force Formula:
$$
f = \mu F_N
$$
Where $\mu$ is the coefficient of friction and $F_N$ is the normal force.
To calculate *energy loss due to friction* you need to calculate *work done* by the friction force.

Work Formula:
$$
W = Fd
$$
$$
W_{net} = \Delta KE
$$
### Kinematic Equations
$$
V_f = V_i + at
$$
$$
V_f^2 = V_i^2 + 2a \Delta x
$$
$$
\Delta x = V_it + \frac{1}{2}at^2
$$
$$
\Delta x = \frac{1}{2}(V_i + V_f)t
$$
### Trigonometry Notes
$$
sin(\theta) = \frac{\mathrm{opposite}}{\mathrm{hypotenuse}}
$$
$$
cos(\theta) = \frac{\mathrm{adjacent}}{\mathrm{hypotenuse}}
$$
$$
tan(\theta) = \frac{\mathrm{opposite}}{\mathrm{adjacent}}
$$
If you have the angles $A$, $B$ and $C$ for a triangle and one of the side's length. You can find the other side's length from this formula:
$$
\frac{sin(A)}{a} = \frac{sin(B)}{b} = \frac{sin(C)}{c}
$$
### Collisions
#### Elastic Collision
In elastic collision both momentum and kinetic energy is conserved.

Conservation of Momentum:
$$
m_{1}V_{1i} + m_{2}V_{2i} = m_{1}V_{1f} + m_{2}V_{2f}
$$
Conservation of Kinetic Energy:
$$
\frac{1}{2}m_1V_{1i}^2 + \frac{1}{2}m_2V_{2i}^2 = \frac{1}{2}m_1V_{1f}^2 + \frac{1}{2}m_2V_{2f}^2
$$
There is also this formula which is obtained by the above two formulas:
$$
V_{1i} + V_{1f} = V_{2i} + V_{2f}
$$
#### Inelastic Collision
In inelastic collision momentum is conserved but kinetic energy is not.

Conservation of Momentum:
$$
m_{1}V_{1i} + m_{2}V_{2i} = m_{1}V_{1f} + m_{2}V_{2f}
$$
#### Perfectly Inelastic Collision
In perfectly inelastic collision both objects are stuck together and act like one object.
### Inclined Plane
$sin(\theta)$ for *"horizontal"* force.
$cos(\theta)$ for *"vertical"* force.
### Impulse
Impulse $\to \Delta P$ so it's actually the change in *momentum*.
$$
J = \Delta P = F\Delta t
$$
### Gravitation
$$
F_g = G\frac{m_1m_2}{r^2}
$$
## Q2
Angular displacement $\to \Delta \theta$ (measured in radians)
Angular velocity $\to \omega = \frac{\Delta \theta}{\Delta t}$ (measured in radians/secs)
Angular acceleration $\to \alpha = \frac{\Delta \omega}{\Delta t}$ (measured in radians/secs^2)
**Their relation with regular motion variables:**
Arc length $\to S = \Delta \theta r$
Regular Speed $\to V = \omega r$
Tangential Acceleration $\to a_{tan} = \alpha r$
**NOTE:** You can find total acceleration like this:
$$
a_{tot}^2 = a_{tan}^2 + a_{c}^2
$$
Tangential acceleration is about object speeding up or down. Centripetal acceleration is about changing direction. And because they're both vectors you can find the total acceleration like above.
### Rotational Kinematic Equations
$$
\omega_f = \omega_i + \alpha t
$$
$$
\omega_f^2 = \omega_i^2 + 2\alpha \Delta \theta
$$
$$
\Delta \theta = \omega_it + \frac{1}{2} \alpha t^2
$$
$$
\Delta \theta = \frac{1}{2}(\omega_i + \omega_f)t
$$
### Radians to Degrees
$\pi \  rad = 180 \degree$
$1 \  rad = 180 \degree/\pi$
One full rotation means $2\pi$ radians.
### Center of Mass
$$
x_{cm} = \frac{m_1x_1 + m_2x_2 + m_3x_3 + \ ...}{m_1 + m_2 + m_3 + \ ...}
$$
### Torque
$$
\tau = F_{p}r
$$
Just like $F = ma$, we have something similar between Torque and angular acceleration:
$$
\tau = mr^2\alpha
$$
$$
\tau = I\alpha
$$
$I$ is *Moment of Inertia* or *Rotational Inertia* and is equal to $I = mr^2$ and it's units is $kg\cdot m^2$.
### Moment of Inertia
![[Pasted image 20240624192000.png]]
So based on above, we can say that $I$ increase when the mass is further concentrated from the rotation axis.

$$
I = I_{CM} + Md^2
$$
### Angular Momentum
$$
L = mVr
$$
$$
L = I\omega
$$
### Rotational Kinetic Energy
$$
K_{trans} = \frac{1}{2}mV^2
$$
$$
K_{rot} = \frac{1}{2}I\omega^2
$$
$$
K_{tot} = K_{trans} + K_{rot}
$$
### Rolling without slipping problems
$$
V_{cm} = \omega r
$$
### Power
$$
P = \tau \omega
$$
Above is true assuming *constant* torque.
### General
![[Pasted image 20240625013409.png]]
## Q3
### Ideal Gas Basics
$$
PV=nRT
$$
$$
R = 8.314\frac{J}{K \cdot mol}
$$
$$
R = 0.0821 \frac{L \cdot atm}{K \cdot mol}
$$
$$
\frac{P_1V_1}{T_1} = \frac{P_2V_2}{T_2}
$$
### PV Diagram
**NOTE:** Use $R = 8.314$ for all below formulas.
**For Monoatomic Gasses:**
$$
C_v = \frac{3}{2}R \ \ \ \ \ \ \ \ \ \ C_p = \frac{5}{2}R
$$
**For Diatomic (Biatomic) Gasses:**
$$
C_v = \frac{5}{2}R \ \ \ \ \ \ \ \ \ \ C_p = \frac{7}{2}R
$$
#### Isochoric Process $(\Delta V = 0)$
- $W = 0$
- $Q = nC_v \Delta T$
- $\frac{P_1}{T_1} = \frac{P_2}{T_2}$
- $\Delta U = Q$
- $\Delta S_{1,2} = nC_p \cdot ln(\frac{T_2}{T_1}) - nR \cdot ln(\frac{P_2}{P_1})$
- $\Delta S_{1,2} = nC_v \cdot ln(\frac{T_2}{T_1}) + nR \cdot ln(\frac{V_2}{V_1})$
- $\Delta S_{1,2} = nC_p \cdot ln(\frac{V_2}{V_1}) + nC_v \cdot ln(\frac{P_2}{P_1})$ **THIS MIGHT BE WRONG**
#### Isobaric Process $(\Delta P = 0)$
- $W = P \Delta V = nR \Delta T$
- $Q = nC_p \Delta T$
- $\frac{V_1}{T_1} = \frac{V_2}{T_2}$
- $\Delta U = nC_v \Delta T$
#### Isothermal Process $(\Delta T = 0)$
- $W = Q = nRT \cdot ln(\frac{V_f}{V_0}) = nRT \cdot ln(\frac{P_0}{P_f})$
- $P_1 \cdot V_1 = P_2 \cdot V_2$
- $\Delta U = 0$
#### Adiabatic Process
- $W = -nC_v \Delta T$
- $Q = 0$
- $\gamma = \frac{C_p}{C_v}$
- $P_1 \cdot V_1^\gamma = P_2 \cdot V_2^\gamma$
- $T_1 \cdot V_1^{(\gamma - 1)} = T_2 \cdot V_2^{(\gamma -1)}$
- $\Delta U = -W$
- $\Delta S = 0$ (if reversible)
#### Drawing PV Diagram
![[Pasted image 20240624025237.png]]
### Work
$$
W = P_{ext}\Delta V
$$
**NOTE:** Free expansion means $P_{ext} = 0$
### Thermal Efficiency
$$
e = 1 - \frac{|Q_{out}|}{Q_{in}} = \frac{W}{Q_{abs}}
$$
Every $Q$ value from processes that are negative belongs to $Q_{out}$
Every $Q$ value from processes that are positive belongs to $Q_{in}$
$$
Q_{tot} = W_{tot}
$$
Above is true because $\Delta U = Q - W$ and $\Delta U = 0$ for an engine cycle because $U$ is a state variable.

The Efficiency of an Otto Cycle:
$$
e = 1 - \bigg{(}\frac{V_A}{V_B}\bigg{)}^{(1-\gamma)}
$$
Where $\gamma = \frac{C_p}{C_v}$ and $\frac{V_A}{V_B}$ is the *compression ratio*

The Efficiency of a Carnot Cycle:
$$
e = \frac{T_H - T_L}{T_H} = 1 - \frac{T_L}{T_H}
$$
### Sign Conventions About $(\Delta U)$

|      $\Delta U$      |             Q            |             W             |
|:--------------------:|:------------------------:|:-------------------------:|
| $+$ if $T$ increases | $+$ if heat enters gas   | $+$ if gas is compressed  |
| $-$ if $T$ decreases | $-$ if heat exits gas    | $-$ if gas expands        |
| $0$ if $T$ constant  | $0$ if no heat exchanged | $0$ if volume is constant |

### Thermal Equilibrium
$$
Q = mC \Delta T
$$
Above equation becomes this one for ideal gasses:
$$
Q = nC_v \Delta T
$$
$$
Q = mL
$$
For thermal equilibrium questions you need to equalize both objects energy losses and gains.
#### Some Specific Heats and Latent Heats
##### Specific Heats
- $C_{ice} = 4186$ J/kg K
- $C_{water} = 2090$ J/kg K
- $C_{steam} = 2010$ J/kg K
##### Latent Heats of Condensation
- $L_{water} = 3.33\mathrm{x}10^5$ J/kg
### Refrigerator and Heat Pumps 
$Q_L$ is the amount of *heat flows out of refrigerator*.
**NOTE:** Always use $Q_L$ for the first calculation.

Coefficient of Performance (Refrigerator):
$$
COP = \frac{Q_L}{W} = \frac{Q_L}{Q_H-Q_L}
$$
The above is true because of $Q_H = Q_L + W$
For an *ideal* refrigerator it would be:
$$
COP = \frac{T_L}{T_H-T_L}
$$
For Heat Pumps Coefficient of Performance would be:
$$
COP = \frac{Q_H}{W}
$$
Third Law of Thermodynamics (This is true for reversible engines):
$$
\frac{Q_L}{Q_H} = \frac{T_L}{T_H}
$$
Power Formula:
$$
P = \frac{W}{\Delta t}
$$
### Entropy
$$
\Delta S = \frac{Q}{T}
$$
**NOTE:** For any *reversible* process $\Delta S_{tot} = 0$, if the process is *irreversible* $\Delta S_{tot} > 0$.
$$
\Delta S_{syst} = \frac{\Delta Q}{T}
$$
$$
\Delta S_{env} = \frac{-\Delta Q}{T}
$$
**NOTE:** Disorder $\to \Delta S > 0$, Order $\to \Delta S < 0$
### Units
- $S \to J/K$
- $W = Q = U \to J$
- $T \to K$
- $P \to atm \to Pa$ (Pressure)
- $V \to L \to m^3$
- $P \to W$ (Power to Watt)
#### Other Conversion Stuff
$1$ atm $=$ $101325$ Pa
$1$ $m^3$ $=$ $1000$ $dm^3$ $=$ $1000$ L
![[Pasted image 20240624113850.png]]