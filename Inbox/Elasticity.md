---
icon: OcInfinity16
---

#Elasticity #Incompressible 
# Strong form
The strong form of elasticity problem is given by
$$
\left \{
\begin{array}{l}
\nabla \cdot \boldsymbol{\sigma} + \boldsymbol{b} = \mathbf{0} & \text{in} \; \Omega \\
\boldsymbol{\sigma} \cdot \boldsymbol{n} = \boldsymbol{t} & \text{on} \; \Gamma_{t} \\
\boldsymbol{u} = \boldsymbol{g} & \text{on} \; \Gamma_{g}
\end{array} \right .
$$
or with a indices form
$$
\left \{
\begin{array}{l}
\sigma_{ij,j} + b_{i} = 0 & \text{in} \; \Omega \\
\sigma_{ij} n_{j} = t_{i} & \text{on} \; \Gamma_{t} \\
u_{i} = g_{i} & \text{on} \; \Gamma_{g}
\end{array} \right .
$$
where $\boldsymbol b$ is the prescribed body force, $\Gamma_t$ and $\Gamma_g$ are the natural boundary and essential boundary, and $\boldsymbol t$, $\boldsymbol g$ are the corresponding prescribed variables(traction and displacement) respectively. For a linear isotropic material, the stress $\boldsymbol \sigma$ can be expressed by material coefficients and strain $\boldsymbol \varepsilon$ as

$$
\boldsymbol{\sigma} = \boldsymbol{C} : \boldsymbol{\varepsilon}, \quad \sigma_{ij} = C_{ijkl} \varepsilon_{kl}
$$

^9388fd

in which $\boldsymbol C$ stands for the [fourth-order elasticity tensor](https://en.wikipedia.org/wiki/Hooke%27s_law#Linear_elasticity_theory_for_continuous_media) and its components has the following form

$$
C_{ijkl} = \lambda \delta_{ij}\delta_{kl} + \mu (\delta_{ik}\delta_{jl} + \delta_{il}\delta_{jk})
$$

^b89fd8

and $\lambda$ and $\mu$ are Lamé coefficients, they can be expressed by Young's modulus $E$ and Poisson's ratio $\nu$ as

$$
\lambda = \frac{E\nu}{(1+\nu)(1-2\nu)}, \quad \mu = \frac{E}{2(1+\nu)}
$$

and the strain has a linear relationship with displacement under infinitesimal deformation assumption

$$
\boldsymbol{\varepsilon} = \frac{1}{2}(\nabla \cdot \boldsymbol{u} + \boldsymbol{u} \cdot \nabla), \quad
\varepsilon_{ij} = \frac{1}{2}(u_{i,j} + u_{j,i})
$$

^605c91

# Galerkin formulation
The **Galerkin weak form** of elasticity strong form can be derived from *weighted residual method* or *minimum total potential energy principle* as
$$
\int_{\Omega} \delta \boldsymbol \varepsilon : \boldsymbol \sigma d\Omega = \int_{\Gamma_t} \delta \boldsymbol u \cdot \boldsymbol t d\Gamma + \int_\Omega \delta \boldsymbol u \cdot \boldsymbol b d\Omega
$$
In numerical formulation, the whole domain is discretized by a set of control nodes $\{\boldsymbol x_I\}_{I=1}^{n_p}$, where $n_p$ is the total number of nodes. The displacement can be approximate by
$$
\boldsymbol{u}^{h} = \sum_{I=1}^{n_{p}} N_{I} \boldsymbol{d}_{I}
$$
where $N_I$ is the shape function at node $\boldsymbol x_I$ and $\boldsymbol d_I$ is the corresponding nodal coefficient. Using [Voigt notation](https://en.wikipedia.org/wiki/Voigt_notation), the strain tensor can be expressed as the vector form
$$
\boldsymbol \varepsilon =
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ \varepsilon_{33} \\ 2\varepsilon_{12} \\ 2\varepsilon_{13} \\ 2\varepsilon_{23}
\end{Bmatrix} =
\begin{Bmatrix}
u_{1,1} \\ u_{2,2} \\ u_{3,3} \\ u_{1,2} + u_{2,1} \\ u_{3,1} + u_{1,3} \\ u_{2,3} + u_{3,2}
\end{Bmatrix} = \sum_{I=1}^{n_{p}}
\underbrace{
\begin{bmatrix}
N_{I,1} & 0 & 0 \\ 0 & N_{I,2} & 0 \\ 0 & 0 & N_{I,3} \\
N_{I,2} & N_{I,1} & 0 \\ N_{I,3} & 0 & N_{I,1} \\ 0 & N_{I,3} & N_{I,2} 
\end{bmatrix}}_{\boldsymbol B_I}
\begin{Bmatrix}
d_{1I} \\ d_{2I} \\ d_{3I}
\end{Bmatrix} = \sum_{I=1}^{n_p} \boldsymbol B_I \boldsymbol d_I
$$
meanwhile, the stress is also represented by strain vector in accordance with constitutive relationship  
$$
\boldsymbol \sigma =
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12} \\ \sigma_{13} \\ \sigma_{23}
\end{Bmatrix} = \underbrace{
\frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu &   \nu &   \nu & 0 & 0 & 0 \\
  \nu & 1-\nu &   \nu & 0 & 0 & 0 \\
  \nu &   \nu & 1-\nu & 0 & 0 & 0 \\
    0 &     0 &     0 & \frac{(1-2\nu)}{2} & 0 & 0 \\
    0 &     0 &     0 & 0 & \frac{(1-2\nu)}{2} & 0 \\
    0 &     0 &     0 & 0 & 0 & \frac{(1-2\nu)}{2}
\end{bmatrix}}_{\boldsymbol D}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ \varepsilon_{33} \\ 2\varepsilon_{12} \\ 2\varepsilon_{13} \\ 2\varepsilon_{23}
\end{Bmatrix}
$$

^6a77ed

$$
\boldsymbol \sigma = \boldsymbol D \boldsymbol \varepsilon = \sum_{I=1}^{n_p} \boldsymbol D \boldsymbol B_I \boldsymbol d_I
$$
Consequently, the discrete governing equations can be established as
$$
\boldsymbol K \boldsymbol d = \boldsymbol f
$$
where $\boldsymbol K$ is the stiffness matrix, $\boldsymbol f$ is the force vector, and their components has the following forms
$$
\begin{align}
\boldsymbol K_{IJ} &= \int_\Omega \boldsymbol B_I^T \boldsymbol D \boldsymbol B_J d\Omega \\
\boldsymbol f_I &= \int_{\Gamma_t} N_I \boldsymbol t d\Gamma + \int_\Omega N_I \boldsymbol b d\Omega
\end{align}
$$
# Plane strain and plane stress
In 2D case, the constitutive relation will be reduced based on **plane strain assumption** or **plane stress assumption**. In **plane strain**, all of the strain tensor components related with z-axis are vanished, i.e. $\varepsilon_{3i}=0$, then the non-zero stress can also be reduced as
$$
\boldsymbol \sigma =
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{12}
\end{Bmatrix} = 
\underbrace{
\frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu &   \nu & 0 \\
  \nu & 1-\nu & 0 \\
    0 &     0 & \frac{1-2\nu}{2} \\
\end{bmatrix}}_{\boldsymbol D}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix} = \boldsymbol D \boldsymbol \varepsilon
$$
and
$$
\sigma_{33} = \frac{E\nu}{(1+\nu)(1-2\nu)}(\varepsilon_{11}+\varepsilon_{22})
$$
It is noted that the stress vector $\boldsymbol \sigma$ excludes $\sigma_{33}$ since $\varepsilon_{33}=0$ and then $\sigma_{33}$ cannot contribute to potential energy in Galerkin weak form.
The strain tensor in 2D is also reduced as the following form
$$
\boldsymbol \varepsilon =
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix} = \sum_{I=1}^{n_p}
\underbrace{
\begin{bmatrix}
N_{I,1} & 0 \\ 0 & N_{I,2} \\ N_{I,2} & N_{I,1}
\end{bmatrix}}_{\boldsymbol B}
\begin{Bmatrix}
d_{1I} \\ d_{2I}
\end{Bmatrix} = \sum_{I=1}^{n_p}
\boldsymbol B_I \boldsymbol d_I
$$

^a2b267

The **plane stress** can be regarded as a counterpart of the plane strain since all of the stress tensor components related to z-axis direction are assumed to be zeros, i.e. $\sigma_{3i}=0$. Therefore the [[Elasticity#^6a77ed|constitutive equation]] can be rewritten as
$$
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ 0 \\ \sigma_{12} \\ 0 \\ 0
\end{Bmatrix} =
\frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu &   \nu & \nu & 0 & 0 & 0 \\
  \nu & 1-\nu & \nu & 0 & 0 & 0 \\
  \nu & \nu & 1-\nu & 0 & 0 & 0 \\
    0 &     0 &   0 & \frac{1-2\nu}{2} & 0 & 0 \\
    0 &     0 &   0 & 0 & \frac{1-2\nu}{2} & 0 \\
    0 &     0 &   0 & 0 & 0 & \frac{1-2\nu}{2} \\
\end{bmatrix}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ \varepsilon_{33} \\ \varepsilon_{12} \\ \varepsilon_{13} \\ \varepsilon_{23}
\end{Bmatrix}
$$
Finally, the stress vector for plane stress can be represented by $\varepsilon_{11},\varepsilon_{22},\varepsilon_{12}$ through solving above constitutive equation, yields
$$
\boldsymbol \sigma =
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{12}
\end{Bmatrix} = 
\underbrace{
\frac{E}{1-\nu^2}
\begin{bmatrix}
  1 & \nu & 0 \\
\nu &   1 & 0 \\
    0 &     0 & \frac{1-\nu}{2} \\
\end{bmatrix}}_{\boldsymbol D}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix} = \boldsymbol D \boldsymbol \varepsilon
$$

^91dd38

It can be easily found that
$$\varepsilon_{33}=-\frac{\nu}{1-\nu}(\varepsilon_{11}+\varepsilon_{22}) \ne 0$$
however the strain vector $\boldsymbol \varepsilon$ does not include it since $\varepsilon_{33}$ cannot contribute to potential energy, which is similar with $\sigma_{33}$ in plane strain case. Moreover, the approximant of $\boldsymbol \varepsilon$ is identical with [[Elasticity#^a2b267|plane strain one]].
# Spectral decomposition of elasticity
![[Spectral decomposition of elasticity]]
# Benchmark examples

## Cantilever beam problem (plane stress)
![[Cantilever Beam]]
## Hollow cylinder under  inner and outer pressures
![[Hollow cylinder under  inner and outer pressures]]

## Manufactorized solution for hollow cylinder problem
![[Manufactorized solution for hollow cylinder problem]]
## Plate with a hole
![[Plate with a hole]]
