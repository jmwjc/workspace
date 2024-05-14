---
icon: OcInfinity16
---

#Formulation/Hellinger-Reissner #Elasticity/Plate/Thin-plate #Hyperelasticity 
# [[Elasticity|Linear Elasticity]]

Consider the following strong form:
$$
\left \{
\begin{array}{ll}
    \sigma_{ij,j} + b_{i} = 0 & \text{on} \; \Omega \\
    \sigma_{ij}n_{j} = t_{i} & \text{in} \; \Gamma^t \\
    u_i  = g_i & \text{in} \; \Gamma^g
\end{array}
\right .
$$
the Hellinger-Reissner complementary energy functional is given by:
$$
\Pi(\sigma_{ij}) = \int_\Omega W(\sigma_{ij}) d\Omega - \int_{\Gamma^g} \sigma_{ij}n_{j}g_{i} d\Gamma
$$
where $W$ is the energy density, stress and strain has the following relation:
$$
\frac{\partial W}{\partial \sigma_{ij}} = \frac{1}{2}(u_{i,j} + u_{j,i})
$$
the external force and body force are applied by Lagrangian multipliers as:
$$
\begin{align}
    \bar{\Pi}(\sigma_{ij},u_i) &= \Pi(\sigma_{ij}) + \int_{\Omega} u_i (\sigma_{ij,j} + b_i) d\Omega - \int_{\Gamma^t} u_i(\sigma_{ij}n_j-t_i)d\Gamma \\
    &= \int_\Omega W(\sigma_{ij}) d\Omega - \int_{\Gamma^g} \sigma_{ij}n_{j}g_{i} d\Gamma  + \int_{\Omega} u_i (\sigma_{ij,j} + b_i) d\Omega - \int_{\Gamma^t} u_i(\sigma_{ij}n_j-t_i)d\Gamma
\end{align}
$$
with variational operator, the weak form can be expressed as:
$$
\begin{multline}
    \delta \bar{\Pi}(\sigma_{ij},u_i) = \int_{\Omega} \delta \sigma_{ij} \frac{\partial W}{\partial \sigma_{ij}} d\Omega - \int_{\Gamma^g} \delta \sigma_{ij}n_j g_i d\Gamma + \int_{\Omega} \delta \sigma_{ij,j} u_i d\Omega - \int_{\Gamma^t} \delta \sigma_{ij}n_j u_i d\Gamma \\
    + \int_{\Omega} \delta u_i (\sigma_{ij,j} + b_i) d\Omega - \int_{\Gamma^t} \delta u_i(\sigma_{ij}n_j-t_i)d\Gamma
\end{multline}
$$
# Incompressible Linear Elasticity
Consider an [[Elasticity|isotropic elasticity material]], the stress can be divided into hydrostatic pressure and deviatoric stress as
$$
\sigma_{ij} = \frac{1}{3}p \delta_{ij} + s_{ij}
$$
its strong form of equilibrium equation is given by
$$
\left \{
\begin{array}{l}
\sigma_{ij,j} + b_i = \frac{1}{3}p_{,i} + s_{ij,j} + b_i = 0 & \mathrm{in} \; \Omega \\
u_i = g_i & \mathrm{on} \Gamma^g \\
\sigma_{ij} n_j = t_i & \mathrm{on} \Gamma^t \\
\end{array}
\right .
$$
where $K$ is the bulking modulus. The corresponding complementary energy functional can be expressed as
$$
\begin{split}
\Pi(s_{ij},p) &= \int_{\Omega}\frac{1}{2}\sigma_{ij}C_{ijkl}^{-1}\sigma_{kl} d\Omega - \int_{\Gamma^g} (\frac{1}{3}p\delta_{ij}+s_{ij}) n_j g_i d\Gamma \\
&= \int_{\Omega}\frac{1}{2}(\frac{1}{3}p\delta_{ij}+s_{ij})C_{ijkl}^{-1}(\frac{1}{3}p\delta_{kl}+s_{kl}) d\Omega - \int_{\Gamma^g} \sigma_{ij} n_j g_i d\Gamma \\
&= \int_{\Omega}\frac{1}{2}\frac{s_{ij}s_{ij}}{2\mu} d\Omega + \int_{\Omega} \frac{1}{2}\frac{p^2}{9K} d\Omega - \int_{\Gamma^g} \sigma_{ij} n_j g_i d\Gamma
\end{split}
$$
where
$$
\begin{split}
C_{ijkl} &= \lambda \delta_{ij}\delta_{kl} + \mu(\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk}) \\
&= (\lambda+\frac{2\mu}{3})\delta_{ij}\delta_{kl} + 2\mu(\frac{1}{2}(\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk})-\frac{1}{3}\delta_{ij}\delta_{kl}) \\
&= 3K (\frac{1}{3}\delta_{ij}\delta_{kl}) + 2\mu(\frac{1}{2}(\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk})-\frac{1}{3}\delta_{ij}\delta_{kl}) \\
&= C_{ijkl}^{vol} + C_{ijkl}^{dev} \\
\end{split}
$$
$$
C_{ijkl}^{vol} = 3K (\frac{1}{3}\delta_{ij}\delta_{kl}), \quad C_{ijkl}^{dev} = 2\mu(\frac{1}{2}(\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk})-\frac{1}{3}\delta_{ij}\delta_{kl})
$$
plugging the strong form regarding as constraint, the weak form can be rephrased as
$$
\begin{split}
\Pi(s_{ij},p,u_i) &= \int_{\Omega}\frac{1}{2}\frac{s_{ij}s_{ij}}{2\mu} d\Omega
+ \int_{\Omega}\frac{1}{2} \frac{p^2}{3K} d\Omega - \int_{\Gamma^g} (\frac{1}{3}p\delta_{ij}+s_{ij}) n_j g_i d\Gamma \\
&+ \int_{\Omega} u_i (\frac{1}{3}p_{,i}+s_{ij,j}+b_i) d\Omega \\
&- \int_{\Gamma^t} u_i ((\frac{1}{3}p\delta_{ij}+s_{ij})n_j-t_i) d\Gamma \\
\end{split}
$$
leading a standard variational argument regarding above functional gives follows
$$
\int_{\Omega}\frac{1}{2\mu}\delta s_{ij}s_{ij}d\Omega - \int_{\Gamma} \delta s_{ij} n_j u_i d\Gamma + \int_{\Omega} \delta s_{ij,j} u_i d\Omega + \int_{\Gamma^g} \delta s_{ij} n_j u_i d\Gamma = \int_{\Gamma^g} \delta s_{ij} n_j g_i d\Gamma
$$
$$
\int_{\Omega} \frac{1}{K} \delta p p d\Omega - \int_{\Gamma} \delta p n_i u_i d\Gamma + \int_{\Omega} \delta p_{,i} u_i d\Omega + \int_{\Gamma^g} \delta p n_i u_i d\Gamma = \int_{\Gamma^g} \delta p n_i g_i d\Gamma
$$
$$
\int_{\Gamma} \delta u_i s_{ij}n_jd\Gamma - \int_{\Omega} \delta u_i s_{ij,j} d\Omega
+\frac{1}{3}\int_{\Gamma} \delta u_i pn_id\Gamma - \frac{1}{3}\int_{\Omega} \delta u_i p_{,i} d\Omega 
-\int_{\Gamma^g} \delta u_i s_{ij}n_jd\Gamma - \frac{1}{3}\int_{\Gamma^g} \delta u_i pn_id\Gamma =
\int_{\Gamma^t} \delta u_i t_i d\Gamma + \int_{\Omega} \delta u_i b_i d\Omega
$$


# [[Kirchhoff-Love Plate|Kirchhoff-Love Plate]]

Consider the strong form of Kirchhoff-Love plate:
$$
\left \{
\begin{array}{ll}
    M_{\alpha \beta, \alpha \beta} = \bar{q} & \text{in} \; \Omega \\
    w = \bar{w} & \text{on} \; \Gamma^w \\
    w_{,\alpha} n_{\alpha} = \bar{\theta}_\boldsymbol{n} & \text{on} \; \Gamma^{\theta} \\
    Q_\boldsymbol{n} + M_{\boldsymbol{ns},\boldsymbol{s}} = \bar{V}_\boldsymbol{n} & \text{on} \; \Gamma^{V} \\
    M_{\boldsymbol{nn}} = \bar{M}_{\boldsymbol{nn}} & \text{on} \; \Gamma^{M} \\
\end{array}
\right .
$$
where
$$
Q_{\boldsymbol{n}} = M_{\alpha \beta, \beta} n_{\alpha}, \qquad M_{\boldsymbol{nn}} = M_{\alpha \beta} n_\alpha n_\beta, \qquad M_{\boldsymbol{ns},\boldsymbol{s}} = M_{\alpha \beta, \gamma}s_{\alpha} n_{\beta} s_{\gamma}
$$
and the $n_{\alpha}$ and $s_{\alpha}$ are the components of outward normal and tangential vectors, and the following relation holds true:
$$
\delta_{\alpha \beta} = n_{\alpha}n_{\beta} + s_{\alpha}s_{\beta}
$$
the Hellinger-Reissner complementary energy functional lists as follow:
$$
\begin{multline}
    \Pi(M_{\alpha \beta}) = \int_{\Omega} \frac{1}{2D(1-\nu^2)}((M_{11} + M_{22})^2 + 2(1+\nu)(M^2_{12}-M_{11}M_{22}))d\Omega \\
    - \int_{\Gamma^w}\bar{w} (Q_{\boldsymbol{n}} + M_{\boldsymbol{ns},\boldsymbol{s}}) d\Gamma + \int_{\Gamma^\theta} \bar{\theta}_{\boldsymbol{n}} M_{\boldsymbol{nn}}d\Gamma
\end{multline}
$$
in which, the relation of $\bar{\theta}_{\boldsymbol{s}} = w_{,\alpha}s_{\alpha} = 0$ is embedded. Follow the same path, the external force and body force are applied by Lagrangian multipliers:
$$
\begin{align}
    \bar{\Pi}(M_{\alpha \beta}) = \Pi(M_{\alpha \beta}) + \int_{\Omega} w(M_{\alpha \beta, \alpha \beta} + \bar{q})d\Omega + \int_{\Gamma^M}w_{,\boldsymbol{n}}(M_{\boldsymbol{nn}} - \bar{M}_{\boldsymbol{nn}})d\Gamma - \int_{\Gamma^V} w(V_{\boldsymbol{n}} - \bar{V}_{\boldsymbol{n}})d\Gamma
\end{align}
$$
the corresponding weak form can be gotten by:
$$
\begin{align}
\delta \bar{\Pi}(M_{\alpha \beta}) &= \int_{\Omega} \delta M_{\alpha \beta} \frac{\partial W}{\partial M_{\alpha \beta}} d\Omega - \int_{\Gamma^w} (\delta Q_{\boldsymbol{n}} + \delta M_{\boldsymbol{ns},\boldsymbol{s}}) \bar{w} d\Gamma + \int_{\Gamma^\theta} \delta M_{\boldsymbol{nn}} \bar{\theta}_{\boldsymbol{n}} d\Gamma \\
&+ \int_{\Omega} \delta M_{\alpha \beta,\alpha \beta} w d\Omega + \int_{\Gamma^M} \delta M_{\boldsymbol{nn}} w_{,\boldsymbol{n}} d\Gamma - \int_{\Gamma^V} (\delta Q_{\boldsymbol{n}} + \delta M_{\boldsymbol{ns},\boldsymbol{s}}) w d\Gamma \\
&+ \int_{\Omega} \delta w M_{\alpha \beta,\alpha \beta} d\Omega + \int_{\Gamma^M} \delta w_{,\boldsymbol{n}} M_{\boldsymbol{nn}} d\Gamma - \int_{\Gamma^V} \delta w (Q_{\boldsymbol{n}} + M_{\boldsymbol{ns},\boldsymbol{s}}) d\Gamma \\
&+ \int_{\Omega} \delta w \bar{q} d\Omega - \int_{\Gamma^M} \delta w_{,\boldsymbol{n}} \bar{M}_{\boldsymbol{nn}} d\Gamma + \int_{\Gamma^V} \delta w \bar{V}_{\boldsymbol{n}} d\Gamma
\end{align}
$$

# [[Hyperelasticity|Hyperelasticity]]
The complementary energy for the hyperelasticity material is almost identical with linear elasticity material, the only difference is that the external force is applied regarding spatial coordinates
$$
\Pi(S_{IJ},u_i) = \int_{\Omega} W(E_{IJ}) d\Omega - \int_{\Gamma^g} F_{iI} S_{IJ} n_J g_i d\Gamma + \int_{\Omega} u_i (F_{iI}S_{IJ,J} + b_i) d\Omega - \int_{\Gamma^t} u_i(F_{iI}S_{IJ}n_J-t_i)d\Gamma
$$
$$
\Pi(S_{IJ},u_i) = \int_{\Omega} W(E_{IJ}) d\Omega - \int_{\Gamma^g} P_{iI} n_I g_i d\Gamma + \int_{\Omega} u_i (P_{iI,I} + b_i) d\Omega - \int_{\Gamma^t} u_i(P_{iI}n_I-t_i)d\Gamma
$$
invoking the standard variation argument leads to
$$
\begin{split}
\delta \Pi(S_{IJ},u_i) &= \int_{\Omega} \delta S_{IJ} \frac{\partial W}{\partial S_{IJ}} d\Omega
- \int_{\Gamma^g}\delta P_{iI}n_I g_i d\Gamma + \int_{\Omega} \delta P_{iI}n_I u_i d\Omega
- \int_{\Gamma^t} \delta P_{iI}n_I u_i d\Gamma \\
&+\int_{\Omega} \delta u_i (P_{iI,I} + b_i) d\Omega - \int_{\Gamma^t} \delta u_i(P_{iI}n_I-t_i)d\Gamma \\
&= 0
\end{split}
$$
$$
\int_{\Omega} \delta P_{iI}F_{Ji}^{-1} \frac{\partial W}{\partial S_{IJ}} d\Omega - \int_{\Gamma} \delta P_{iI} n_I u_i d\Gamma + \int_{\Omega} \delta P_{iI,I} u_i d\Omega + \int_{\Gamma^g} \delta P_{iI} n_I u_i d\Gamma = \int_{\Gamma^g} \delta P_{iI} n_I g_i d\Gamma
$$
$$
\int_{\Gamma} \delta u_i F_{iI} S_{IJ} n_J d\Gamma - \int_{\Omega} \delta u_i F_{iI} S_{IJ,J} d\Omega - \int_{\Gamma^g} \delta u_i F_{iI} S_{IJ} n_J d\Gamma = \int_{\Gamma} \delta u_i t_i d\Gamma + \int_{\Omega} \delta u_i b_i d\Omega
$$
Variation argument regarding $S_{IJ}$ and $u_i$:
$$
\begin{split}
\delta \Pi(S_{IJ},u_i) &= \int_{\Omega} \delta S_{IJ} \frac{\partial W}{\partial S_{IJ}} d\Omega
- \int_{\Gamma^g}\delta P_{iI}n_I g_i d\Gamma + \int_{\Omega} \delta P_{iI}n_I u_i d\Omega
- \int_{\Gamma^t} \delta P_{iI}n_I u_i d\Gamma \\
&+\int_{\Omega} \delta u_i (P_{iI,I} + b_i) d\Omega - \int_{\Gamma^t} \delta u_i(P_{iI}n_I-t_i)d\Gamma \\
&= 0
\end{split}
$$
