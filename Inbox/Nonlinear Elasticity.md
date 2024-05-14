---
icon: OcInfinity16
---

#Elasticity

![[Principal invariants of a second-order tensor]]
# Kinematics
There are three typical kinematic descriptions used for finite element analysis of nonlinear problem: (1) Total Lagrangian (TL), (2) Updated Lagrangian (UL) and (3) Co-Rotational (CR).

**Displacement**
$$
\boldsymbol x = \boldsymbol X + \boldsymbol u, \quad \boldsymbol u = \boldsymbol x - \boldsymbol X
$$

**Deformation gradient**
$$
\boldsymbol F = \frac{\partial \boldsymbol x}{\partial \boldsymbol X}, \quad
F_{iI} = \frac{\partial x_i}{\partial X_I}
$$
the corresponding determine of deformation gradient is denoted by $J = \det \boldsymbol F$.

**Displacement gradient**
$$
\boldsymbol G = \boldsymbol F - \boldsymbol I = \frac{\partial \boldsymbol x}{\partial \boldsymbol X} - \boldsymbol I = \frac{\partial \boldsymbol u}{\partial \boldsymbol X}
$$
$$
G_{iI} = F_{iI} - \delta_{iI} = x_{i,I} - \delta_{iI} = u_{i,I}
$$

**Polar decomposition**
The body particle motion can be expressed as a pure deformation followed by a rigid rotation, or as a rigid rotation followed by a pure deformation. The deformation gradient can be written as decomposition
$$
\boldsymbol F = \boldsymbol R \boldsymbol U = \boldsymbol V \boldsymbol R
$$
in which $\boldsymbol R$ is the orthogonal rotation matrix($\boldsymbol R^{-1} = \boldsymbol R^T$, $\det(\boldsymbol R) = 1$).

**Stretch Tensors**
**Right Cauchy-Green stretch tensor**
$$
\boldsymbol C = \boldsymbol F^T \cdot \boldsymbol F, \quad C_{IJ} = F_{iI}F_{iJ}
$$
**Left Cauchy-Green stretch tensor**
$$
\boldsymbol B = \boldsymbol F \cdot \boldsymbol F^T, \quad B_{ij} = F_{iI}F_{jI}
$$

# Strain measures
In order to establish constitutive equation conveniently, we define finite strain measures. The strain must have the following attributes
1. Should be a symmetric second order tensor.
2. Must identically vanish for rigid motions.
3. Should be a continuous, unique and monotonic function of displacement gradients.
4. Should reduce to the infinitesimal strain measure if the deformations become "small".

**Right Green-Lagrange strain**
$$
\boldsymbol E = \frac{1}{2}(\boldsymbol C - \boldsymbol I)
$$
$$
E_{IJ} = \frac{1}{2}(C_{IJ}-\delta_{IJ}) = \frac{1}{2}(u_{I,J}+u_{J,I}+u_{k,I}u_{k,J})
$$

**Left Green-Lagrange strain (Eulerian strain)**
$$
\boldsymbol e = \frac{1}{2}(\boldsymbol I - \boldsymbol B^{-1}) = \frac{1}{2}(\boldsymbol I - \boldsymbol F^{-T}\boldsymbol F^{-1})
$$

# Stress measures
**Cauchy stress (True stress)**: $\boldsymbol \sigma$
**First Piola-Kirchhoff stress (PK1 stress)**
$$
\begin{gather}
\boldsymbol P = J \boldsymbol \sigma \cdot \boldsymbol F^{-T} = \boldsymbol F \cdot \boldsymbol S \\
P_{iI} = J\sigma_{ij}F_{Ij}^{-1} = F_{iJ}S_{JI}
\end{gather}
$$
$$
\begin{gather}
\boldsymbol \sigma = \frac{1}{J} \boldsymbol P \cdot \boldsymbol F^T \\
\sigma_{ij} = \frac{1}{J} P_{iI} F_{jI}
\end{gather}
$$
**Second Piola-Kirchhoff stress (PK2 stress)**
$$
\begin{gather}
\boldsymbol S = J \boldsymbol F^{-1} \boldsymbol \sigma \boldsymbol F^{-T} \\
S_{IJ} = J F_{Ii}^{-1}\sigma_{ij}F_{Jj}^{-1}
\end{gather}
$$

# Constitutive model
![[Hyperelasticity]]

# Equilibrium equations
The equilibrium equations for nonlinear elasticity is identical to that of [[Elasticity|elasticity]] as follows
$$
\left \{
\begin{array}{l}
\nabla \cdot \boldsymbol \sigma + \rho \boldsymbol b = \rho \ddot{\boldsymbol{u}} & \mathrm{in} \; \Omega \\
\boldsymbol n \cdot \boldsymbol \sigma = \boldsymbol t & \mathrm{on} \; \Gamma^t \\
\boldsymbol u = \boldsymbol g & \mathrm{on} \; \Gamma^g \\
\end{array}
\right .
$$
or be rephrased using Einstein notation as
$$
\left \{
\begin{array}{l}
\sigma_{ij,j} + \rho b_i = \rho \ddot u_i & \mathrm{in} \; \Omega \\
n_j \sigma_{ji} = t_i & \mathrm{on} \; \Gamma^t \\
u_i = g_i & \mathrm{on} \; \Gamma^g \\
\end{array}
\right .
$$
These equilibrium equations are also enable to be expressed by 1st and 2en PK stress tensors:
For 1st PK
$$
\left \{
\begin{array}{l}
P_{iI,I} + J \rho b_i = J \rho \ddot u_i & \mathrm{in} \; \Omega \\
\frac{1}{J}P_{iI}F_{jI} n_j = t_i \; \mathrm{or} \; P_{iI} N_{I} = J t_i & \mathrm{on} \; \Gamma^t \\
u_i = g_i & \mathrm{on} \; \Gamma^g \\
\end{array}
\right .
$$
For 2nd PK
$$
\left \{
\begin{array}{l}
F_{iI}S_{IJ,J} + J \rho b_i = J \rho \ddot u_i & \mathrm{in} \; \Omega \\
\frac{1}{J}F_{iI}S_{IJ}F_{jJ} n_j = t_i \; \mathrm{or} \; F_{iI} S_{IJ} N_{J} = J t_i & \mathrm{on} \; \Gamma^t \\
u_i = g_i & \mathrm{on} \; \Gamma^g \\
\end{array}
\right .
$$

# Lagrangian formulation
![[Total Lagrangian formulation]]
