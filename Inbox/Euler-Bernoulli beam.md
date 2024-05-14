---
icon: OcInfinity16
---

#Elasticity/Beam 

strong form
$$
\left \{
\begin{array}{l}
(EIw_{,xx})_{,xx} = q & x\in\Omega \\
-EIw_{,xx} = M & x\;\mathrm on\;\Gamma^M \\
-(EIw_{,xx})_{,x} = V & x\;\mathrm on\;\Gamma^V \\
w_{,x} n_x = \theta & x\;\mathrm on\;\Gamma^\theta \\
w = g & x\;\mathrm on\;\Gamma^w \\
\end{array}
\right .
$$
dynamic Euler-Lagrange equation
$$
(EIw_{,xx})_{,xx} = - \mu \ddot w + q
$$
where $\mu$ is the mass per unit length.
Total energy
$$
\Pi(w) = \int_{t_1}^{t_2} \int_\Omega (\frac{1}{2}\mu \dot w^2 - \frac{1}{2}EIw_{,xx} + qw)dxdt
$$

$$
\delta \Pi(w) = \int_\Omega \mu \delta w \ddot w d\Omega + \int_\Omega \delta w_{,xx}EIw_{,xx} d\Omega -\int_{\Gamma^V}\delta w V d\Gamma + \int_{\Gamma^M} \delta w_{,x} n_x M d\Gamma - \int_\Omega wq d\Omega = 0
$$
# Approximation
plate deflection
$$
w^h = \sum_{I} N_I d_I
$$
equilibrium equation
$$
\boldsymbol M \boldsymbol a + \boldsymbol K \boldsymbol d = \boldsymbol f
$$
where
$$
M_{IJ} = \int_{\Omega} \mu N_I N_J d\Omega
$$
$$
K_{IJ} = \int_{\Omega} N_{I,xx} EI N_{J,xx} d\Omega
$$
$$
f_I = \int_{\Gamma^V} N_I Vd\Gamma - \int_{\Gamma^M} N_{I,x} n_x M d\Gamma + \int_{\Omega} N_I q d\Omega
$$

# Integration constraint
$$
\int_{\Omega}N_{I,xx} \boldsymbol q d\Omega = \int_{\Gamma} N_{I,x} n_x \boldsymbol q d\Gamma - \int_{\Gamma} N_I \boldsymbol q_{,x} n_x d\Gamma + \int_{\Omega} N_I \boldsymbol q_{,xx} d\Omega
$$
$$
f_{,x} = f_{,\xi} \xi_{,x} = - \frac{f_{,\xi}}{L}, \quad f_{,xx} = \frac{f_{,\xi\xi}}{L^2}
$$
$$
\int_{\Omega}N_{I,xx} \boldsymbol q d\Omega = \int_{\Gamma} N_{I,x} n_x \boldsymbol q d\Gamma + \int_{\Gamma} N_I \boldsymbol q_{,\xi} \frac{n_x}{L} d\Gamma + \frac{1}{L^2}\int_{\Omega} N_I \boldsymbol q_{,xx} d\Omega
$$
