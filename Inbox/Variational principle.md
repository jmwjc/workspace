---
icon: OcInfinity16
---

#Math/FunctionalAnalysis #Formulation/Galerkin  

# Potential energy and complementary energy
The *weakly* numerical formulations is a class of methods that constructed via variational functional. All of the current variational principles is based upon potential energy or complementary energy.

**Potential energy** is a functional referring to displacement $\boldsymbol u$
$$
\Pi(\boldsymbol u) = \int_{\Omega} \frac{1}{2} \boldsymbol \sigma : \boldsymbol \varepsilon d\Omega - \int_{\Gamma^t} \boldsymbol u \cdot \boldsymbol t d\Gamma - \int_{\Omega} \boldsymbol u \cdot \boldsymbol b d\Omega
$$
where the displacement essential boundary condition is lost in potential energy.

**Complementary energy** is a functional referring to stress $\boldsymbol \sigma$
$$
\Pi(\boldsymbol \sigma) = \int_{\Omega} \frac{1}{2} \boldsymbol \sigma : \boldsymbol \varepsilon d\Omega - \int_{\Gamma^g} \boldsymbol n \cdot \boldsymbol \sigma \cdot \boldsymbol u d\Gamma
$$
on the contrary, the traction and body force is not concluded in complementary energy.

For clarity, the potential energy and complementary energy of potential problem are listed as follows

**Potential energy**
$$
\Pi(u) = \int_{\Omega} \frac{1}{2}u_{,i}^2 d\Omega - \int_{\Gamma^t} ut d\Gamma - \int_{\Omega}ubd\Omega
$$

**Potential energy with Lagrangian multiplier**
$$
\Pi(u,\lambda) = \int_{\Omega} \frac{1}{2}u_{,i}^2 d\Omega - \int_{\Gamma^t} ut d\Gamma - \int_{\Omega}ubd\Omega - \int_{\Gamma^g} \lambda (u-g) d\Gamma
$$

**Modified variational principle**
$$
\Pi(u) = \int_{\Omega} \frac{1}{2}u_{,i}^2 d\Omega - \int_{\Gamma^t} ut d\Gamma - \int_{\Omega}ubd\Omega - \int_{\Gamma^g}u_{,i} n_i(u-g) d\Gamma
$$
$$
\begin{split}
\delta\Pi(u) &= \int_{\Omega} \delta u_{,i}u_{,i} d\Omega - \int_{\Gamma^t} \delta ut d\Gamma - \int_{\Omega}\delta ubd\Omega - \int_{\Gamma^g}\delta u_{,i} n_i u d\Gamma - \int_{\Gamma^g}\delta u u_{,i} n_i d\Gamma + \int_{\Gamma^g}\delta u_{,i} n_i g d\Gamma \\
&= \int_{\Omega} \delta u_{,i}u_{,i} d\Omega - \int_{\Gamma} \delta uu_{,i}n_i d\Gamma + \int_{\Omega} \delta uu_{,ii} d\Omega\\
&- \int_{\Gamma^g}\delta u_{,i} n_i (u-g) d\Gamma + \int_{\Gamma^t} \delta u(u_{,i}n_i-t) d\Gamma - \int_{\Omega}\delta u(u_{,ii}+b)d\Omega \\
\end{split}
$$

**Complementary energy**
$$
\Pi(s) = \int_{\Omega} \frac{1}{2}s_i^2 d\Omega - \int_{\Gamma^g} s_i n_i g d\Gamma
$$

**Hellinger-Reissner principle**
$$
\Pi(s,u) = \int_{\Omega} \frac{1}{2}s_i^2 d\Omega - \int_{\Gamma^g} s_i n_i g d\Gamma - \int_{\Gamma^t} u(s_i n_i - t)d\Gamma + \int_{\Omega} u(s_{i,i}+b) d\Omega
$$
$$
\begin{split}
\delta \Pi(s,u) &= \int_{\Omega} \delta s_i s_i d\Omega - \int_{\Gamma^g} \delta s_i n_i g d\Gamma - \int_{\Gamma^t} \delta us_id\Gamma - \int_{\Gamma^t} \delta s_i n_i ud\Gamma + \int_{\Gamma^t} \delta utd\Gamma + \int_{\Omega} \delta \delta us_{i,i} d\Omega + \int_{\Omega} \delta s_{i,i}u d\Omega + \int_{\Omega} \delta ub d\Omega \\
&= \int_{\Omega} \delta s_i s_i d\Omega - \int_{\Gamma} \delta s_i n_i u d\Gamma + \int_{\Omega} \delta s_{i,i} u d\Omega \\
&+ \int_{\Gamma^g} \delta s_i n_i (u-g) d\Gamma - \int_{\Gamma^t} \delta u(s_i n_i -t)d\Gamma + \int_{\Omega} \delta u(s_{i,i}+b) d\Omega
\end{split}
$$

# (test::Mixed variational functional)
(data::2023-02-07)
$$
\begin{multline}
\int_{\Omega} \delta u_{,i}u_{,i} d\Omega - \int_{\Gamma} \delta us_in_i d\Gamma + \int_{\Omega} \delta us_{i,i} d\Omega \\
+ \int_{\Gamma^t} \delta us_in_i d\Gamma - \int_{\Omega} \delta us_{i,i} d\Omega =
\int_{\Gamma^t} \delta ut d\Gamma + \int_{\Omega}\delta ubd\Omega \\
\end{multline}
$$
$$
\int_{\Omega} \delta s_i s_i d\Omega - \int_{\Gamma} \delta s_i n_i u d\Gamma + \int_{\Omega} \delta s_{i,i} u d\Omega + \int_{\Gamma^g} \delta s_i n_i u d\Gamma = \int_{\Gamma^g} \delta s_i n_i g d\Gamma
$$
