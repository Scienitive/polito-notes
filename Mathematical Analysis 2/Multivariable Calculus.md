## Partial Derivatives
### Formula
#### Formal Definition
$$
\frac{\partial f}{\partial x}(a,b) = \lim_{h \to 0}\frac{f(a+h, b) - f(a, b)}{h}
$$
#### So Basically
Let's say $f(x,y) = x^2y + sin(y)$
Partial derivative when $y = 2$ for example:
$$
\frac{\partial f}{\partial x}(x,2) = \frac{\partial}{\partial x} \big(2x^2 + sin(2)\big)
$$
### Higher Order Partial Derivatives
![[Pasted image 20250124073653.png]]
## Gradient
$$
\nabla f =
\begin{bmatrix}
\frac{\partial f}{\partial x} \\
\frac{\partial f}{\partial y} \\
\end{bmatrix}
$$
![[Pasted image 20250124074216.png]]
### Remark
Gradient is always *perpendicular* to contour lines.
![[Pasted image 20250124074828.png]]
## Directional Derivatives
Very similar to Partial derivatives but this time instead of taking the derivative in just one dimension you take the derivate in the direction of a vector like $\vec{n} = (1,2)$ for example.
So, if $\vec{n} = (a, b)$
$$
\frac{\partial f}{\partial \vec{n}}(x,y) = a\frac{\partial f}{\partial x} + b\frac{\partial f}{\partial y} = \vec{n} \cdot \nabla f
$$
**IMPORTANT:** Actually above is not 100% true because $\vec{n}$ always need to be unit vector. So it's length should be 1 when doing calculations. Otherwise you might get wrong results.
## Multivariable Chain Rule
![[Pasted image 20250124162843.png]]
![[Pasted image 20250124163133.png]]
## Curvature
![[Pasted image 20250124163632.png]]
### Formula
$$
\kappa = \frac{x'(t)y''(t)-x''(t)y'(t)}{\big|(x'(t)^2 + y'(t)^2)^{3/2}\big|}
$$
### Length of Curve Finding
Let's say curve is $c(t) = (x, y, z)$
- First you need to calculate $c'(t) = (\frac{dx}{dt}, \frac{dy}{dt}, \frac{dz}{dt})$
- Then you need to calculate magnitude of it:
$$
||c'(t)|| = \sqrt{\frac{dx}{dt}^2 + \frac{dy}{dt}^2 + \frac{dz}{dt}^2}
$$
- Then you can find this formula to find the arc length:
$$
L = \int^b_a||c'(t)||dt
$$
## Divergence
Let's say:
$$
\vec{V}(x,y) = 
\begin{bmatrix}
P(x, y) \\
Q(x,y)
\end{bmatrix}
$$
Then the divergence of $\vec{V}$:
$$
\nabla \cdot \vec{V}(x,y) = \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y}
$$
## Curl
### 2D Curl
Again let's say:
$$
\vec{V}(x,y) = 
\begin{bmatrix}
P(x, y) \\
Q(x,y)
\end{bmatrix}
$$
Then the formula of 2D Curl:
$$
\mathrm{2D-} \mathrm{Curl} \ \vec{V}(x,y) = \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}
$$
In curls **counterclockwise** is *positive* and **clockwise** is *negative*.
### 3D Curl
Let's say:
$$
\vec{V}(x,y,z) = 
\begin{bmatrix}
P(x,y,z) \\
Q(x,y,z) \\
R(x,y,z)
\end{bmatrix}
$$
Then the formula of 3D Curl:
$$
\mathrm{3D-} \mathrm{Curl} \ \vec{V}(x,y,z) =
\begin{bmatrix}
\frac{\partial}{\partial x}\\
\frac{\partial}{\partial y}\\
\frac{\partial}{\partial z}
\end{bmatrix}
\times
\begin{bmatrix}
P\\
Q\\
R
\end{bmatrix}
$$
#### Some Important Notes
- When the curl is equal to $0$ it means it is curl-free.
- A vector field is *conservative* if there exists a *potential function*.
- If the curl is 0 then it must be conservative so there aren't any potential functions
![[Pasted image 20250129052439.png]]
### More General Formula
$$
\nabla \times \vec{V}
$$
