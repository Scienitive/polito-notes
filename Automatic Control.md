## Defining A,B,C,D matrixes
Let's go with an example:
$$
\dot{x}(t) = \begin{bmatrix} 0 & 1 \\ -0.2 & -0.5 \end{bmatrix}x(t) + \begin{bmatrix} 0 \\ 1 \end{bmatrix}u(t)
$$
$$
y(t) = \begin{bmatrix} 1 & 0 \end{bmatrix}x(t)
$$
- **$A$ (System Matrix):** $\begin{bmatrix} 0 & 1 \\ -0.2 & -0.5 \end{bmatrix}$. This dictates how the system behaves on its own, without any outside input.
- **$B$ (Input Matrix):** $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$. This dictates how your input $u(t)$ pushes and pulls on the system's internal states.
- **$C$ (Output Matrix):** $\begin{bmatrix} 1 & 0 \end{bmatrix}$. This dictates which internal states actually show up in your final output $y(t)$.
- **$D$ (Feedthrough Matrix):** **$0$**. Look at your output equation for $y(t)$. Notice there is no $u(t)$ term at the end of it? In most physical systems, the input doesn't instantly bypass the physics to become the output, so $D$ is almost always a zero (or a zero matrix).
## What are poles, and why are they Complex Conjugate
In control theory, **poles** (or eigenvalues) act like the DNA of your system. They completely dictate how the system behaves over time.
- **The Real Part** determines if the system decays to zero (stable, negative real part) or explodes to infinity (unstable, positive real part).
- **The Imaginary Part** determines if the system oscillates (bounces up and down) before settling.
### More on Stability (CONTINUOUS-TIME systems only)
To calculate stability you do:
```matlab
A = [your matrix]
disp(eig(A))
```
This gives you the pole values of the system, it can have multiple values and they have real part and imaginary part.
For stability **real part** is the important section.
The rule is (you check them from top to bottom):
- If you have *even one* pole with positive real part (Real > 0), the system is **UNSTABLE**
- If you have *repeated poles* with 0 real parts (poles need to be exactly same, including imaginary parts), the system is also **UNSTABLE**
- If you have *even one* pole with 0 real part (Real = 0), the system is **MARGINALLY STABLE** -> **NOT ASYMPTOTICALLY STABLE**
- If all the poles have negative real parts (Real < 0), the system is **ASYMPTOTICALLY STABLE**
### Complex Conjugate Pole Calculation Formula
$$
p_{1,2} = -\zeta\omega_n \pm j\omega_n\sqrt{1-\zeta^2}
$$

## The Trap: Mixing up $y(t)$ with $y_{ss}(t)$
There is a massive difference on your exam between asking for the **"Output Response" $y(t)$** and the **"Steady-State Response" $y_{ss}(t)$**.

**1. When the system is STABLE:**
- **$y(t)$ (Total Response):** You can calculate it. It will have a transient part that decays to zero ($e^{-2t}$) and a steady-state part.
- **$y_{ss}(t)$ (Steady-State):** You can calculate it easily using shortcuts (like plugging $s = j\omega$ into the transfer function, or using the Final Value Theorem).

**2. When the system is UNSTABLE (like our system in Q3 with the $+4$ pole):**
- **$y(t)$ (Total Response):** You can _still_ calculate it! It just means the equation will have an exploding term in it (like the $e^{4t}$ we found). The math still works perfectly to tell you exactly _how fast_ it explodes.
- **$y_{ss}(t)$ (Steady-State):** **This cannot be computed.** If a system explodes to infinity, it never settles down. Therefore, "steady-state" does not physically exist. If you try to use the Final Value Theorem on an unstable system, it will give you a fake, wrong number.

# Continuous-Time LTI Systems: Boundedness & Eigenvalue Relationships

## 1. Bounded vs. Unbounded Responses

> **Definition:** A response $y(t)$ or $x(t)$ is **bounded** if its absolute value never exceeds a finite limit as time approaches infinity ($t \to \infty$). If the mathematical function explodes to $\pm \infty$, it is **unbounded**.

To calculate and determine boundedness, you must analyze both the **Free Response** (natural system behavior) and the **Forced Response** (reaction to the input).
### Step 1: Check the System's Natural Stability (Free Response)
The natural bounds of the system are determined entirely by the real parts of the eigenvalues of matrix $A$.

- **Asymptotically Stable (All Real Parts < 0):** The free response will naturally decay to **0**. (Always Bounded).
- **Marginally Stable (Distinct Real Parts = 0):** The free response will oscillate between fixed limits forever. (Bounded).
- **Unstable (Any Real Part > 0 or Repeated Real Parts = 0):** The free response explodes exponentially or linearly. (Unbounded).
### Step 2: Check the Input (Forced Response)
Even if a system is naturally stable, a bad input can break it. You must look at the input function $u(t)$ and the system's poles.

- **BIBO Rule (Bounded-Input, Bounded-Output):** If the system is asymptotically stable, **any** bounded input (like a step function or a sine wave) will guarantee a bounded output.
- **The Unbounded Input:** If your input is unbounded (e.g., a ramp $u(t) = t$), your output will almost always be unbounded, regardless of stability.
- **The Resonance Trap (Critical Exam Trap):** If the system is marginally stable (contains poles at $\pm j\omega$) and the input is a sine wave with the **exact same frequency** (e.g., $u(t) = \sin(\omega t)$), they will resonate. The math creates a $t$ multiplier: $t\sin(\omega t)$. The output wave will grow larger forever and is **Unbounded**.
## 2. The Relationship Between Eigenvalues and Output Expressions
The eigenvalues ($\lambda$) of the state matrix $A$ are the **poles** of the system. They act as the system's mathematical DNA, strictly dictating the exact shape of the time-domain equations $x(t)$ and $y(t)$.

Every eigenvalue has the general complex form:
$$\lambda = \sigma \pm j\omega$$
Where **$\sigma$** is the Real Part (friction/growth) and **$\omega$** is the Imaginary Part (oscillation frequency).
### How Eigenvalues Translate to Time-Domain Math

| **Eigenvalue Type (λ)**                                  | **Mathematical Output Component**   | **Physical Behavior**                        |
| -------------------------------------------------------- | ----------------------------------- | -------------------------------------------- |
| **Real, Negative** ($\sigma < 0, \omega = 0$)            | $e^{\sigma t}$                      | Exponential decay toward **0**.              |
| **Real, Positive** ($\sigma > 0, \omega = 0$)            | $e^{\sigma t}$                      | Exponential explosion to $\infty$.           |
| **Complex, Negative Real** ($\sigma < 0, \omega \neq 0$) | $e^{\sigma t}\cos(\omega t + \phi)$ | Oscillating wave that shrinks to **0**.      |
| **Complex, Positive Real** ($\sigma > 0, \omega \neq 0$) | $e^{\sigma t}\cos(\omega t + \phi)$ | Oscillating wave that violently expands.     |
| **Purely Imaginary** ($\sigma = 0, \omega \neq 0$)       | $\cos(\omega t + \phi)$             | Pure, sustained oscillation forever.         |
| **Repeated Roots** (e.g., double pole at $\sigma$)       | $t e^{\sigma t}$                    | Adds a $t$ multiplier to the standard shape. |
### The "Speed" of the System
- **Dominant Poles:** Eigenvalues closest to the imaginary axis (closest to **0** on the real line) are the "slowest" to decay. They will dominate the final shape of the output equation because the faster exponentials (e.g., $e^{-10t}$) will die out almost instantly compared to the slow ones (e.g., $e^{-0.5t}$).

## BIBO Stability Calculation
**IMPORTANT SHORTCUT:** If an LTI system is internally asymptotically stable, it is automatically *BIBO stable*.
**IMPORTANT SHORTCUT 2:** If *ALL* eigenvalues of matrix $A$ are unstable, you can instantly say that it's also *BIBO unstable*.
```matlab
syms s
I = eye(2);

% Build the Transfer Function exactly as the formula dictates
H_raw = C * inv(s*I - A) * B + D;

% simplify() forces MATLAB to cancel out common terms in the fraction!
H_simplified = simplify(H_raw);

% Find the poles of H(s) by finding the roots of its denominator
[num, den] = numden(H_simplified);
poles_H = solve(den == 0, s);

disp(vpa(poles_H, 4));
```
With that code you can see the poles of the transfer function and from there you'll conclude the BIBO stability according to this:
- All surviving poles are *negative* (Real < 0) $\to$ **BIBO STABLE**
- Even one surviving pole is *positive* (Real > 0) $\to$ **BIBO UNSTABLE**
- Even one surviving pole is *zero* (Real = 0) $\to$ **BIBO UNSTABLE**

**NOTE:** In the code we need to use vpa() function when displaying if we encounter root(...) kind of response from the MATLAB.

### Descartes' Rule of Signs (Stability Cheat Sheet)
**Goal:** Instantly check BIBO stability without calculating poles.

**The Rule:** Look at the transfer function's denominator polynomial, ordered from highest to lowest power:

$P(s) = a_n s^n + a_{n-1} s^{n-1} + \dots + a_0$

#### 1. The Quick Checks
- **Missing $s$ terms?** (e.g., $s^3 + 4s + 2$) $\rightarrow$ Automatically **Unstable** (or marginally stable).
- **No missing terms?** Read the coefficients from left to right and count the sign changes (+ to -, or - to +).
#### 2. The Verdict
- **0 Sign Changes** (all coefficients share the same sign) $\rightarrow$ $0$ positive poles $\rightarrow$ **BIBO Stable** (guaranteed for 1st/2nd order).
- **$\ge 1$ Sign Change** $\rightarrow$ At least 1 positive pole $\rightarrow$ **BIBO Unstable**.
## Time Constant $(\tau)$
The Formula:
$$
\tau = \frac{1}{|Re(p)|}
$$
Where $p \to$ represents the eigenvalues of our system.
We can have multiple time constants for multiple eigenvalues!

Let's say:
$\lambda_1 = -1$ and $\lambda_2 = -10$

This will give:
$\tau_1 =$ 1 second, and $\tau_2 =$ 0.1 second
So, the second part of the system ($e^{-10t}$) decays incredibly fast. It is basically gone in half a second. But the first part ($e^{-1t}$) is slow and sluggish. It will take roughly 5 seconds to completely disappear.

**IMPORTANT:** If a question asks "what is the time constant of the overall system," you always pick the **largest $\tau$** (which corresponds to the eigenvalue closest to the imaginary zero-line).

##  Classifying Natural Modes: The Complete "Menu"
When a professor asks you to "classify the natural modes," they are asking: _"Based on the eigenvalues, what is the fundamental shape of the math equation if the system is left alone?"_
Here are all the possible modes you can encounter, based strictly on the eigenvalue ($\lambda = \sigma \pm j\omega$):

**A. The Convergent Modes (Stable - Real Part is Negative)**
- **Exponentially Convergent:** Real pole ($\lambda = -2$). Math shape: $e^{-2t}$. (Slowly slides to zero).
- **Exponentially Convergent Oscillating:** Complex pole ($\lambda = -2 \pm 3j$). Math shape: $e^{-2t}\cos(3t)$. (Bounces, but shrinks to zero).

**B. The Divergent Modes (Unstable - Real Part is Positive)**
- **Exponentially Divergent:** Real pole ($\lambda = +2$). Math shape: $e^{2t}$. (Explodes to infinity).
- **Exponentially Divergent Oscillating:** Complex pole ($\lambda = +2 \pm 3j$). Math shape: $e^{2t}\cos(3t)$. (Bounces, expanding to infinity).

**C. The Bounded Modes (Marginally Stable - Real Part is exactly 0)**
- **Bounded (Constant):** A single pole exactly at zero ($\lambda = 0$). Math shape: $1$. (Stays perfectly flat).
- **Bounded (Oscillating):** Distinct purely imaginary poles ($\lambda = \pm 3j$). Math shape: $\cos(3t)$. (A pure sine wave that bounces forever).
- **Linearly Divergent:** Repeated poles on the zero line (e.g., two poles at exactly $0$). Math shape: $t$. (Marches upward to infinity like a ramp).

**IMPORTANT:** You need to answer for each eigenvalue separately for this one. But $\pm j$ ones are counted as 1.
So if you have $1 + 2j$ and $1 - 2j$, this counts as one, and it's *exponentially divergent (oscillating)*.

**NOTE:** If you have *linearly divergent* mode, that means you have two poles of 0. However when writing down the modes you should now that one of them counts for *Bounded* and the other one counts as *linearly divergent*. So you get both of them at the same time.
## Calculating Steady-State Response $y_{ss}(t)$ in the presence of an input
We're gonna do this with an example:
$$
H(s) = \frac{1}{s^3 + 2s^2 + 5.25s + 4.25}
$$
$$
u(t) = (2 + 3sin(0.1t))\epsilon(t)
$$
These are our transfer function and input
#### Step 1: Check BIBO Stability
You have more information on how to check this here. The important part is that: To have a Steady-State response you *must* have your system to be *BIBO Stable*. Otherwise the steady-state response doesn't exist. Even marginally stable doesn't cut it.
#### Step 2: The Matlab Code - Finding $y(t)$
```matlab
syms s t;

H_s = 1 / (s^3 + 2*s^2 + 5.25*s + 4.25);
u_t = (3*sin(0.1*t)+2);

U_s = laplace(u_t, t, s);
Y_s = H_s * U_s;
y_t = ilaplace(Y_s, s, t);

disp(vpa(y_t, 4));
```
With a setup like this one you can calculate $y(t)$, however we don't want $y(t)$ we want $y_{ss}(t)$ so we need to do some extra things.
**NOTE:** Using vpa() really helps here
#### Step 3: Visual Deletion
You'll have an output like this from the code above:

0.6985sin(0.1t) - 0.08653cos(0.1t) - *0.4007exp(-1.0t)* + *0.01664exp(-0.5t)(cos(2.0t) - 13.89sin(2.0t))* + 0.4706

This is very ugly but you have to eliminate some terms here.
Terms that have $exp(-t...)$ are the terms that you can eliminate completely.
I highlighted them here.

So you'll end up with something like this:
$$
y_{ss}(t) = 0.6985\sin(0.1t) - 0.0865\cos(0.1t) + 0.4706
$$
- $0.4706$ is your *DC Flat Line* component.
- And the other part is *AC Sine Wave* component.
#### Step 4: Rebuild The Sine Wave
As you see, you have two functions in your sinusoidal AC part. You can just have one there. For that you need to calculate some little things:
$$
R = \sqrt{A^2 + B^2}
$$
$A$ and $B$ representing the amplitudes of your sinusoidal waves. $A = 0.6985$ and $B = -0.0865$.
There you'll have your *amplitude*.

You also need to calculate the *the phase shift* and you do that by:
```matlab
phi = atan2(B, A);
```

The *frequency* $0.1t$ part, you just copy it from the input at the beginning $u(t)$.

Now you have your steady-state response:
$$
y_{ss}(t) = (0.7038\sin(0.1t - 0.1232) + 0.4706)\epsilon(t)
$$
### Handling Multiple Frequencies in $y(t)$
If you feed a system a crazy input like $u(t) = 3\sin(0.1t) + 5\sin(2.0t) + 2$, your output $y_{ss}(t)$ will absolutely contain multiple sine and cosine terms with different frequencies.

Here is the golden rule for dealing with them: **Linear systems never mix frequencies.** Because of the principle of **Superposition**, every frequency acts like it is in its own isolated universe. You do not combine them into one massive wave. Instead, you just repeat **Step 4** separately for each frequency group.

Here is exactly how you handle it:
**1. Group by Frequency**
Sort your messy output into distinct buckets based on the number next to $t$.
- **Bucket 1 (DC):** $0.4706$
- **Bucket 2 ($\omega = 0.1$):** $0.6985\sin(0.1t) - 0.0865\cos(0.1t)$
- **Bucket 3 ($\omega = 2.0$):** $1.2\sin(2.0t) + 0.5\cos(2.0t)$

**2. Rebuild Each Bucket Separately**
Apply your $R$ and $\phi$ formulas only to the numbers inside that specific bucket.
- **For $\omega = 0.1$:** Calculate $R_1$ and $\phi_1$ using $A = 0.6985$ and $B = -0.0865$.
- **For $\omega = 2.0$:** Calculate $R_2$ and $\phi_2$ using $A = 1.2$ and $B = 0.5$.

**3. Add Them All Together**
Your final steady-state response is just a chain of the individual, rebuilt waves added to the DC constant.
$$y_{ss}(t) = R_1\sin(0.1t + \phi_1) + R_2\sin(2.0t + \phi_2) + \text{DC}$$
You just treat it like two smaller, easier problems stacked on top of each other!
## Calculating Maximum Input Amplitude $\bar{u}$ for a Bounded Output $|y_{ss}(t)|$
We are going to do this with an example:
$$H(s) = \frac{1}{s^3 + 2s^2 + 5.25s + 4.25}$$
$$u(t) = \bar{u}\sin(3t)\epsilon(t)$$
**The Constraint:** We need the steady-state output amplitude to be less than or equal to 1, written mathematically as: $|y_{ss}(t)| \le 1$
### Step 1: Check BIBO Stability
Just like finding the standard steady-state response, **you must prove the system is BIBO Stable first**. If the system is unstable, the output explodes to infinity, meaning it is impossible to bound the output to $\le 1$. If it is unstable, the answer is just "Impossible."
### Step 2: The Core Rule of Frequency Response
You do not need to calculate the massive time-domain equation $y(t)$ for this. You only need to know how the system scales the input wave.

**The Golden Rule:** The amplitude of the output wave is exactly equal to the amplitude of the input wave multiplied by the magnitude of the transfer function at that specific frequency.

$$\text{Output Amplitude} = \text{Input Amplitude} \times |H(j\omega)|$$
Plugging in our variables:
$1 \ge \bar{u} \times |H(j3)|$

So to find the maximum $\bar{u}$, we just isolate it:
$\bar{u} \le \frac{1}{|H(j3)|}$
### Step 3: The MATLAB Code - Finding $|H(j\omega)|$
We use the Control System Toolbox (`tf`) and the evaluation function (`evalfr`) to bypass the Laplace algebra completely.

```matlab
% 1. Define the transfer function using tf (NOT syms!)
s = tf('s');
H = 1 / (s^3 + 2*s^2 + 5.25*s + 4.25);

% 2. Define the frequency from your input u(t)
% Our input is sin(3t), so omega is 3
omega = 3;

% 3. Evaluate the transfer function at s = j*omega
H_evaluated = evalfr(H, 1j * omega);

% 4. Find the magnitude (absolute value) of that complex result
mag = abs(H_evaluated);

% 5. Calculate the maximum u_bar
u_bar_max = 1 / mag;

disp('The maximum input amplitude u_bar is:');
disp(u_bar_max);
```
### Step 4: The Final Calculation
If you look at the intermediate steps MATLAB takes behind the scenes:
1. It calculates the magnitude: $|H(j3)| = 0.05628$
2. It solves the inequality: $\bar{u} \le \frac{1}{0.05628}$
**Final Answer:** $\bar{u} \le 17.7658$
## Analyzing Step Responses ($\zeta$, $\omega_n$, $\tau$, & Metrics)
We use this for analyzing transient behavior, particularly for 2nd-order prototypes:
$$H(s) = K\frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}$$
- **$\omega_n$**: Natural Frequency (Speed of the system).
- **$\zeta$**: Damping Ratio (Friction of the system).
### Step 1: Fast Parameter Extraction & The Dominant Pole
If you already have the transfer function, do not do manual algebra. Use MATLAB's `damp()` command to find the system's "DNA".

```matlab
s = tf('s');
H = 10 / (s^2 + 1.6*s + 4);

% Prints a table of Poles, Damping (zeta), and Frequency (omega_n)
damp(H);
```

**Calculating the Time Constant ($\tau$):**
The formula for any individual pole is $\tau = \frac{1}{|Re(p)|}$.
- **The Dominant Pole Rule:** If a system has multiple poles (e.g., $\lambda_1 = -1$ and $\lambda_2 = -10$), they will have different time constants ($\tau_1 = 1$s, $\tau_2 = 0.1$s).
- The pole with the **largest $\tau$** (closest to the imaginary zero-line) is the **Dominant Pole**. It decays the slowest and completely dictates the overall settling time of the system.

```matlab
% How to extract the overall system tau in MATLAB:
p = pole(H);

% Assuming p is sorted, find the real part closest to 0
dominant_sigma = min(abs(real(p))); 
system_tau = 1 / dominant_sigma;
```
### Step 2: The `stepinfo` Override Trick
To find transient metrics (Rise Time, Peak Time, Overshoot, Settling Time), use `stepinfo()`.
**CRITICAL EXAM TRAP:** By default, MATLAB calculates Settling Time ($t_s$) using a $2\%$ error band. If a question asks for a $5\%$ band, you **must** override the threshold.

```matlab
% Standard 2% Settling Time
metrics_standard = stepinfo(H);

% Override for 5% Settling Time
metrics_override = stepinfo(H, 'SettlingTimeThreshold', 0.05);

% Extract the exact numbers:
max_overshoot = metrics_override.Overshoot;
peak_time = metrics_override.PeakTime;
settling_time = metrics_override.SettlingTime;
```
### Step 3: Reverse Engineering (The "Design" Formulas)
If you are given a graph or asked to design a controller to meet specific requirements, you must calculate $\zeta$ and $\omega_n$ manually from the transient metrics.

**0. DC Gain ($K$)**
- *What it is:* The "Static Multiplier" of the system. It dictates the final resting height of the output after all transients die.
- *Formula:* $K = H(0)$
- *Reverse Engineering:* If you know the final steady-state value of the graph ($y_\infty$) and the amplitude of the step input ($U$): $$K = \frac{y_\infty}{U}$$
**1. Maximum Overshoot ($\hat{s}$)** $\to$ Given in PDF
- _Formula:_ $\hat{s} = e^{-\frac{\pi\zeta}{\sqrt{1-\zeta^2}}}$
- _Practical translation:_ Overshoot is strictly controlled by $\zeta$. Lower $\zeta \rightarrow$ higher overshoot.

**2. Settling Time ($t_s$)** $\to$ Given in PDF
- _For 5% Band:_ $t_{s, 5\%} \approx \frac{3}{\zeta\omega_n}$
- _For 2% Band:_ $t_{s, 2\%} \approx \frac{4}{\zeta\omega_n}$
- _Note:_ The denominator ($\zeta\omega_n$) is exactly the real part of your dominant complex pole!

**3. Peak Time ($t_p$)**
- _Formula:_ $t_p = \frac{\pi}{\omega_n\sqrt{1-\zeta^2}}$

**4. Steady-State Value ($y_\infty$)**
- _Formula:_ $y_\infty = \text{Input Amplitude} \times \text{dcgain}(H)$
## State-Space Matrices: Open-Loop vs. Closed-Loop
### 1. The Open-Loop System (Natural Physics)
This represents the raw, uncontrolled machine. Its stability is entirely dictated by its natural poles (the eigenvalues of $A$).
- **Equation:** $\dot{x} = Ax + Bu$ and $y = Cx + Du$

- **$A$ (System Matrix):** The natural physics/DNA. Determines the "free response."
- **$B$ (Input Matrix):** The actuators. Maps your raw input $u(t)$ into physical state changes.
- **$C$ (Output Matrix):** The sensors. Maps the internal states $x(t)$ to the measurable output $y(t)$.
- **$D$ (Feedthrough Matrix):** Direct connection from input to output. Almost always $0$ in standard physical systems.
### 2. The Controller (The Autopilot)
To change how the system behaves, we apply a state-feedback controller:
- **Equation:** $u = -Kx + Nr$

- **$K$ (Feedback Matrix):** The pole-placer. It constantly reads the states ($x$) and applies counter-forces to stabilize the system.
- **$N$ (Feedforward Gain):** The volume knob. Moving poles with $K$ ruins the steady-state gain. $N$ pre-scales the reference input ($r$) to guarantee the final output perfectly hits the target (usually unitary DC-gain).
### 3. The Closed-Loop System (The Hacked Physics)
When we plug the controller equation into the open-loop equation, we permanently rewrite the system's physics.
- **Equation:** $\dot{x} = (A - BK)x + BNr$

- **$A_{cl} = (A - BK)$**: The new system matrix. Its eigenvalues are your strictly controlled, desired closed-loop poles.
- **$B_{cl} = (BN)$**: The new input matrix. It scales the reference signal $r(t)$ by your gain $N$.
- **$C_{cl} = C$**: Unchanged (you didn't change the physical sensors).
- **$D_{cl} = D$**: Unchanged (still usually $0$).
### 4. The State-Space to Laplace Bridge
If you need to calculate the standard transfer function $H(s)$ of your brand-new closed-loop system to find the time-domain equation $y(t)$, use the Resolvent Matrix formula:
$$H_{cl}(s) = C(sI - A_{cl})^{-1} B_{cl}$$
## State Feedback Controller Design (Pole Placement)
**Goal:** Design a controller $u(t) = -Kx(t) + Nr(t)$ to force an open-loop system to meet strict transient performance requirements.
### Step 1: Translate Requirements to System DNA ($\zeta$ and $\omega_n$)
You must convert physical limits into the mathematical parameters $\zeta$ (friction) and $\omega_n$ (speed).
**1. Maximum Overshoot ($\hat{s}$)**
- _Constraint Example:_ $\hat{s} \le 6\%$ ($0.06$)
- _Translation:_ Use the inverse overshoot formula.
$$
\zeta \ge \frac{|\ln(0.06)|}{\sqrt{\pi^2 + (\ln(0.06))^2}} \approx 0.667
$$
- _Rule of Thumb:_ **Flip the inequality.** Less overshoot requires _more_ friction. Always round up slightly (e.g., $\zeta = 0.67$) to create a "safe margin" for real-world hardware inaccuracies.

**2. Settling Time ($t_{s, \alpha\%}$)**
- _Constraint Example:_ $t_{s, 2\%} \le 2$ seconds
- _Translation:_ Use the settling time formula ($4$ for $2\%$ band, $3$ for $5\%$ band).
$$
t_{s,2\%} = \frac{4}{\zeta\omega_n} \le 2 \implies \omega_n \ge \frac{4}{2(0.67)} \approx 2.98 \text{ rad/s}
$$
- _Rule of Thumb:_ Pick a clean, slightly higher value (e.g., $\omega_n = 3.1$) to ensure the system is fast enough to settle before the deadline. Do not pick a massive value, or the required voltages ($K$) will fry your physical motors.
### Step 2: The MATLAB Workflow
Instead of manually calculating complex conjugate roots, feed the standard 2nd-order polynomial coefficients `[1, 2*zeta*omega_n, omega_n^2]` directly into MATLAB's `roots()` command.

```matlab
% 1. Define the Open-Loop System
A = [-0.2, -1; 1, 0];
B = [0.5; 0];
C = [0, 1];
D = 0;

% 2. Input your translated safe requirements
zeta = 0.67; 
omega_n = 3.1; 

% 3. Let MATLAB calculate the complex desired poles (p_des)
p_des = roots([1, 2*zeta*omega_n, omega_n^2]);

% 4. Calculate the Feedback Matrix (K) to place the poles
K = place(A, B, p_des);

% 5. Calculate the Feedforward Gain (N) to fix the DC-Gain to 1.0
% Formula: N = 1 / dcgain(Closed_Loop_System)
sys_cl = ss(A - B*K, B, C, D);
N = 1 / dcgain(sys_cl);

% Print Results
fprintf('K = [%.4f, %.4f]\n', K(1), K(2));
fprintf('N = %.4f\n', N);
```
## Reverse-Engineering Bode Plots (Finding $H(s)$)
The goal is to build the standard Bode-form transfer function:
$$H(s) = K \frac{(1 + \frac{s}{\omega_{z1}})\dots}{s^n (1 + \frac{s}{\omega_{p1}})\dots}$$
### Step 1: The Initial Slope (Origin Poles/Zeros)
Always start by looking at the far-left side of the **Magnitude** plot ($\omega \to 0$).
- **Flat line (0 dB/dec):** No poles or zeros at the origin ($n=0$).
- **Slope of -20 dB/dec:** One integrator ($1/s$).
- **Slope of -40 dB/dec:** Two integrators ($1/s^2$).
- **Slope of +20 dB/dec:** One differentiator ($s$).
### Step 2: Calculate the Gain ($K$)
The method changes slightly depending on your Step 1 result.
- **If the initial slope is FLAT (Type 0):**
    Read the flat magnitude value directly.
    $20\log_{10}(K) = \text{Magnitude (dB)} \implies K = 10^{\frac{\text{Mag}}{20}}$
	
- **If the initial line is SLOPED (Type $n$):**
    Extend that initial straight line (ignore any later bends) all the way to **$\omega = 1$ rad/s**. Read the magnitude of that _extended line_ at $\omega = 1$.
    $20\log_{10}(K) = \text{Magnitude at } \omega=1$
    
### Step 3: Break Frequencies (The Middle Poles & Zeros)
Scan the magnitude plot from left to right. Every time the slope bends, you hit a break frequency ($\omega_b$).
- **Slope bends UP by +20 dB/dec:** You found a Zero $(1 + \frac{s}{\omega_b})$.
- **Slope bends DOWN by -20 dB/dec:** You found a Pole $\frac{1}{(1 + \frac{s}{\omega_b})}$.
- **Slope bends by $\pm40$ dB/dec:** You found a double pole/zero OR a complex conjugate pair. Look for a sharp resonant peak to confirm it is a complex pair.
### Step 4: Verify with the Phase Plot (The "Trick" Check)
Always cross-reference your findings with the phase plot to catch Right-Half Plane (RHP) traps.
- **Standard LHP Pole:** Phase drops by $90^\circ$.
- **Standard LHP Zero:** Phase rises by $90^\circ$.
- **The RHP Zero Trap:** If the magnitude bends UP (+20 dB/dec), but the phase drops DOWN (-90°), you have a Non-Minimum Phase (RHP) zero!
    - _Formula changes to:_ $(1 - \frac{s}{\omega_b})$
# Feedback Control Systems
## The 4 Golden Equations of Feedback Control
When you connect a Controller $C(s)$ and a Plant $G(s)$ in a closed loop, you can no longer use just one equation. You have to calculate how different inputs (reference $r$, output disturbance $d_y$) affect different points in the system (output $y$, error $e$, control effort $u$).

**1. The Loop Transfer Function ($L$)**
- **Formula:** $L(s) = C(s)G(s)$
- **Use:** Used purely for stability analysis (Nyquist, Bode margins).

**2. The Complementary Sensitivity Function ($T$)**
- **Formula:** $T(s) = \frac{L(s)}{1 + L(s)}$
- **Path:** Reference $r \to$ Output $y$.
- **Use:** Calculates how perfectly the system tracks your desired input. Ideally, $T \approx 1$.

**3. The Sensitivity Function ($S$)**
- **Formula:** $S(s) = \frac{1}{1 + L(s)}$
- **Path:** Disturbance $d_y \to$ Output $y$ (and Reference $r \to$ Error $e$).
- **Use:** Calculates how well the system rejects disturbances. Ideally, $S \approx 0$.

**4. The Control Sensitivity Function ($S_u$)**
- **Formula:** $S_u(s) = \frac{C(s)}{1 + L(s)}$
- **Path:** Reference $r \to$ Control Effort $u$.
- **Use:** Calculates how hard your physical motors have to work to track the input.
### What are the *Paths* represent really
As you see for $T$, $S$ and $S_u$ we have paths. These functions are transfer functions basically and we know that
$$TF = \frac{\text{Output}}{\text{Input}}$$
So the left-side of the path represents the *Input* and the right-side of the path represents the *output*.
This way you can come up with those values ($r$, $u$, $y$) fairly easily.
## How to check if a Feedback Control System is well-posed
$$\lim_{s \to \infty} L(s) \neq -1$$
The rule is just that so you can do:
```matlab
% 1. Boot up the symbolic variable
syms s

% 2. Define your open-loop equation
L_sym = 4 / (s*(s+4));

% 3. Calculate the limit as s goes to infinity (inf)
L_inf = limit(L_sym, s, inf);

fprintf('The limit as s -> inf is: %s\n', char(L_inf));
```
## Stability of Feedback Control Systems
There are 3 ways to check the stability of FCS: (Actually there's also nichols way)
They all use the function $L(s)$
```matlab
s = tf('s');
L = 4 / (s * (s + 4));
```
#### 1) Stability by Definition
Here you build $T(s)$ and check it's poles.
**IMPORTANT:** It's mandatory to use minreal() here. Otherwise you might get some fake poles.
```matlab
T = minreal(L / (1 + L));
p = pole(T);
disp(p);
```
Here if all the real parts of $p$ are negative, it is *stable* otherwise not.
#### 2) Stability by Nyquist
TO BE WRITTEN (or not)
#### 3) Stability by margin()
```matlab
[Gm, Pm] = margin(L);
Gm_dB = 20 * log10(Gm);
disp(Gm_dB);
disp(Pm);
```
Here if both values that are being displayed are $> 0$, then the system is *stable* otherwise not.
## Connections from Sketch
![[Pasted image 20260601140323.png]]
So let's say you have a system like this, from here you can have many information:
- $e = r - (y + d_t)$
- $u = d_a + (e \times C(s))$
- $y = d_y + (u \times G(S))$
And remember all of this in the Laplace world $(s)$!
# Some Unrelated Hints
- If you have a diagonal matrix, the eigenvalues of the matrix is simply the entries on the diagonal.
- $u(t) = (2 + 3sin(0.1t))\epsilon(t) \to$ When you have a input like this you can divide it into two parts *(superposition)*
	- **DC Component (Flat Line):** $u_1(t) = 2$. The frequency $\omega = 0$ here.
		- **NOTE:** The frequency of the DC Component is always 0.
	- **AC Component (Sine Wave):** $u_2(t) = 3sin(0.1t)$. The frequency $\omega = 0.1$ here.
- LAB3 Problem 5 and Problem 6 notes haven't been prepared.
# Part 2 Questions Step by Step
## Phase 1 (Initial Setup)
We define these values based on the question.
```matlab
s = tf('s');
G = 120 / (s^3 + 15.8*s^2 + 12*s); 
T_s = 0.015;
G_ZOH = 1 / (1 + s * T_s / 2);
```
## Phase 2 (Building Static Controller  $C_{ss}(s)$)
The goals of this phase are:
- Establish the *System Type* (how many integrators do we need)
- Calculate the minimum static gain $(K_c)$ required to satisfy the steady-state constraints.

The controller will always be in this form:
$$
C_{ss}(s) = \frac{K_c}{s^h}
$$
- $K_c \to$ Gain
- $h \to$ Number of integrators added by the controller
### Step 1 (Isolate the Steady-State Requirements)
Check the list of requirements, for steady-state we're looking for things like: $|e_r^\infty|$, $|y_{d_a}^\infty|$, $|y_{d_y}^\infty|$
- **IGNORE:** Any requirement where the input signal is a sine wave like $sin(\omega t)$. We'll handle them in Phase 3.
- **KEEP:** Requirements where the input signal is a step $(\epsilon(t))$ or a ramp $(t\epsilon(t))$
### Step 2 (Determine the number of integrators $h$ needed for the system)
For each requirement we keep we'll do this:
**NOTE:** By input we mean $d_a$ for $|y_{d_a}^\infty|$ for example.
#### If the Input is Step $\epsilon(t)$:
- If target is zero $(= 0)$: System needs *1* total integrator.
- If target is finite $(\text{e.g.}\leq 0.5)$: System needs *0* total integrator.
#### If the Input is Ramp $t\epsilon(t)$:
- If target is zero $(= 0)$: System needs *2* total integrator.
- If target is finite $(\text{e.g.}\leq 0.5)$: System needs *1* total integrator.
#### If the Input is Parabola $t^2\epsilon(t)$:
- If target is zero $(= 0)$: System needs *3* total integrator.
- If target is finite $(\text{e.g.}\leq 0.5)$: System needs *2* total integrator.

After calculating this for each requirement, we just need the *maximum* value that we got from any requirement. That will be our number.

After determining the number of integrators needed for the system you need to check how many integrators does our plant $G(s)$ already has
- Checking this is fairly easy, just group the $s$ together in the denominator of $G(s)$.
- If there's a single $s$ standing there that means we have one integrator
- If there's $s^2$, that means we have two integrators.
- If it's just like $(s + 2)(s - 5)$, as you can see there's no single $s$ standing there so we have zero integrators

Count how many integrators your plant $G(s)$ already has. Your controller $C_{ss}(s)$ must supply whatever is missing to reach the required total.
(e.g., If the system needs 1 integrator, and $G(s)$ has 0, your controller needs $1/s$. If $G(s)$ already has an $s$ in the denominator, your controller needs 0).
### Step 3 (Come up with the correct Transfer Function)
You only need to find the transfer function for the specific requirement(s) that determined your maximum $h$ in Step 2.
**NOTE:** If two requirements demanded the exact same maximum $h$, you calculate for both and pick the larger $K_c$

To find the relationship between one specific input and output, use the principle of **Superposition**: turn all other external inputs in the master equations to $0$.

From the block diagram you need to extract master equations like this first:
- $y = d_y + u \cdot G(s)$
- $u = d_a + e \cdot C(s)$
- $e = r - (y + d_t)$
Substitute them into each other for your specific input. For standard exams, they always resolve to one of these three common forms. Let's call the transfer function $W(s)$:
- **For Reference Tracking ($e_r$):** Set $d_a, d_y, d_t = 0$. Solve for $e/r$.
$$W(s) = \frac{1}{1 + C(s)G(s)}$$
- **For Actuator Disturbance ($y_{d_a}$):** Set $r, d_y, d_t = 0$. Solve for $y/d_a$.
$$W(s) = \frac{G(s)}{1 + C(s)G(s)}$$
- **For Output Disturbance ($y_{d_y}$):** Set $r, d_a, d_t = 0$. Solve for $y/d_y$.
$$W(s) = \frac{1}{1 + C(s)G(s)}$$
### Step 4 (Calculating $K_c$)
We use Final Value Theorem (FVT) here. It calculates exactly what the system output settles to as time goes to infinity.

The master formula:
$$\text{Final Value} = \lim_{s \to 0} s \cdot W(s) \cdot U(s)$$
But you don't need that we can do this step on Matlab:
```matlab
% Boot up symbolic variables
syms s t Kc

% 1. Define the Time-Domain Input and Convert to S-Domain
% For a step of 0.4: input_t = 0.4;
% For a ramp of 2t: input_t = 2 * t;
input_t = 2 * t;
U_s = laplace(input_t, t, s);

% 2. Define the Plant and Controller Symbolically
G_sym = 40 / ((s + 5.72)*(s - 1.72));
% Controller is Kc / s^h, so if you have h=1:
C_sym = Kc / s;

% 3. Define the Transfer Function W(s)
W_sym = 1 / (1 + C_sym * G_sym);

% 4. Apply the Final Value Theorem
FVT_result = limit(s * W_sym * U_s, s, 0);

% 5. Solve for the exact Kc boundary
% This limit is what the requirement had in the question
% There's a big catch here: If the exam_limit = 0, then you can simply assume K_c = 1, otherwise do these:
exam_limit = 0.25;
Kc_solutions = solve(abs(FVT_result) == exam_limit, Kc);
Kc_min = double(max(Kc_solutions));

disp(Kc_min);
```
 Like this you'll have your $K_c$ but it's always nice to round $K_c$ up a bit for example:
 - If $K_c$ is 1.968 $\rightarrow$ use 2.0
- If $K_c$ is 0.812 $\rightarrow$ use 0.85
- If $K_c$ is 14.1 $\rightarrow$ use 15
## Phase 3 (Nichols Loop Shaping)
Before starting this phase, you need to define $K_c$ and Controller using standard `tf` variables:
```matlab
Kc = 2.0; % The safe value you found in Phase 2
Css = Kc / s; % Use Kc/s if h=1, Kc/s^2 if h=2, or just Kc if h=0
C = Css;
```
### Step 1 (Translate Requirements to Math)
#### 1) High-Frequency Noise $(|y_{d_t}^\infty|) \to$ Attenuation Boundary $(M_{T\_HF})$
The input of $|y_{d_t}^\infty|$ is always going to be sinusoidal. So it will be skipped in Phase 2.
- **Formula:**
$$
M_{T\_HF} =  20 \log_{10}\left(\frac{\text{Output Limit}}{\text{Input Amplitude}}\right)
$$
- **Example:** If $d_t(t) = 0.1\sin(90t)$ and limit is $\le 0.01$, then $M_{T\_HF} = 20 \log_{10}\left(\frac{0.01}{0.1}\right) = -20 \text{ dB}$.
#### 2) Rise Time $(t_r) \to$ Target Crossover Frequency $(\omega_{c,des})$
- **Formula:**
$$
\omega_{c,des} \ge \frac{1.8}{t_r}
$$
#### 3) Overshoot ($\hat{S}$) $\to$ Nichols Exclusion Circles ($T_p$ and $S_p$)
Open the `diagrams_translation_requirements.pdf` file provided during the exam and follow these three steps:
- **Find $\zeta$:** Go to the first chart ($\hat{S}$ vs $\zeta$). Find your maximum overshoot percentage on the Y-axis (e.g., 20), trace horizontally to the curve, and read the corresponding $\zeta$ value on the X-axis.
- **Find $T_p$:** Go to the second chart ($d$ or $T_p$ vs $\zeta$). Find your $\zeta$ on the X-axis, trace vertically to the curve, and read the $T_p$ value on the Y-axis.
- **Find $S_p$:** Go to the third chart ($S$ vs $\zeta$). Find your $\zeta$ on the X-axis, trace vertically to the curve, and read the $S_p$ value on the Y-axis.
Once you read the linear values from the charts, convert them to dB in MATLAB:
```matlab
% Example values read from the PDF charts
T_p_linear = 1.23;
S_p_linear = 1.53;

T_p = 20 * log10(T_p_linear);
S_p = 20 * log10(S_p_linear);
```

So at the end you'll have these:
```matlab
wc_des = 1.85 / t_r_limit;
M_T_HF = 20 * log10(noise_output_limit / noise_input_amp);
T_p = 20 * log10(Tp_linear);
S_p = 20 * log10(S_p_linear);
```
### Step 2 (The Initial Plot)
**The Goal:** Before we start fixing the system, we need to see how bad the baseline is. By plotting the plant ($G$), the delay ($G_{ZOH}$), and our steady-state controller ($C_{ss}$), we can see exactly where the system naturally wants to go and which exclusion zones it violates.

**The Action:** We multiply them together to create the initial open-loop transfer function ($L_1$) and plot it against our target grids.
```matlab
L1 = C * G * G_ZOH;
figure(1)
nichols(L1)
hold on
T_grid(T_p)
S_grid(S_p)
T_grid(M_T_HF)
```
#### How to read the Nichols Chart
![[Pasted image 20260615123923.png]]
- **The Axes:** The x-axis is Phase (deg) and y-axis is Gain (dB)
- **The Black Line:** This represents our system, we need to change it according to the needs.
- **The Hidden Frequency $(\omega)$:** The top of the system line represents slow frequencies $(\omega \approx 0)$. As you trace the line downward the frequency increases. Very bottom *(tail)* of our system line represents the high frequencies $(\omega \to \infty)$.
- **The Danger Zone (Center Circles):** The red $(S_p)$ and blue $(T_p)$ circles in the middle. Our system line *must* stay completely to the *right and bottom* of these circles.
- **The Noise Ceiling:** This is the $M_{T\_HF}$ limit (a horizontal line, like -41.93 dB). The specific "mile marker" on your curve that corresponds to the exam's noise frequency (e.g., $\omega_t = 100$ rad/s) *must sit completely below* this line.
- **The Speed Line (0 dB Axis):** The horizontal 0dB line determines system speed. The specific frequency that crosses this 0 dB line becomes your actual crossover frequency $(\omega_c)$.
### Step 3 (Move 1: The Phase Shift - Dodging the Danger Zone)
**The Goal:** Your initial $L_1$ curve will likely crash into the left side of the $T_p$ and $S_p$ circles. We need to physically pull the curve to the _right_ to dodge them and create a safe phase margin.

**The Action:** Adding a **Real Negative Zero** adds phase lead (pulls the curve right). You should always start with a single zero to avoid amplifying high-frequency noise unnecessarily. If a single zero isn't strong enough to pull the curve past the circles, upgrade to a double zero.

Anchor the zero slightly behind your target crossover frequency ($\omega_{c,des}$) using a tuning factor (`wnorm`), usually between **2 and 6**.
```matlab
wnorm = 3; % TUNE THIS: Adjust between 2 and 6
wZ = wc_des / wnorm;
C_Z = 1 + (s / wZ);

% Try Option A first. Run the script.
% If the green line still crashes into the circles, comment it out and use Option B.

% Option A: Single Zero (Moderate Pull)
C = C * C_Z; 
% Option B: Double Zero (Heavy Pull)
% C = C * C_Z * C_Z; 

L2 = C * G * G_ZOH;
nichols(L2, 'g'); % Plot the new shape in green
```
