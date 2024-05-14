---
icon: OcInfinity16
---

#Elasticity  #Example 

Displacement (plane stress)

$$
\left \{
\begin{array}{l}
u_{r} = \frac{1}{E(b^{2} - a^{2})}[(1-\nu)(a^{2}P_{i} - b^{2}P_{o})r + (1+\nu)\frac{a^{2}b^{2}(P_{i} - P_{o})}{r}] \\
u_{\theta} = 0
\end{array}
\right .
$$

Displacement (plane strain)

$$
\left \{
\begin{array}{l}
u_{r} = \frac{1+\nu}{E(b^{2} - a^{2})}[(1-2\nu)(a^{2}P_{i} - b^{2}P_{o})r + \frac{a^{2}b^{2}(P_{i} - P_{o})}{r}] \\
u_{\theta} = 0
\end{array}
\right .
$$

$$
\left \{
\begin{array}{l}
u = u_{r}\cos \theta = \frac{x}{r} u_{r}  \\
v = u_{r}\sin \theta = \frac{y}{r} u_{r} 
\end{array}
\right .
$$

Strain (plane stress)

$$
\begin{Bmatrix}
\varepsilon_{xx} \\ \varepsilon_{yy} \\ 2\varepsilon_{xy}
\end{Bmatrix} = 
\begin{Bmatrix}
u_{,x} \\ v_{,y} \\ u_{,y} + v_{,x}
\end{Bmatrix} 
= \frac{1}{E(b^{2} - a^{2})}
\begin{Bmatrix}
(1-\nu)(a^{2}P_{i} - b^{2}P_{o}) + (1+\nu)\frac{a^{2}b^{2}(P_{i} - P_{o})(y^2-x^2)}{r^4}\\
(1-\nu)(a^{2}P_{i} - b^{2}P_{o}) - (1+\nu)\frac{a^{2}b^{2}(P_{i} - P_{o})(y^2-x^2)}{r^4} \\
-(1+\nu)\frac{4a^{2}b^{2}(P_{i} - P_{o})xy}{r^4}
\end{Bmatrix}
$$

Strain (plane strain)

$$
\begin{Bmatrix}
\varepsilon_{xx} \\ \varepsilon_{yy} \\ 2\varepsilon_{xy}
\end{Bmatrix} = 
\begin{Bmatrix}
u_{,x} \\ v_{,y} \\ u_{,y} + v_{,x}
\end{Bmatrix} 
= \frac{1+\nu}{E(b^{2} - a^{2})}
\begin{Bmatrix}
(1-2\nu)(a^{2}P_{i} - b^{2}P_{o}) + \frac{a^{2}b^{2}(P_{i} - P_{o})(y^2-x^2)}{r^4}\\
(1-2\nu)(a^{2}P_{i} - b^{2}P_{o}) - \frac{a^{2}b^{2}(P_{i} - P_{o})(y^2-x^2)}{r^4} \\
-\frac{4a^{2}b^{2}(P_{i} - P_{o})xy}{r^4}
\end{Bmatrix}
$$

Stress

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
\end{Bmatrix} \\ &= \frac{1}{b^{2}-a^{2}}
\begin{Bmatrix}
a^{2}P_{i}-b^{2}P_{o}+\frac{a^{2}b^{2}(P_{i}-P_{o})(y^{2}-x^{2})}{r^{4}} \\
a^{2}P_{i}-b^{2}P_{o}-\frac{a^{2}b^{2}(P_{i}-P_{o})(y^{2}-x^{2})}{r^{4}} \\ 
-\frac{2a^{2}b^{2}(P_{i} - P_{o})xy}{r^4}
\end{Bmatrix}
\end{split}
$$

Traction
$$
\begin{Bmatrix}
t_1 \\ t_2
\end{Bmatrix} = 
\begin{Bmatrix}
\sigma_{xx}n_{x} + \sigma_{xy}n_{y} \\
\sigma_{yx}n_{x} + \sigma_{yy}n_{y}
\end{Bmatrix} 
$$

Body force

$$
\boldsymbol{b} = - \nabla \cdot \boldsymbol \sigma = \mathbf{0}
$$

Boundary condition
$$
\left \{
\begin{array}{l}
x = 0: u = 0, \; t_{y} = 0 \\
y = 0: v = 0, \; t_{x} = 0 \\
r = a: \boldsymbol{t} = 
-\frac{P_{i}}{a}
\begin{Bmatrix}
x \\
y
\end{Bmatrix}\\
r = b: \boldsymbol{t} = 
-\frac{P_{o}}{b}
\begin{Bmatrix}
x \\
y
\end{Bmatrix}\\
\boldsymbol{b} = \mathbf{0}
\end{array}
\right .
$$
