## Finding Tangent Plane
$x_0$, $y_0$ and $z_0$ being the points where we calculate the tangent plane from.
$$
L(x,y) = a(x - x_0)+b(y-y_0)+z_0
$$
Apart from this you also need to find $a$, $b$ valued by:
$$
a = \frac{\partial f}{\partial x}(x_0, y_0)
$$
$$
b = \frac{\partial f}{\partial y}(x_0, y_0)
$$
### Vector Form (Local Linearization)
First let's declare:
$$
\vec{x} = 
\begin{bmatrix}
x \\
y
\end{bmatrix}
\ \ \ \ \ \ \ \ 
\vec{x_0} = 
\begin{bmatrix}
x_0 \\
y_0
\end{bmatrix}
$$
Then:
$$
\nabla f(\vec{x_0}) \cdot (\vec{x} - \vec{x_0}) + f(\vec{x_0})
$$
## Quadratic Approximation
$$
Q(x,y) = f(x_0, y_0) + f_x(x_0, y_0)(x - x_0) + f_y(x_0, y_0)(y - y_0) + a(x - x_0)^2 + b(x - x_0)(y - y_0) + c(y - y_0)^2
$$
Where:
$$
a = \frac{1}{2}f_{xx}(x_0, y_0)
$$
$$
b = f_{xy}(x_0, y_0)
$$
$$
c = \frac{1}{2}f_{yy}(x_0, y_0)
$$
**NOTE:** $f_x$ means first partial derivative with x and $f_{xx}$ means second partial derivative.
## Maxima and Minima
![[Pasted image 20250128030315.png]]
$$
\frac{\partial f}{\partial x}(x_0, y_0) = 0 \ \ \ \& \ \ \ \frac{\partial f}{\partial y}(x_0, y_0) = 0
$$
Or in other terms:
$$
\nabla f = \vec{0}
$$
If these conditions are true, that means you've found a *local maxima* or *local minima*.
**NOTE:** There is one exception called *saddle points*
### Saddle Points
![[Pasted image 20250128030730.png]]
When you purely look at the graph from $x$ if it's local maxima but from $y$ it's local minima (or the other way around) we call these points saddle points and they're not particularly local maxima or local minima for the entire function.
### How to distinguish local maxima, local minima and saddle points
With a test called **Second partial derivative test**.
$$
SPDT = f_{xx}(x_0, y_0)f_{yy}(x_0,y_0)-f_{xy}(x_0,y_0)^2
$$
- If $SPDT > 0 \to$ You have either local maxima or local minima at that point. You can figure it out by looking either $f_{xx}$ or $f_{yy}$ part.
- If $SPDT < 0 \to$ You definitely have a saddle point there.
- If $SPDT = 0 \to$ Then it means this test isn't enough to tell anything about the situation.
### Hessian Matrix
![[Pasted image 20250129054731.png]]