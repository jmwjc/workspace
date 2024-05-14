---
icon: OcInfinity16
---
 #Hyperelasticity/SaintVenant-Kirchhoff #Group/褚英杰

# Kinematics
For 1D case, the spatial coordinate $x$ is depicted by material coordinate $X$ and displacement $u$
$$
x = X + u
$$
the corresponding **deformation gradient**, **right Cauchy-Green tensor** and **Green-Lagrangian strain** have the following forms
$$
F = \frac{\partial x}{\partial X} = 1+u_{,X}
$$
$$
C = F^2 = u_{,X}^2 + 2u_{,X} + 1
$$
$$
E = \frac{1}{2}(C-1) = u_{,X} + \frac{1}{2}u_{,X}^2
$$

# Weak form
For **Saint Venant-Kirchhoff** material in 1D case, the energy density functional is given by
$$
W(E) = \frac{1}{2} E^{SE} E^2
$$
where $E^{SE}$ is **Young's module**, and the PK2 stress and its derivative yield
$$
S = \frac{\partial W}{\partial E} = E^{SE} E
$$
$$
\Delta S = E^{SE} \Delta E
$$
The potential energy functional of this system has the form that
$$
\Pi(u) = \int_{\Omega}\frac{1}{2}E^{SE}E^2 d\Omega - \int_{\Gamma^t}utd\Gamma - \int_{\Omega}ubd\Omega
$$
after a variation referring to $E$, the weak form can be got as
$$
\delta \Pi(u) = \int_{\Omega}\delta E E^{SE} E d\Omega - \int_{\Gamma^t} \delta utd\Gamma - \int_{\Omega}\delta ubd\Omega = 0
$$
where
$$
\delta E = F\delta u_{,X}
$$

# Approximation
The displacement can be discretized by nodal coefficients $d_I$'s and their shape functions $N_I$'s
$$
u = \sum_{I=1}^{n_p} N_I d_I, \quad u_{,X} = \sum_{I=1}^{n_p} N_{I,X} d_I
$$
where $n_p$ is total number of discrete nodes. Therefor, the linearized Green-Lagrangian strain can be rewritten as
$$
\Delta E = (1+u_{,X}) \Delta u_{,X} = F \Delta u_{,X} = F\sum_{I=1}^{n_p} N_{I,X} \Delta d_I
$$
$$
\begin{split}
\Delta \int_{\Omega} \delta E S d\Omega &= \int_{\Omega} \delta u_{,X} \Delta (FS) d\Omega \\
&= \int_{\Omega} \delta u_{,X} (\Delta F S + F \Delta S) d\Omega \\
&= \int_{\Omega} \delta u_{,X} (\Delta u_{,X} S + F^2 E^{SE} \Delta u_{,X}) d\Omega \\
&= \int_{\Omega} \delta u_{,X} (S + F^2 E^{SE}) \Delta u_{,X} d\Omega \\
\end{split}
$$
For $n$th time step and $i$th iteration step in **Newton's iteration**, we input the nodal coefficients of displacement $d_{I}(n,i)$'s and the prescribed variables $t_{n+1}$, $b_{n+1}$, and solve the increased nodal coefficients $\Delta d_I(n,i)$. The discrete equilibrium equation is given by
$$
\boldsymbol K_{n,i} \Delta \boldsymbol d_{n,i} = \boldsymbol f^{ext}_{n+1} - \boldsymbol f^{int}_{n,i}
$$
in which
$$
K_{IJ} = \int_{\Omega} N_{I,X} (S(u_{n,i}) + F^2(u_{n,i}) E^{SE}) N_{J,X} d\Omega
$$
$$
f^{int}_I = \int_{\Omega} N_{I,x}E^{SE}F(u_{n,i})E(u_{n,i})d\Omega
$$
$$
f^{ext}_I = \int_{\Gamma^t} N_I t d\Gamma + \int_{\Omega} N_I bd\Omega
$$

$$
F = 1 + \sum_{I=1}^{n_p} \Psi_{I,X} d_I
$$
