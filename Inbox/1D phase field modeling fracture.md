---
icon: OcInfinity16
---


#Formulation/PhaseField 

Consider a bar with the length $L$, the equilibrium equation of this problem is given by
$$
\left \{
\begin{array}{l,l}
&(EAu_{,x})_{,x} + b = 0 & \text{in} \; \Omega \\
&u = g & \text{on} \; \Gamma^g \\
&u_{,x} = t & \text{on} \; \Gamma^t \\
\end{array}
\right .
$$
where $E$ is the Young's modulus, $A$ is the area of cross section, $b$ stands for the body force. $\Gamma^g$ and $\Gamma^t$ are essential and natural boundary conditions, and $g$, $t$ are the prescribed variables on these boundaries. 
Introduce the phase field model to depict the fracture in the bar, the total potential energy is stated as
$$
\Pi(u,v) = \mathcal{P}(u,v) + \mathcal{D}(v) - \mathcal{F}(u)
$$
where
$$
\begin{align}
\mathcal{P}(u,v) &= \int_\Omega(v^2 + \eta) W(u) d\Omega \\
&= \int_\Omega(v^2 + \eta) \frac{1}{2} u_{,x}^2 d\Omega
\end{align}
$$
$$
\mathcal{D}(v) = \int_{\Omega} k(\frac{(1-v)^2}{4l} + l v_{,x}^2) d\Omega
$$
$$
\mathcal{F}(u) = \int_{\Gamma^t} ut d\Gamma + \int_\Omega ub d\Omega
$$
in which $\mathcal{P}$, $W$ denote the potential energy and its density, $\mathcal{F}$ is the external energy, $\mathcal{D}$ is dissipation energy raised by crack and $k$ is the corresponding density.
With a variational operation, the weak form can be obtained as
$$
\int_\Omega (v^2+\eta) \delta u_{,x} u_{,x} d\Omega = \int_{\Gamma^t} \delta ut d\Gamma + \int_{\Omega} \delta ub d\Omega
$$
$$
\int_\Omega k(2l\delta v_{,x} v_{,x} + \frac{\delta v v}{2l}) + 2\delta v v W(u) d\Omega = \int_{\Omega} \delta v \frac{k}{2l}d\Omega
$$
Leading the finite element formulation to approximate $u$ and $v$ as
$$
u^h(x) = \sum_{I=1}^{n_p} N_I(x)u_I,\quad v^h(x) = \sum_{I=1}^{n_p} N_I(x)v_I
$$
Substituting them to the weak form can get the discrete equilibrium equation
$$
\begin{align}
&\boldsymbol{K}^u(v)\boldsymbol{u} = \boldsymbol{f}^u \\
&\boldsymbol{K}^v \boldsymbol{v} = \boldsymbol{f}^v(u)
\end{align}
$$
where the components of above matrices and vectors evaluated by
$$
K^u_{IJ} = \int_\Omega (v^2 + \eta) N_{I,x} N_{J,x} d\Omega
$$
$$
f^u_{I} = \int_{\Gamma^t} N_I t d\Gamma + \int_\Omega N_I b d\Omega
$$
$$
K^v_{IJ} = \int_\Omega k(2l N_{I,x} N_{J,x} + \frac{ N_I N_J}{2l}) + 2W(u)N_I N_J d\Omega
$$
$$
f^v_I = \int_{\Omega} N_I \frac{k}{2l}d\Omega
$$
Due to the non-convex of the above system, the alternative iteration procedure is used herein to solve the nonlinear equations, for the step $n+1$, we have
$$
\begin{align}
&\boldsymbol{K}^u(v_n) \boldsymbol{u}_{n+1} = \boldsymbol{f}^u \\
&\boldsymbol{K}^v(u_{n+1}) \boldsymbol{v}_{n+1} = \boldsymbol{f}^v
\end{align}
$$
