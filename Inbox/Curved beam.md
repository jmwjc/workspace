---
icon: OcInfinity16
---

#Curvilinear #Elasticity 
# Curved Timoshenko beam
In contrast to straight beam, the kinematics of curved beam should be described by [[Curvilinear Coordinates|curvilinear coordinates]]. For a curvilinear coordinates system $\xi^1,\xi^2,\xi^3$, a point $\boldsymbol{x}$ in curved beam can be expressed as:
$$
\boldsymbol x(\xi^1,\xi^2,\xi^3) = \boldsymbol r(\xi^1) + \boldsymbol s(\xi^2) + \xi^3 \boldsymbol a_3(\xi^1)
$$
where the covariant basis vector $\boldsymbol g_i$ is evaluated by
$$
\boldsymbol g_i = \frac{\partial \boldsymbol x}{\partial \xi^i} \Rightarrow
\left \{
\begin{split}
\boldsymbol g_1 &= \frac{\partial \boldsymbol r}{\partial \xi^1} + \xi^3 \frac{\partial \boldsymbol a_3}{\partial \xi^1} = \boldsymbol a_1 + \xi^3 \boldsymbol a_{3,1} = (1+\Gamma_{13}^1 \xi^3)\boldsymbol a_1 \\
\boldsymbol g_2 &= \frac{\partial \boldsymbol s}{\partial \xi^2} = \boldsymbol a_2 \\
\boldsymbol g_3 &= \boldsymbol a^3 = \boldsymbol a_3 \\
\end{split}
\right .
$$
where $\boldsymbol a_i,i=1,2,3$ is a orthogonal basis vector base on the geometry of curved beam, $\boldsymbol a_1$ is the axial direction, $\boldsymbol a_3$ is the direction of the thickness and $\boldsymbol a_2$ is perpendicular to $\boldsymbol a_1, \boldsymbol a_3$. Due to the orthogonality of $\boldsymbol a_1$, $\boldsymbol a_3$, the derivatives of $\boldsymbol a_1,\boldsymbol a_3$ has the following relationship
$$
(\boldsymbol a_1 \cdot \boldsymbol a^3)_{,1} \Rightarrow \boldsymbol a_{1,1} = - \boldsymbol a_1 \cdot \boldsymbol a_{3,1} \boldsymbol a_3 = \Gamma_{11}^3 \boldsymbol a_3, \quad \boldsymbol a_{3,1} = - \boldsymbol a_{1,1} \cdot \boldsymbol a_3 \boldsymbol a_1 = \Gamma_{13}^1 \boldsymbol a_1
$$
in which $\Gamma_{ij}^k$ is the [[Curvilinear Coordinates#^05802b|second kind of the Christoffel symbol]] of base $\boldsymbol a_i$.
In the infinitesimal deformation assumption, the displacement of curved beam $\boldsymbol u$ is assumed to be the follows
$$
\boldsymbol u = \boldsymbol v + \xi^3 \boldsymbol \varphi
$$
where $\boldsymbol v$ and $\boldsymbol \varphi$ are the displacement and rotation in mid-surface, their components are given by
$$
\boldsymbol a_1 \cdot \boldsymbol v = u, \quad \boldsymbol a_2 \cdot \boldsymbol v = 0, \quad \boldsymbol a_3 \cdot \boldsymbol v = w
$$
$$
\boldsymbol a_1 \cdot \boldsymbol \varphi = - \varphi, \quad \boldsymbol a_2 \cdot \boldsymbol \varphi = 0, \quad \boldsymbol a_3 \cdot \boldsymbol \varphi = 0
$$
In this circumstance, the components of strain tensor can be computed by
$$
\varepsilon_{ij} = \frac{1}{2}(\boldsymbol g_i \cdot \boldsymbol u_{,j} + \boldsymbol g_j \cdot \boldsymbol u_{,i})
$$
and
$$
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ \varepsilon_{33} \\ 2\varepsilon_{12} \\ 2\varepsilon_{13} \\ 2\varepsilon_{23}
\end{Bmatrix} \approx
\begin{Bmatrix}
\boldsymbol a_1 \cdot \boldsymbol v_{,1} + (\boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} + \boldsymbol a_{1} \cdot \boldsymbol \varphi_{,1}) \xi^3 \\ 0 \\ \underbrace{\boldsymbol a_3 \cdot \boldsymbol \varphi}_0 \\
\underbrace{\boldsymbol a_2 \cdot (\boldsymbol v_{,1} + \boldsymbol \varphi_{,1}\xi^3)}_0 \\
\boldsymbol a_1 \cdot \boldsymbol \varphi + \boldsymbol a_3 \cdot \boldsymbol v_{,1} + \underbrace{(\boldsymbol a_3 \cdot \boldsymbol \varphi_{,1} + \boldsymbol a_{3,1} \cdot \boldsymbol \varphi)}_0 \xi^3 \\
\underbrace{\boldsymbol a_2 \cdot \boldsymbol \varphi}_0
\end{Bmatrix} =
\begin{Bmatrix}
\varepsilon + \kappa \xi^3 \\ 0 \\ 0 \\ 0 \\ \gamma \\ 0
\end{Bmatrix}
$$
where #FIXME
$$
\begin{align}
\varepsilon &= \boldsymbol a_1 \cdot \boldsymbol v_{,1} =(\boldsymbol a_1 \cdot \boldsymbol v)_{,1} - \boldsymbol a_{1,1} \cdot \boldsymbol v = u_{,1} - \Gamma_{11}^3 w \\
\kappa &= \boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} + \boldsymbol a_1 \cdot \boldsymbol \varphi_{,1} 
= \underbrace{\boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} - \boldsymbol a_{1,1} \cdot \boldsymbol \varphi}_{\approx 0} + (\boldsymbol a_1 \cdot \boldsymbol \varphi)_{,1} = - \varphi_{,1} \\
\gamma &= \boldsymbol a_1 \cdot \boldsymbol \varphi + \boldsymbol a_3 \cdot \boldsymbol v_{,1} = 
\boldsymbol a_1 \cdot \boldsymbol \varphi + (\boldsymbol a_3 \cdot \boldsymbol v)_{,1} - \boldsymbol a_{3,1} \cdot \boldsymbol v = w_{,1} - \varphi - \Gamma_{13}^1 u
\end{align}
$$
in which $\varepsilon, \kappa, \gamma$ are the membrane strain, curvature and shearing strain respectively.
For a circular curved beam with radius $R$, a point $\boldsymbol x$ in curved beam can be presented as
$$
\boldsymbol x = \begin{Bmatrix}
- R \cos \frac{s}{R} \\ R \sin \frac{s}{R}
\end{Bmatrix} + \xi^3 \begin{Bmatrix}
- \cos \frac{s}{R} \\ \sin \frac{s}{R}
\end{Bmatrix}
$$
and the base vector $\boldsymbol a_1$ and $\boldsymbol a_3$ have the following forms
$$
\boldsymbol a_1 = \begin{Bmatrix}
\sin \frac{s}{R} \\ \cos \frac{s}{R}
\end{Bmatrix}, \quad
\boldsymbol a_3 = \begin{Bmatrix}
- \cos \frac{s}{R} \\ \sin \frac{s}{R}
\end{Bmatrix}
$$
the second kind of the Christoffel symbols of $\Gamma_{11}^3, \Gamma_{13}^1$ can be evaluated by
$$
\Gamma_{11}^3 = - \frac{1}{R}, \quad \Gamma_{13}^1 = \frac{1}{R}
$$
Consequently, the membrane strain $\varepsilon$, curvature $\kappa$ and $\gamma$ shearing strain can be reduced to
$$
\begin{align}
\varepsilon &= u_{,s} + \frac{w}{R} \\
\kappa &= -\varphi_{,s} \\
\gamma &= w_{,s} - \varphi - \frac{u}{R}
\end{align}
$$

# Curved Euler beam
For Euler beam assumption, the shearing strain $\kappa$ is vanished, then the rotation $\boldsymbol \varphi$ can be expressed by displacement $\boldsymbol v$ as
$$
\boldsymbol a_1 \cdot \boldsymbol \varphi = - \boldsymbol a_3 \cdot \boldsymbol v_{,1} \Rightarrow \boldsymbol \varphi = - \boldsymbol a_3 \cdot \boldsymbol v_{,1} \boldsymbol a^1
$$
substituting it into $\kappa$ yields
$$
\begin{split}
\kappa &= \boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} - \boldsymbol a_{1,1} \cdot \boldsymbol \varphi + (\boldsymbol a_1 \cdot \boldsymbol \varphi)_{,1} \\
&= \boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} - \Gamma_{11}^3 \underbrace{\boldsymbol a_3 \cdot \boldsymbol \varphi}_0 - (\boldsymbol a_3 \cdot \boldsymbol v_{,1})_{,1} \\
&= \boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} - \boldsymbol a_{3,1} \cdot \boldsymbol v_{,1} - \boldsymbol a_3 \cdot \boldsymbol v_{,11} \\
&= - \boldsymbol a_3 \cdot \boldsymbol v_{,11} \\
\end{split}
$$
Plugging them into weak form leads to
$$
\begin{split}
\int_\Omega \delta \varepsilon N d\Omega + \int_\Omega \delta \kappa M d\Omega &=
\int_\Omega \delta \boldsymbol v_{,1} \cdot \boldsymbol a_1 N d\Omega - \int_\Omega \delta \boldsymbol v_{,11} \cdot \boldsymbol a_3 M d\Omega \\
&= \left . \delta \boldsymbol v \cdot \boldsymbol a_1 N \right \vert_\Gamma - \int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_1 N)_{,1} d\Omega 
- \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 M \right \vert_\Gamma + \int_\Omega \delta \boldsymbol v_{,1} \cdot (\boldsymbol a_3 M)_{,1} d\Omega \\
&= \left . \delta \boldsymbol v \cdot (\boldsymbol a_1 N + (\boldsymbol a_3 M)_{,1}) \right \vert_\Gamma
- \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 M \right \vert_\Gamma
- \int_\Omega \delta \boldsymbol v \cdot ((\boldsymbol a_1 N)_{,1} + (\boldsymbol a_3 M)_{,11}) d\Omega \\
\end{split}
$$
Hellinger-Reissner principle
$$
\begin{split}
\Pi(\boldsymbol v,N,M) &= \int_\Omega \frac{1}{2}\frac{N N}{EA} + \frac{1}{2}\frac{M M}{EI} d\Omega 
- \left . (\boldsymbol a_1 N + (\boldsymbol a_3 M)_{,1}) \cdot \bar{\boldsymbol v} \right \vert_{\Gamma_v} + \left . M \bar \theta \right \vert_{\Gamma_\theta} \\
&- \left . \boldsymbol v \cdot (\boldsymbol a_1 N + (\boldsymbol a_3 M)_{,1} - \bar{\boldsymbol t}) \right \vert_{\Gamma_t} + \left . \boldsymbol v_{,1} \cdot \boldsymbol a_3 (M - \bar M) \right \vert_{\Gamma_M} + \int_\Omega \boldsymbol v \cdot ((\boldsymbol a_1 N)_{,1} + (\boldsymbol a_3 M)_{,11} + \bar{\boldsymbol b}) d\Omega 
\end{split}
$$
weak form
$$
\begin{align}
\int_\Omega \frac{a^{11}}{EA} (\delta N \boldsymbol a_1) \cdot (\boldsymbol a_1 N) d\Omega - \left . \delta N \boldsymbol a_1 \cdot \boldsymbol v \right \vert_{\Gamma_t} + \int_\Omega (\delta N \boldsymbol a_1)_{,1} \cdot \boldsymbol v d\Omega &= \left . \delta N \boldsymbol a_1 \cdot \bar{\boldsymbol v} \right \vert_{\Gamma_v} \\
\int_\Omega \frac{a^{33}}{EI} (\delta M \boldsymbol a_3) \cdot (M \boldsymbol a_3) d\Omega - \left . (\delta M \boldsymbol a_3)_{,1} \cdot \boldsymbol v \right \vert_{\Gamma_t} + \left . \delta M \boldsymbol a_3 \cdot \boldsymbol v_{,1} \right \vert_{\Gamma_M} + \int_\Omega (\delta M \boldsymbol a_3)_{,11} \cdot \boldsymbol v d\Omega &= \left . (\delta M \boldsymbol a_3)_{,1} \cdot \bar{\boldsymbol v} \right \vert_{\Gamma_v} - \left . \delta M \boldsymbol a_3 \cdot \boldsymbol a^3 \bar \theta \right \vert_{\Gamma_\theta} \\
- \left . \delta \boldsymbol v \cdot (\boldsymbol a_1 N + (\boldsymbol a_3 M)_{,1}) \right \vert_{\Gamma_t} + \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 M \right \vert_{\Gamma_M} + \int_\Omega \delta \boldsymbol v \cdot ((\boldsymbol a_1 N)_{,1} + (\boldsymbol a_3 M)_{,11}) d\Omega &= - \left . \delta \boldsymbol v \cdot \bar{\boldsymbol t} \right \vert_{\Gamma_t} + \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 \bar M \right \vert_{\Gamma_M} + \int_\Omega \delta \boldsymbol v \cdot \bar{\boldsymbol b} d\Omega
\end{align}
$$
or
$$
\int_\Omega \frac{a^{11}}{EA} (\delta N \boldsymbol a_1) \cdot (\boldsymbol a_1 N) d\Omega - \left . \delta N \boldsymbol a_1 \cdot \boldsymbol v \right \vert_{\Gamma} + \int_\Omega (\delta N \boldsymbol a_1)_{,1} \cdot \boldsymbol v d\Omega 
+ \left . \delta N \boldsymbol a_1 \cdot \boldsymbol v \right \vert_{\Gamma_v} = \left . \delta N \boldsymbol a_1 \cdot \bar{\boldsymbol v} \right \vert_{\Gamma_v}
$$
$$
\begin{multline}
\int_\Omega \frac{a^{33}}{EI} (\delta M \boldsymbol a_3) (M \boldsymbol a_3) d\Omega - \left . (\delta M \boldsymbol a_3)_{,1} \cdot \boldsymbol v \right \vert_{\Gamma} + \left . \delta M \boldsymbol a_3 \cdot \boldsymbol v_{,1} \right \vert_{\Gamma} + \int_\Omega (\delta M \boldsymbol a_3)_{,11} \cdot \boldsymbol v d\Omega \\ 
+ \left . (\delta M \boldsymbol a_3)_{,1} \cdot \boldsymbol v \right \vert_{\Gamma_v} - \left . \delta M \boldsymbol a_3 \cdot \boldsymbol a^3 \theta \right \vert_{\Gamma_\theta}
= \left . (\delta M \boldsymbol a_3)_{,1} \cdot \bar{\boldsymbol v} \right \vert_{\Gamma_v} - \left . \delta M \boldsymbol a_3 \cdot \boldsymbol a^3 \bar \theta \right \vert_{\Gamma_\theta}
\end{multline}
$$
$$
\begin{multline}
- \left . \delta \boldsymbol v \cdot (\boldsymbol a_1 N + (\boldsymbol a_3 M)_{,1}) \right \vert_{\Gamma} + \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 M \right \vert_{\Gamma} + \int_\Omega \delta \boldsymbol v \cdot ((\boldsymbol a_1 N)_{,1} + (\boldsymbol a_3 M)_{,11}) d\Omega \\
- \left . \delta \boldsymbol v \cdot (\boldsymbol a_1 N + (\boldsymbol a_3 M)_{,1}) \right \vert_{\Gamma_v} + \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 M \right \vert_{\Gamma_\theta}
= - \left . \delta \boldsymbol v \cdot \bar{\boldsymbol t} \right \vert_{\Gamma_t} + \left . \delta \boldsymbol v_{,1} \cdot \boldsymbol a_3 \bar M \right \vert_{\Gamma_M} + \int_\Omega \delta \boldsymbol v \cdot \bar{\boldsymbol b} d\Omega
\end{multline}
$$
