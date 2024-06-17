---
icon: OcInfinity16
---


#Incompressible #Formulation/Hellinger-Reissner  

# Three variables

The energy functional of Hellinger-Reissner principle
$$
\Pi(s_{ij},p,u_i) = \int_\Omega\frac{1}{2}\sigma_{ij}C_{ijkl}^{-1}\sigma_{kl}d\Omega - \int_{\Gamma_g} \sigma_{ij} n_j g_i d\Gamma - \int_{\Gamma_t} u_i (\sigma_{ij}n_j - t_i) d\Gamma + \int_\Omega u_i (\sigma_{ij,j} + b_i) d\Omega
$$

Stress decomposition
$$
\sigma_{ij} = p \delta_{ij} + s_{ij}
$$
where
$$
p =\frac{1}{3} \sigma_{kk}, \quad s_{ij} = \sigma_{ij} -\frac{1}{3} \sigma_{kk} \delta_{ij}
$$
$$
C_{ijkl}^{-1} =  -\frac{\nu}{E} \delta_{ij}\delta_{kl} + \frac{1+\nu}{2E} (\delta_{ik}\delta_{jl} + \delta_{il}\delta_{jk})
$$

Internal energy
$$
\begin{split}
\int_\Omega\frac{1}{2} \sigma_{ij} C^{-1}_{ijkl} \sigma_{kl} d\Omega &=
\int_\Omega\frac{1}{2} (p\delta_{ij} + s_{ij}) \left (
-\frac{\nu}{E} \delta_{ij}\delta_{kl} + \frac{1+\nu}{2E} (\delta_{ik}\delta_{jl} + \delta_{il}\delta_{jk})
\right ) (p\delta_{kl} + s_{kl}) d\Omega \\ &=
\int_\Omega\frac{1}{2}(\frac{3(1-2\nu)}{E} p^2 + \frac{1+\nu}{E} s_{ij} s_{ij}) d\Omega \\ &+
\int_\Omega\frac{1}{2} ( \frac{2(1-2\nu)}{E} ps_{ii} - \frac{\nu}{E} s_{ii}s_{jj} ) d\Omega \\ &=
\int_\Omega\frac{1}{2}(\frac{1}{K} p^2 +\frac{1}{2G} s_{ij} s_{ij} -\frac{\nu}{E}s_{ii}s_{jj} +\frac{2}{3K}ps_{ii}) d\Omega
\end{split}
$$

External energy
$$
\int_{\Gamma_g} \sigma_{ij} n_j g_i d\Gamma = \int_{\Gamma_g} (p\delta_{ij} + s_{ij}) n_j g_i d\Gamma
= \int_{\Gamma_g} (p n_i g_i + s_{ij} n_j g_i) d\Gamma
$$
$$
\int_{\Gamma_t} u_i (\sigma_{ij}n_j - t_i) d\Gamma = \int_{\Gamma_t} u_i (p n_i + s_{ij} n_j - t_i) d\Gamma
$$
$$
\int_\Omega u_i (\sigma_{ij,j} + b_i) d\Omega = \int_\Omega u_i (p_{,i} + s_{ij,j} + b_i) d\Omega
$$

Weak form
$$
\int_\Omega\frac{1}{K}\delta p p d\Omega + \int_\Omega \frac{2}{3K} \delta p s_{ii} d\Omega - \int_{\Gamma_t} \delta p n_i u_i d\Gamma + \int_\Omega \delta p_{,i} u_i d\Omega = \int_{\Gamma_g} \delta p n_i g_i d\Gamma 
$$
$$
\int_\Omega \frac{1}{2G} \delta s_{ij} s_{ij} d\Omega - \int_\Omega\frac{\nu}{E} \delta s_{ii}s_{jj} d\Omega + \int_\Omega\frac{2}{3K} \delta s_{ii} p d\Omega - \int_{\Gamma_t} \delta s_{ij} n_j u_i d\Gamma + \int_\Omega \delta s_{ij,j} u_i d\Omega = \int_{\Gamma_g} \delta s_{ij} n_j g_i d\Gamma
$$
$$
- \int_{\Gamma_t} \delta u_i (p n_i + s_{ij} n_j) d\Gamma + \int_\Omega \delta u_i (p_{,i} + s_{ij,j}) d\Omega 
= - \int_{\Gamma_t} \delta u_i t_i d\Gamma - \int_\Omega \delta u_i b_i d\Omega
$$

First equation can be rephrased as
$$
\begin{split}
&\int_\Omega\frac{1}{K}\delta p p d\Omega + \int_\Omega \frac{2}{3K} \delta p s_{ii} d\Omega - \int_{\Gamma} \delta p n_i u_i d\Gamma + \int_\Omega \delta p_{,i} u_i d\Omega + \int_{\Gamma_g} \delta p n_i u_i d\Gamma = \int_{\Gamma_g} \delta p n_i g_i d\Gamma \\
\Rightarrow
&\int_\Omega\frac{1}{K}\delta p p d\Omega - \int_\Omega \delta p u_{i,i} d\Omega + \int_\Omega \frac{2}{3K} \delta p s_{ii} d\Omega + \int_{\Gamma_g} \delta p n_i u_i d\Gamma = \int_{\Gamma_g} \delta p n_i g_i d\Gamma \\
\end{split}
$$
Second equation
$$
\begin{split}
&\int_\Omega \frac{1}{2G} \delta s_{ij} s_{ij} d\Omega - \int_\Omega\frac{\nu}{E} \delta s_{ii}s_{jj} d\Omega + \int_\Omega\frac{2}{3K} \delta s_{ii} p d\Omega - \int_{\Gamma} \delta s_{ij} n_j u_i d\Gamma + \int_\Omega \delta s_{ij,j} u_i d\Omega + \int_{\Gamma_g} \delta s_{ij} n_j u_i d\Gamma = \int_{\Gamma_g} \delta s_{ij} n_j g_i d\Gamma \\
\Rightarrow
&\int_\Omega \frac{1}{2G} \delta s_{ij} s_{ij} d\Omega - \int_\Omega\frac{\nu}{E} \delta s_{ii}s_{jj} d\Omega + \int_\Omega\frac{2}{3K} \delta s_{ii} p d\Omega - \int_\Omega \delta s_{ij} \varepsilon_{ij} d\Omega + \int_{\Gamma_g} \delta s_{ij} n_j u_i d\Gamma = \int_{\Gamma_g} \delta s_{ij} n_j g_i d\Gamma \\
\end{split}
$$
Last equation
$$
- \int_\Omega \delta u_{i,i} p d\Omega - \int_\Omega \delta \varepsilon_{ij} s_{ij} d\Omega 
+ \int_{\Gamma_g} \delta u_i (p n_i + s_{ij} n_j) d\Gamma 
= - \int_{\Gamma_t} \delta u_i t_i d\Gamma - \int_\Omega \delta u_i b_i d\Omega
$$

## Plane strain
$$
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12}
\end{Bmatrix} = 
\frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu & \nu & 0 \\
\nu & 1-\nu & 0 \\
\nu & \nu & 0 \\
0 & 0 & \frac{1-2\nu}{2}
\end{bmatrix}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix}
$$
$$
\begin{split}
p &=\frac{1}{3} \sigma_{kk} =\frac{1}{3}\frac{E}{1-2\nu} (\varepsilon_{11} + \varepsilon_{22}) \\
&= \frac{E}{(1+\nu)(1-2\nu)}( \frac{1+\nu}{3} \varepsilon_{11} + \frac{1+\nu}{3} \varepsilon_{22} )
\end{split}
$$
$$
\begin{Bmatrix}
s_{11} \\ s_{22} \\ s_{33} \\ s_{12}
\end{Bmatrix} =\frac{E}{3(1+\nu)}
\begin{bmatrix}
2 & -1 & 0 \\
-1 & 2 & 0 \\
-1 & -1 & 0 \\
0 & 0 & \frac{1-2\nu}{2}
\end{bmatrix}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix}
$$

# Two variables

The energy functional of Hellinger-Reissner principle
$$
\Pi(p,u_i) = \int_\Omega\frac{1}{2}\sigma_{ij}C_{ijkl}^{-1}\sigma_{kl}d\Omega - \int_{\Gamma_g} \sigma_{ij} n_j g_i d\Gamma - \int_{\Gamma_t} u_i (\sigma_{ij}n_j - t_i) d\Gamma + \int_\Omega u_i (\sigma_{ij,j} + b_i) d\Omega
$$

Stress decomposition
$$
\sigma_{ij} = p \delta_{ij} + 2G e_{ij}
$$

Internal energy
$$
\int_\Omega\frac{1}{2} \sigma_{ij} C_{ijkl}^{-1} \sigma_{kl} d\Omega = \int_\Omega\frac{1}{2}(\frac{1}{K}p^2 + 2G e_{ij} e_{ij}) d\Omega
$$

External energy
$$
\int_{\Gamma_g} \sigma_{ij} n_j g_i d\Gamma = \int_{\Gamma_g} ( p\delta_{ij} + 2G e_{ij} ) n_j g_i d\Gamma
$$
$$
\int_{\Gamma_t} u_i (\sigma_{ij}n_j - t_i) d\Gamma = \int_{\Gamma_t} u_i( pn_i + 2Ge_{ij} n_j - t_i) d\Gamma
$$
$$
\int_\Omega u_i (\sigma_{ij,j} + b_i) d\Omega = \int_\Omega u_i (p_{,i} + 2Ge_{ij,j} + b_i) d\Omega
$$

Weak form
$$
- \int_\Omega\frac{1}{K} \delta p p d\Omega + \int_\Gamma \delta p n_i u_i d\Gamma - \int_\Omega \delta p_{,i} u_i d\Omega - \int_{\Gamma_g} \delta p n_i u_i d\Gamma = -\int_{\Gamma} \delta p n_i g_i d\Gamma
$$
$$
\int_\Omega \delta e_{ij} s_{ij} d\Omega + \int_\Omega \delta u_{i,i} p d\Omega
$$

# Test: Two variables
$$
\sigma_{ij} = p \delta_{ij} + \sigma_{ij} -\frac{1}{3} \sigma_{kk} \delta_{ij}
$$
$$
s_{ij} = \sigma_{ij} -\frac{1}{3} \sigma_{kk} \delta_{ij}
$$
$$
\int_\Omega\frac{1}{2} \sigma_{ij} C^{-1}_{ijkl} \sigma_{kl} d\Omega = \int_\Omega\frac{1}{2}(\frac{1}{K}p^2 +\frac{1}{2G}s_{ij}s_{ij}) d\Omega
$$

Weak form
$$
\int_\Omega\frac{1}{K}\delta p p d\Omega - \int_\Omega \delta p u_{i,i} d\Omega + \int_{\Gamma_g} \delta p n_i u_i d\Gamma = \int_{\Gamma_g} \delta p n_i g_i d\Gamma 
$$
$$
\int_\Omega \frac{1}{2G} \delta s_{ij} s_{ij} d\Omega - \int_\Omega \delta s_{ij} \varepsilon_{ij} d\Omega + \int_{\Gamma_g} \delta s_{ij} n_j u_i d\Gamma = \int_{\Gamma_g} \delta s_{ij} n_j g_i d\Gamma 
$$
$$
- \int_\Omega \delta u_{i,i} p d\Omega - \int_\Omega \delta \varepsilon_{ij} s_{ij} d\Omega 
+ \int_{\Gamma_g} \delta u_i (p n_i + s_{ij} n_j) d\Gamma 
= - \int_{\Gamma_t} \delta u_i t_i d\Gamma - \int_\Omega \delta u_i b_i d\Omega
$$

## Assembly
$$
\begin{Bmatrix}
s_{11} \\ s_{22} \\ s_{33} \\ s_{12}
\end{Bmatrix} =
\begin{bmatrix}
  \frac{2}{3} & - \frac{1}{3} & - \frac{1}{3} & 0 \\
- \frac{1}{3} &   \frac{2}{3} & - \frac{1}{3} & 0 \\
- \frac{1}{3} & - \frac{1}{3} &   \frac{2}{3} & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12}
\end{Bmatrix}
$$
$$
\int_\Omega\frac{1}{2G} \delta s_{ij} s_{ij} d\Omega = \int_\Omega
\begin{Bmatrix}
\delta \sigma_{11} \\ \delta \sigma_{22} \\ \delta \sigma_{33} \\ \delta \sigma_{12}
\end{Bmatrix}
\begin{bmatrix}
  \frac{4}{9} & -\frac{2}{9} & -\frac{2}{9} & 0 \\
 -\frac{2}{9} &  \frac{4}{9} & -\frac{2}{9} & 0 \\
 -\frac{2}{9} & -\frac{2}{9} &  \frac{4}{9} & 0 \\
 0 & 0 & 0 & 2
\end{bmatrix}
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12}
\end{Bmatrix} d\Omega
$$
$$
\int_\Omega \delta s_{ij} \varepsilon_{ij} d\Omega = \int_\Omega
\begin{Bmatrix}
\delta \sigma_{11} \\ \delta \sigma_{22} \\ \delta \sigma_{33} \\ \delta \sigma_{12}
\end{Bmatrix}
\begin{bmatrix}
  \frac{2}{3} \frac{\partial}{\partial x} & - \frac{1}{3} \frac{\partial}{\partial y} \\
- \frac{1}{3} \frac{\partial}{\partial x} &   \frac{2}{3} \frac{\partial}{\partial y} \\
- \frac{1}{3} \frac{\partial}{\partial x} & - \frac{1}{3} \frac{\partial}{\partial y} \\
\frac{\partial}{\partial y} & \frac{\partial}{\partial x}
\end{bmatrix}
\begin{Bmatrix}
u_1 \\ u_2
\end{Bmatrix}
d\Omega
$$ 
$$
\int_{\Gamma_g} \delta s_{ij} n_j u_i d\Gamma = \int_{\Gamma_g}
\begin{Bmatrix}
\delta \sigma_{11} \\ \delta \sigma_{22} \\ \delta \sigma_{33} \\ \delta \sigma_{12}
\end{Bmatrix}
\begin{bmatrix}
  \frac{2}{3} n_1 & - \frac{1}{3} n_2 \\
- \frac{1}{3} n_1 &   \frac{2}{3} n_2 \\
- \frac{1}{3} n_1 & - \frac{1}{3} n_2 \\
n_2 & n_1
\end{bmatrix}
\begin{Bmatrix}
u_1 \\ u_2
\end{Bmatrix}
d\Gamma
$$
