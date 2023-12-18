## Index
**Go Back To** [[!Chemistry]]
## System, States and Energy
- We define the *system* as the material or process we are studying the energy changes within.
- We define the *surroundings* as everything else in the universe.
![[Pasted image 20231217220917.png]]
## Work and Energy
Work = opposite force x distance moved
$$
W = F \cdot D
$$
The unit of $W$ is $J$ (joule) and $1J = 1kg \cdot \frac{m^2}{s^2}$

A system can do two kinds of work:
1) **Expansion Work:** A change in the volume of a system.
2) **Non-Expansion Work:** For example, a battery.

*Expansion Work* can be formulated like this:
$$
W = P\Delta V
$$
## Internal Energy
In thermodynamics, the total store of energy in a system is called its *internal energy* $U$.
$$
\Delta U = Q \pm W
$$
### Work
$W$ here, represents the energy transferred to a system by doing work.
- **When energy is transferred to a system as work**, the internal energy of the system increases and $W$ is *positive*.
- **When energy leaves the system as work**, the internal energy of the system decreases and $W$ is *negative*.

To calculate the work done by a gas that expands against a changing external pressure, we need to specify exactly how that pressure changes in the course of the expansion. In particular, we consider the very important case of *reversible* expansion of an ideal gas.
- A *reversible process* is one that can be reversed by an infinitely small change in a variable.
- An *irreversible process* is one where an infinitesimal change in a variable does not reverse the direction.
### Heat
Heat is the exchange of thermal energy between the system and surroundings (difference in temperature). And is represented with $Q$.
- Heat flows from matter with high temperature to matter with low temperature until both objects reach the same temperature.

The unit of $Q$ is also $J$. However it can also be represented with $\mathrm{cal}$.
- Originally, $1 \mathrm{cal}$ was the energy needed to raise the temperature of $1 g$ of water by $1 \degree C$
- $1 \mathrm{cal} = 4.184 J$

- If **energy leaves the system as heat**, the internal energy of the system decreases and $Q$ is *negative*.
- If **energy enters a system as heat**, the internal energy of the system increases and $Q$ is *positive*.
![[Pasted image 20231217222458.png]]
- A process that releases heat is an *exothermic* process (e.g. combustions).
- A process that absorbs heat is an *endothermic* process (e.g. vaporization).
#### Heat Capacity
When a system absorbs heat, its temperature increases the increase in temperature is directly proportional to the amount of heat absorbed.
The proportionality constant is called the *heat capacity* $C$
$$
C = \frac{Q}{\Delta T}
$$

The *specific heat capacity* is the amount of heat energy required to raise the temperature of one gram of a substance $1 \degree C$.
- $C_s$ units are $J/(g \cdot \degree C)$
The *molar heat capacity* is the amount of heat energy required to raise the temperature of one mole of a substance $1 \degree C$.
- $C_m$ units are $J/(mol \cdot \degree C)$
## State Functions
If *something* of a system is independent of the path by which the system achieved that state, we call it a *state function*.

**You need to know these:**
Some state functions are:
- Internal Energy
- Pressure
- Volume
- Enthalpy
- Entropy
- Gibbs Free Energy
*Remember!* These are not state functions:
- Work
- Heat
## PV Diagrams
![[Pasted image 20231217223839.png]]
PV diagrams stand for the Pressure and Volume diagrams.
- Area under the dark blue line gives you the *work done by the system*.
- Area under the light blue line gives you the *work done to the system*.
- So the orange area is *net work done by the system*.
## Enthalpy
The state function that allows us to keep track of energy changes at constant pressure is called the *enthalpy* and it's represented with $H$.
$$
H = U + PV
$$
$$
\Delta H = \Delta U + \Delta P \Delta V \Longrightarrow \Delta H = Q - P\Delta V + \Delta P \Delta V
$$
Based on this we can say that $- P \Delta V + \Delta P \Delta V$ will cancel out when the $P$ is constant.
So, in constant pressure, we'll end up with:
$$
\Delta H = Q
$$
**Important General Note:**
- When the *volume is constant* $\to \Delta U = Q$
- When the *pressure is constant* $\to \Delta H = Q$
### Endothermic and Exothermic
- $\Delta H > 0$: *Endothermic*
- $\Delta H < 0$: *Exothermic*
### Enthalpy of Physical Change
When a phase transition takes place at constant pressure, the heat transfer accompanying the phase change is equal to the change in enthalpy of the substance.
- At a given temperature, the vapor phase of a substance has a higher energy and therefore a higher enthalpy than the liquid phase. The difference in molar enthalpy between the vapor and the liquid states is called the *enthalpy of vaporization*:
	- $\Delta H_{vap} = H_m \mathrm{(vapor)} - H_m \mathrm{(liquid)}$
 - The molar enthalpy change that accompanies melting (fusion) is called the *enthalpy of fusion*:
	 - $\Delta H_{fus} = H_m \mathrm{(liquid)} - H_m \mathrm{(solid)}$
**NOTE:** Because the enthalpy is a state function enthalpy of freezing is equal to enthalpy of freezing and enthalpy of sublimation is equal to enthalpy of vaporization.
#### Possible Theory Question (Heating Curve of Water)
![[Drawing 2023-12-18 01.51.44.excalidraw]]
**NOTE:** When doing this on exam, you should draw the details just like this one.
### Heating Curves
![[Pasted image 20231217232517.png]]
 - In some cases boiling does not begin until a few degrees over the boiling point. Once boiling begins, the temperature falls back to that of the boiling point. This phenomenon is called *superheating*.
 - Similarly, when a sample is cooled, the temperature may fall below the freezing point briefly before freezing begins in a process called *supercooling*.
 ![[Pasted image 20231217232949.png]]
### Enthalpy of Reaction
**Watch this video:**
[This video explains everything](https://youtu.be/chXMpDwjBDk?si=tJc_a1df5NsWZi4W)
### The Relation Between $H$ and $U$
It is sometimes necessary to convert the measured value of $\Delta U$ into $\Delta H$.
$$
\Delta H = \Delta U + \Delta n_{gas}RT
$$
So, for reactions in which no gas is generated or consumed:
$$
\Delta n_{gas} = 0 \Longrightarrow \Delta H = \Delta U
$$
## Spontaneous Change
A *spontaneous change* is a change that has a tendency to occur without needing to be driven by an external influence.
![[Pasted image 20231217234607.png]]
**NOTE:** Spontaneous changes need not to be fast and in some cases must be initiated.
## Entropy and Disorder
Entropy is represented with $S$.
Second law of Thermodynamics is: The entropy of an isolated system increases in the course of any spontaneous change.

If the temperature is constant:
$$
\Delta S = \frac{Q}{T}
$$
To use $\Delta S = \frac{Q}{T}$ to calculate the entropy change for a substance undergoing a transition from one phase to another at its transition temperature, we need to note three facts:
1) At the transition temperature (such as the boiling point for vaporization), the temperature of the substance remains constant as heat is supplied.
2) At the temperature of a phase transition, the transfer of heat is reversible. So actually $Q$ in that formula stands for $Q_{rev}$.
3) Because the transition takes place at constant pressure (for instance, $1\mathrm{atm}$), the heat supplied is equal to the change in enthalpy of the substance.
If these are valid, we can also conclude:
$$
\Delta S_{vap} = \frac{\Delta H_{vap}}{T_b}
$$
$$
\Delta S_{fus} = \frac{\Delta H_{fus}}{T_f}
$$ ^18ca8c
### Third Law of Thermodynamics
The entropies of all perfect crystals approach zero as the absolute temperature approaches zero.
![[Pasted image 20231218010912.png]]
### Standard Molar Entropies
If a phase transition takes place between T =0 and the temperature of interest, then we also have to include in S(T) the corresponding entropy of transition by using [[Thermodynamics#^18ca8c|these]].
![[Pasted image 20231218011230.png]]
### Entropy Changes
**NOTE:** Entropy increases as you go to $\mathrm{solid} \to \mathrm{liquid} \to \mathrm{gas}$. 
#### Global Changes
$$
\Delta S_{tot} = \Delta S + \Delta S_{surr}
$$
- Both the entropy change of the system and that of the surroundings affect the direction of a reaction, because both contribute to the entropy of the universe.
- The process is *spontaneous* only if the total change in entropy, the sum of the changes in the system and the surroundings, *is positive*.
#### Changes in System
Entropy changes for a reaction (system) can be estimated in a manner analogous to that by which $\Delta H$ is estimated:
![[Pasted image 20231218011834.png]]
#### Changes in Surroundings
Heat that flows into or out of the system changes the entropy of the surroundings:
$$
\Delta S_{surr} \propto -Q_{sys}
$$
For an *isothermal* process:
$$
\Delta S_{surr} = -\frac{Q_{sys}}{T}
$$
**Mind the sign!** The heat that leaves the system enters the surroundings.
So at constant pressure and temperature we can conclude:
$$
\Delta S_{surr} = -\frac{\Delta H}{T} 
$$
### Spontaneity of a Reaction
To use the entropy to judge the direction of spontaneous change, we must consider the change $\Delta S_{tot}$
- $\Delta S_{tot} > 0 \to$ The process is *spontaneous*.
- $\Delta S_{tot} < 0 \to$ The *reverse* process is *spontaneous*.
- $\Delta S_{tot} = 0 \to$ The process has no tendency to proceed in either direction *(equilibrium)*.
![[Pasted image 20231218012631.png]]
![[Pasted image 20231218012650.png]]
![[Pasted image 20231218012718.png]]
## Gibbs Free Energy
Gibbs free energy is represented with $G$.
$$
G = H - TS
$$
For a process that is occurring in a *constant temperature*:
$$
\Delta G = \Delta H - T \Delta S
$$
![[Pasted image 20231218014245.png]]
![[Pasted image 20231218014300.png]]
### Gibbs Free Energy of a Reaction
Gibbs Free Energy changes for a reaction (system) can be estimated in a manner analogous to that by which $\Delta H$ and $\Delta S$ is estimated:
![[Pasted image 20231218014449.png]]
An example:
![[Pasted image 20231218014505.png]]
### The Standard Gibbs Free Energy
$\Delta G \degree \to$ The standard Gibbs free energy of reaction is the difference in Gibbs free energy between the *pure products* and the *pure reactants*.
### Gibbs Free Energy and Spontaneity
#### This is also a Possible Theory Question
![[Pasted image 20231218014849.png]]