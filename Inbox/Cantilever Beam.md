---
icon: OcInfinity16
---

#Elasticity  #Example  

# Plane stress

Consider a cantilever beam with thickness $D$ and length $L$. The left hand side of beam is fixed and right side applied a traction $P$ along the $y$ axis. The material parameters of beam is that: Young's Module $E$, Poission's ratio $\nu$. According to [[Linear Elasticity#Plane strain and plane stress|plane stress assumption]] and Saint Venant's principle, the exact solution of this problem is given by:

$$
\left \{
\begin{array}{l}
u = -\frac{Py}{6EI}[(6L-3x)x + (2+\nu)(y^2 - \frac{D^2}{4})] \\
v = \frac{P}{6EI}[3\nu y^2(L-x) + (4+5\nu)\frac{D^2x}{4} + (3L-x)x^2]
\end{array}
\right .
$$
where $u$ and $v$ are the displacements along the $x$ and $y$ axises respectively, $I$ is the second moment of beam's cross area, if the cross area is rectangle, $I=\frac{bD^3}{12}$ and $b$ is width of beam. The corresponding gradients of displacement can be calculated by direct difference as: 
$$
\left \{
\begin{array}{l}
u_{,x} = -\frac{Py}{EI}(L-x) \\
u_{,y} = \frac{P}{6EI}[-(6L-3x)x - (2+\nu)(3y^2 - \frac{D^2}{4})] \\
v_{,x} = \frac{P}{6EI}[(6L-3x)x -3\nu y^2 + (4+5\nu)\frac{D^2}{4}] \\
v_{,y} = \frac{Py}{EI}(L-x)\nu
\end{array}
\right .
$$
therefore, the strain and stress can be obtain by leading the [[Linear Elasticity#^9388fd|constitutive relation]]:
Strain:
$$
\begin{Bmatrix}
\varepsilon_{xx} \\ \varepsilon_{yy} \\ 2\varepsilon_{xy}
\end{Bmatrix} = 
\begin{Bmatrix}
u_{,x} \\ v_{,y} \\ u_{,y} + v_{,x}
\end{Bmatrix} 
= \frac{P}{EI}
\begin{Bmatrix}
-(L-x)y \\
\nu(L-x)y \\
(1+\nu)(\frac{D^2}{4} - y^2)
\end{Bmatrix}
$$
Stress:

$$
\begin{split}
\begin{Bmatrix}
\sigma_{xx} \\ \sigma_{yy} \\ \sigma_{xy}
\end{Bmatrix} &=
\frac{E}{1-\nu^2}
\begin{bmatrix}
  1 & \nu & 0 \\
\nu &   1 & 0 \\
  0 &   0 & \frac{1-\nu}{2}
\end{bmatrix}
\begin{Bmatrix}
\varepsilon_{xx} \\ \varepsilon_{yy} \\ 2\varepsilon_{xy}
\end{Bmatrix} \\ &=
\begin{Bmatrix}
-\frac{P(L-x)y}{I} \\ 0 \\ \frac{P}{2I}(\frac{D^2}{4} - y^2)
\end{Bmatrix}
\end{split}
$$
In order to check the consistency, the essential boundary at left side is enforced by theoretical displacement, and the left side is applied by: 

$$
\begin{Bmatrix}
t_{x} \\ t_{y}
\end{Bmatrix} = 
\begin{Bmatrix}
\sigma_{xx}n_{x} + \sigma_{xy}n_{y} \\
\sigma_{yx}n_{x} + \sigma_{yy}n_{y}
\end{Bmatrix}
$$
As we can find by the [[Linear Elasticity#Strong form|strong form]], there has no body force in this problem:

$$
\boldsymbol b = -
\begin{Bmatrix}
\sigma_{xx,x} + \sigma_{xy,y} \\
\sigma_{yx,x} + \sigma_{yy,y}
\end{Bmatrix} = \mathbf{0}
$$
It is noted that, as we can find by substituting $y=\pm \frac{D}{2}$ to traction, the top and bottom of cantilever beam is immersed a natural boundary as follow:

$$
\boldsymbol t = \mathbf{0}
$$
