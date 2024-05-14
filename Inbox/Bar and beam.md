---
icon: OcInfinity16
---

#Elasticity/Beam

# Constitutive relation
In bar or beam problem, the structure is stretched or compressed only in the axial direction. Assuming that $x$-axis is the axial direction, $z$-axis is the corresponding transverse direction, and $y$-axis is perpendicular to $x$- and $y$-axis. In accordance with [Poisson effect](https://en.wikipedia.org/wiki/Poisson%27s_ratio), the components of the strain tensor has the following relationship
$$
\varepsilon_{22} = \varepsilon_{33} = - \nu\varepsilon_{11}, \quad \varepsilon_{12} = \varepsilon_{23} = 0
$$
under this assumption and according to [[Elasticity#^9388fd|constitutive equation]], the stress components are given by
$$
\sigma_{11} = E \varepsilon_{11}, \quad \sigma_{13} = 2G\varepsilon_{13}, \quad \sigma_{22}=\sigma_{33}=\sigma_{12}=\sigma_{23}=0
$$
where $E$ and $G$ are the *Young's modulus* and *shearing modulus* respectively.
# Timoshenko-Ehrenfest beam
In Timoshenko beam theory, the displacement is assumed to be that
$$
u_1(\boldsymbol x) \approx u(x) - z \varphi(x), \quad u_2(\boldsymbol x) \approx 0, \quad u_3(\boldsymbol x) \approx w(x)
$$
where $u_i,i=1,2,3$ are the components of global displacement tensor, $u$ and $w$ are the displacement of mid-surface in $x-$ and $z-$direction respectively, and $\varphi$ is the angle of rotation of normal to the mid-surface of the beam. Under this circumstance, the components of strain tensor can be expressed as
$$
\varepsilon_{11} = \underbrace{u_{,x}}_\varepsilon - z \underbrace{\varphi_{,x}}_{-\kappa}, \quad \varepsilon_{13} = \frac{1}{2}\underbrace{(w_{,x} - \varphi)}_\gamma = \frac{1}{2}\gamma
$$
where $\varepsilon$, $\kappa$ and $\gamma$ are denoted as membrane strain, curvature and shearing strain respectively. And their expression is that
$$
\varepsilon = u_{,x},\quad \kappa = -\varphi_{,x},\quad \gamma = w_{,x} - \varphi
$$
Furthermore, the internal force in [[Elasticity#Galerkin formulation|Galerkin weak form]] can be rewritten as
$$
\begin{split}
\int_\Omega \delta \varepsilon_{ij}\sigma_{ij} d\Omega &= \int_{\Omega} \delta \varepsilon_{11}\sigma_{11} + 2\delta \varepsilon_{13}\sigma_{13} d\Omega \\
&= \int_0^L \int_A (\delta \varepsilon - z \delta \kappa)E(\varepsilon - z \kappa) + \delta \gamma k G \gamma dA dx \\
&= \int_0^L \delta \varepsilon EA \varepsilon dx + \int_0^L \delta \kappa EI \kappa dx + \int_0^L \delta \gamma kGA \gamma dx \\
&= \int_0^L \delta \varepsilon N dx + \int_0^L \delta \kappa M dx + \int_0^L \delta \gamma V dx
\end{split}
$$
where $N$,$M$ and $V$ are axial stress, bending moment and shear resultants, their expression is listed as follows
$$
N = EA \varepsilon, \quad M = EI \kappa, \quad V = kGA \gamma
$$
and the $A$ stands for the cross section. As the $xyz$ coordinate system is established on the mid-surface of beam, the integration along cross section means the moment of area, and can be evaluated by 
$$
\int_A dA = A,\quad \int_A z dA = 0,\quad \int_A z^2 dA = I
$$
where $I$ is the second moment of area.
Besides, the external force in weak form yields
$$
\int_{\Gamma_t} \delta u_i t_i d\Gamma + \int_{\Omega} \delta u_i b_i d\Omega = \delta u \bar N\vert_{x=x_N} - \delta \varphi \bar M \vert_{x=x_M} + \delta w \bar V \vert_{x=x_V} + \int_0^L \delta u b - \delta w q dx \\
$$
with a combination of internal force and external force and the arbitrariness of $\delta u, \delta w, \delta \varphi$, the Galerkin weak form can be expressed as
$$
\begin{align}
\int_0^L \delta \varepsilon N dx &= \delta u \bar N\vert_{x=x_N} + \int_0^L \delta u b dx \\
\int_0^L \delta \kappa M dx + \int_0^L \delta \gamma V dx &= \delta w \bar V \vert_{x=x_V} - \delta \varphi \bar M \vert_{x=x_M} - \int_0^L \delta w q dx
\end{align}
$$
using the integration by parts leads to
$$
\begin{multline}
\int_0^L \delta u (N_{,x}+b) + \delta w (V_{,x}-q) + \delta \varphi (V-M_{,x}) dx \\ - \delta u (N-\bar N) \vert_{x=x_N} - \delta w(V-\bar V) \vert_{x=x_V} + \delta \varphi (M-\bar M) \vert_{x=x_M} = 0
\end{multline}
$$
with the arbitrariness of $\delta u, \delta w, \delta \varphi$ and the essential boundaries, the strong form of bar and beam problem can be given by
- Bar

$$
\begin{cases}
N_{,x}+b = 0 & x\in (0,L) \\
N=\bar N & x = x_N \\
u=\bar u & x = x_u \\
\end{cases}
$$

- Beam

$$
\begin{cases}
V_{,x} = q & x\in (0,L) \\
M_{,x} = V & x\in (0,L) \\
V=\bar V & x = x_V \\
M=\bar M & x = x_M \\
w=\bar w & x = x_w \\
\varphi=\bar \varphi & x = x_\varphi \\
\end{cases}
$$

# Euler-Bernoulli beam
In Euler-Bernoulli theory, the shear deformation of Timoshenko beam has been varnished, and then the rotation $\varphi$ can be expressed by deflection $w$ as
$$
\gamma = 0 \Rightarrow \varphi = w_{,x}
$$
substituting it into curvature leads to
$$
\kappa = - w_{,xx}
$$
and the corresponding bending moment can be rewritten as
$$
M = - EI w_{,xx}
$$
plugging the new curvature and bending moment into the strong form and weak form of Timoshenko beam can rephrase them to that of Euler beam.

# Curved beam
![[Curved beam]]
