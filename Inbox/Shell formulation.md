---
icon: OcInfinity16
---

#Elasticity/Shell/Thin-shell #Math/Tensor/Curvilinear 
# Kinematics on surface
Suppose that a specific point at shell can be expressed by material coordinates $\boldsymbol{X}$ or spatial coordinates $\boldsymbol{x}$ as follows
$$
\boldsymbol{X}(\xi^1,\xi^2,\xi^3) = \boldsymbol R (\xi^1,\xi^2) +
\xi^3 \boldsymbol A_3(\xi^1,\xi^2)
$$
$$
\boldsymbol{x}(\xi^1,\xi^2,\xi^3) = \boldsymbol r(\xi^1,\xi^2) +
\xi^3 \boldsymbol a_3(\xi^1,\xi^2)
$$
where
$$
\boldsymbol A_\alpha = \boldsymbol R_{,\alpha},\quad \boldsymbol A_3 = \frac{1}{J_0} \boldsymbol A_{1} \times \boldsymbol A_{2},\quad
J_0 = \Vert \boldsymbol A_{1} \times \boldsymbol A_{2} \Vert, \quad \alpha = 1,2
$$
$$
\boldsymbol a_\alpha = \boldsymbol r_{,\alpha},\quad \boldsymbol a_3 = \frac{1}{J} \boldsymbol a_{1} \times \boldsymbol a_{2},\quad
J = \Vert \boldsymbol a_{1} \times \boldsymbol a_{2} \Vert, \quad \alpha = 1,2
$$
$\boldsymbol A_3$ and $\boldsymbol a_3$ are the outward unite normal of the surface, and have the following properties
$$
\begin{gather}
\boldsymbol a_3 \cdot \boldsymbol a_3 = 1, \quad
\boldsymbol A_3 \cdot \boldsymbol A_3 = 1 \\
\boldsymbol a_{3,\alpha} \cdot \boldsymbol a_3 = 0, \quad
\boldsymbol A_{3,\alpha} \cdot \boldsymbol A_3 = 0
\end{gather}
$$
the relation between $\boldsymbol r$ and $\boldsymbol R$ can be depicted by mid-plane displacement $\boldsymbol v$ and rotation $\boldsymbol \vartheta$
**Displacement**
$$
\begin{split}
\boldsymbol{x} &= \boldsymbol{u} + \boldsymbol{X} \\
\boldsymbol r + \xi^3 \boldsymbol a_3 &= \boldsymbol v + \xi^3 \boldsymbol \vartheta + \boldsymbol R + \xi^3 \boldsymbol A_3 \\
\boldsymbol r + \xi^3 \boldsymbol a_3 &= \boldsymbol R + \boldsymbol v + \xi^3 (\boldsymbol A_3 + \boldsymbol \vartheta)
\end{split}
$$
or
$$
\boldsymbol r = \boldsymbol R + \boldsymbol{v}, \quad
\boldsymbol a_3 = \boldsymbol A_3 + \boldsymbol{\vartheta}
$$
$$
\boldsymbol{u} = \boldsymbol{v} + \xi^3 \boldsymbol{\vartheta}
$$
**Strain Measure**
$$
\begin{split}
ds^2 - dS^2 &= d\boldsymbol{x} \cdot d\boldsymbol{x} - d\boldsymbol{X} \cdot d\boldsymbol{X} \\ &=
\boldsymbol{g}_i \cdot \boldsymbol{g}_j d\xi^i d\xi^j -
\boldsymbol{G}_i \cdot \boldsymbol{G}_j d\xi^i d\xi^j \\ &=
(g_{ij} - G_{ij}) d\xi^i d\xi^j \\ &=
d\boldsymbol{\xi} \cdot 2 \boldsymbol{E} \cdot d\boldsymbol{\xi}
\end{split}
$$
where, according to [[Curvilinear Coordinates]], the covariant basis vectors and metric coefficient are defined by:
$$
d\boldsymbol{x} = \boldsymbol{g}_i d\xi^i, \quad
d\boldsymbol{X} = \boldsymbol{G}_i d\xi^i
$$
$$
g_{ij} = \boldsymbol{g}_i \cdot \boldsymbol{g}_j, \quad
G_{ij} = \boldsymbol{G}_i \cdot \boldsymbol{G}_j
$$
and $\boldsymbol{E}$ is the strain tensor, and its components are given by:
$$
E_{ij} = \frac{1}{2}(g_{ij} - G_{ij})
$$
with
$$
\boldsymbol{g}_\alpha = \boldsymbol a_{\alpha} + \xi^3 \boldsymbol a_{3,\alpha}, \quad
\boldsymbol{g}_3 = \boldsymbol a_3
$$
$$
\boldsymbol{G}_\alpha = \boldsymbol A_{\alpha} +
\xi^3 \boldsymbol{A}_{3,\alpha}, \quad
\boldsymbol G_3 = \boldsymbol A_3
$$
$$
\begin{split}
\boldsymbol{g}_\alpha &= \boldsymbol A_{\alpha} + \boldsymbol{v}_{,\alpha} +
\xi^3 (\boldsymbol A_{3,\alpha} + \boldsymbol{\vartheta}_{,\alpha}) \\ &=
\boldsymbol A_{\alpha} + \xi^3 \boldsymbol A_{3,\alpha} + \boldsymbol{v}_{,\alpha} + \xi^3 \boldsymbol{\vartheta}_{,\alpha} \\ &=
\boldsymbol{G}_{\alpha} + \boldsymbol{u}_{,\alpha}
\end{split}
$$
$$
\begin{split}
g_{\alpha \beta} &= \boldsymbol{g}_{\alpha} \cdot \boldsymbol{g}_{\beta} \\
&= (\boldsymbol a_{\alpha} + \xi^3 \boldsymbol a_{3,\alpha}) \cdot
(\boldsymbol a_{\beta} + \xi^3 \boldsymbol a_{3,\beta}) \\
&= \boldsymbol a_{\alpha} \cdot \boldsymbol a_{\beta} +
(\boldsymbol a_{\alpha} \cdot \boldsymbol a_{3,\beta} +
\boldsymbol a_{3,\alpha} \cdot \boldsymbol a_{\beta}) \xi^3 +
\boldsymbol a_{3,\alpha} \cdot \boldsymbol a_{3,\beta} (\xi^3)^2 \\
\end{split}
$$
$$
\begin{split}
g_{\alpha 3} &= \boldsymbol{g}_{\alpha} \cdot \boldsymbol{g}_3 \\
&= (\boldsymbol a_{\alpha} + \xi^3 \boldsymbol a_{3,\alpha}) \cdot
\boldsymbol a_3 \\
&= \boldsymbol a_{3,\alpha} \cdot \boldsymbol a_3 \xi^3 \\
\end{split}
$$
$$
g_{33} = \boldsymbol{g}_3 \cdot \boldsymbol{g}_3
= \boldsymbol a_3 \cdot \boldsymbol a_3 = 1
$$
$$
\begin{split}
G_{\alpha \beta} &= \boldsymbol{G}_{\alpha} \cdot \boldsymbol{G}_{\beta} \\
&= \boldsymbol A_{\alpha} \cdot \boldsymbol A_{\beta} +
(\boldsymbol A_{\alpha} \cdot \boldsymbol A_{3,\beta} +
\boldsymbol A_{3,\alpha} \cdot \boldsymbol A_{,\beta}) \xi^3 +
\boldsymbol A_{3,\alpha} \cdot \boldsymbol A_{3,\beta} (\xi^3)^2
\end{split}
$$
$$
G_{\alpha 3} = \boldsymbol{G}_{\alpha} \cdot \boldsymbol{G}_3 = \boldsymbol A_{3,\alpha} \cdot \boldsymbol A_3 \xi^3
$$
$$
G_{33} = \boldsymbol{G}_3 \cdot \boldsymbol{G}_3
= \boldsymbol A_3 \cdot \boldsymbol A_3 = 1
$$
subsequently, the [[Nonlinear Elasticity#Strain measures|right Green-Lagrangian strain]] can be written as
$$
\begin{split}
E_{\alpha \beta}
&= \frac{1}{2}
(\boldsymbol a_{\alpha} \cdot \boldsymbol a_{\beta} -
\boldsymbol A_{\alpha} \cdot \boldsymbol A_{\beta})\\
&+ \frac{1}{2}
(\boldsymbol a_{\alpha} \cdot \boldsymbol a_{3,\beta} +
\boldsymbol a_{3,\alpha} \cdot \boldsymbol a_{\beta} -
\boldsymbol A_{\alpha} \cdot \boldsymbol A_{3,\beta} -
\boldsymbol A_{3,\alpha} \cdot \boldsymbol A_{\beta}) \xi^3 \\
&+ \frac{1}{2}
(\boldsymbol a_{3,\alpha} \cdot \boldsymbol a_{3,\beta} -
\boldsymbol A_{3,\alpha} \cdot \boldsymbol A_{3,\beta})(\xi^3)^2 \\
&= \frac{1}{2}
(\boldsymbol A_{\alpha} \cdot \boldsymbol{v}_{,\beta} +
\boldsymbol{v}_{,\alpha} \cdot \boldsymbol A_{\beta} +
\boldsymbol{v}_{,\alpha} \cdot \boldsymbol{v}_{,\beta}) \\
&+ \frac{1}{2}
(\boldsymbol A_{3,\alpha} \cdot \boldsymbol{v}_{,\beta} +
\boldsymbol{v}_{,\alpha} \cdot \boldsymbol A_{3,\beta} +
\boldsymbol A_{\alpha} \cdot \boldsymbol{\vartheta}_{,\beta} +
\boldsymbol{\vartheta}_{,\alpha} \cdot \boldsymbol A_{\beta} +
\boldsymbol{v}_{,\alpha} \cdot \boldsymbol{\vartheta}_{,\beta} +
\boldsymbol{\vartheta}_{,\alpha} \cdot \boldsymbol{v}_{,\beta}) \xi^3 \\
&+ \frac{1}{2}
(\boldsymbol A_{3,\alpha} \cdot \boldsymbol{\vartheta}_{,\beta} +
\boldsymbol{\vartheta}_{,\alpha} \cdot \boldsymbol A_{3,\beta} +
\boldsymbol{\vartheta}_{,\alpha} \cdot \boldsymbol{\vartheta}_{,\beta})
(\xi^3)^2 \\
\end{split}
$$
$$
\begin{split}
E_{3\alpha} &= \frac{1}{2}(g_{\alpha3}-G_{\alpha3}) \\
&= \frac{1}{2}(\boldsymbol a_{3,\alpha} \cdot \boldsymbol a_3-\boldsymbol A_{3,\alpha} \cdot \boldsymbol A_3)\xi^3 \\
&= \frac{1}{2}(\boldsymbol A_{3,\alpha} \cdot \boldsymbol \vartheta + \boldsymbol \vartheta_{,\alpha} \cdot \boldsymbol A_3 + \boldsymbol \vartheta_{,\alpha} \cdot \boldsymbol \vartheta)\xi^3 \\
\end{split}
$$
$$
E_{33} = 0
$$

# Linear shell
For infinitesimal deformation, the strain has the form that
$$
\boldsymbol A \approx \boldsymbol a
$$
$$
\epsilon_{\alpha \beta}
= \frac{1}{2}(\boldsymbol g_\alpha \cdot \boldsymbol u_{,\beta} + \boldsymbol u_{,\alpha} \cdot \boldsymbol g_\beta)
= \varepsilon_{\alpha \beta} + \kappa_{\alpha \beta} \xi^3
$$
$$
\epsilon_{\alpha3} = \frac{1}{2}(\boldsymbol g_\alpha \cdot \boldsymbol u_{,3} + \boldsymbol u_{,\alpha}\cdot \boldsymbol g_3) = \frac{1}{2}(\boldsymbol a_\alpha \cdot \boldsymbol \vartheta + \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3) + \frac{1}{2} (\boldsymbol a_3 \cdot \boldsymbol \vartheta)_{,\alpha} \xi^3
$$
$$
\epsilon_{33} = \boldsymbol g_3 \cdot \boldsymbol u_{,3} = \boldsymbol a_3 \cdot \boldsymbol \vartheta
$$
where
$$
\varepsilon_{\alpha \beta} = \frac{1}{2}
(\boldsymbol a_{\alpha} \cdot \boldsymbol{v}_{,\beta} +
\boldsymbol{v}_{,\alpha} \cdot \boldsymbol a_{\beta})
$$
$$
\boldsymbol \varepsilon = \boldsymbol a^\gamma \boldsymbol v_{,\gamma}, \quad \varepsilon_{\alpha \beta} = \boldsymbol a_\alpha \cdot \boldsymbol \varepsilon \cdot \boldsymbol a_\beta
$$
$$
\begin{split}
\kappa_{\alpha \beta} &= \frac{1}{2}
(\boldsymbol a_{3,\alpha} \cdot \boldsymbol{v}_{,\beta} +
\boldsymbol{v}_{,\alpha} \cdot \boldsymbol a_{3,\beta} +
\boldsymbol a_{\alpha} \cdot \boldsymbol{\vartheta}_{,\beta} +
\boldsymbol{\vartheta}_{,\alpha} \cdot \boldsymbol a_{\beta}) \\
&= \frac{1}{2} \left (
\begin{split}
&(\boldsymbol a_3 \cdot \boldsymbol v_{,\beta})_{,\alpha} - \boldsymbol a_3 \cdot \boldsymbol v_{,\alpha \beta} \\
+ &(\boldsymbol v_{,\alpha} \cdot \boldsymbol a_{3})_{,\beta} - \boldsymbol a_3 \cdot \boldsymbol v_{,\alpha \beta} \\
+ &(\boldsymbol a_\alpha \cdot \boldsymbol \vartheta)_{,\beta} - \boldsymbol \vartheta \cdot \boldsymbol a_{\alpha, \beta} \\ 
+ &(\boldsymbol \vartheta \cdot \boldsymbol a_\beta)_{,\alpha} - \boldsymbol \vartheta \cdot \boldsymbol a_{\alpha, \beta} \\ 
\end{split}
\right )
\end{split}
$$
$$
\boldsymbol \kappa = \boldsymbol \vartheta_{,\gamma} \boldsymbol a^\gamma + \boldsymbol a^\gamma \otimes \boldsymbol a_{3,\gamma} \cdot \boldsymbol v_{,\eta} \otimes \boldsymbol a^\eta = \boldsymbol \vartheta_{,\gamma} \boldsymbol a^\gamma - \boldsymbol b \cdot \boldsymbol v_{,\eta} \boldsymbol a^\eta = \nabla \boldsymbol \vartheta - \boldsymbol b \cdot \nabla \boldsymbol v
$$
where
$$
\boldsymbol b = \boldsymbol a^\gamma_{,\gamma} \otimes \boldsymbol a_3 = - \boldsymbol a^\gamma \otimes \boldsymbol a_{3,\gamma}, \quad
b_{\alpha\beta} = \boldsymbol a_\alpha \cdot \boldsymbol b \cdot \boldsymbol a_\beta = - \boldsymbol a_{3,\alpha} \cdot \boldsymbol a_\beta = \boldsymbol a_3 \cdot \boldsymbol a_{\alpha, \beta}
$$
$$
b_{\alpha \beta} = b_{\beta \alpha}, \quad \boldsymbol b = \boldsymbol b^T
$$
assuming that
$$
\epsilon_{3i} = 0 \rightarrow \boldsymbol \vartheta = - \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 \boldsymbol a^\alpha
$$
where $\boldsymbol a^\alpha$'s are the in-plane contravariant base vectors. Substituting it into $\kappa_{\alpha \beta}$ yields
$$
\begin{split}
\kappa_{\alpha \beta} &= (\Gamma_{\alpha \beta}^{\gamma}\boldsymbol v_{,\gamma}-\boldsymbol v_{,\alpha \beta}) \cdot \boldsymbol a_3 \\ 
&= - (\boldsymbol v_{,\alpha})\vert_\beta \cdot \boldsymbol a_3 \\ 
&= - \boldsymbol a_\alpha \cdot (\boldsymbol a^\gamma \boldsymbol v_{,\gamma})_{,\beta} \cdot \boldsymbol a_3 \\ 
&= - \boldsymbol a_\alpha \cdot (\boldsymbol a^\gamma \boldsymbol v_{,\gamma})_{,\eta}\cdot \boldsymbol a_3 \boldsymbol a^\eta \cdot \boldsymbol a_\beta \\
&= - \boldsymbol a_\alpha \cdot \boldsymbol a_3 \cdot \nabla^S(\nabla^S \boldsymbol v) \cdot \boldsymbol a_\beta \\
&= \boldsymbol a_\alpha \cdot \boldsymbol \kappa \cdot \boldsymbol a_\beta
\end{split}
$$

# Forth order elasticity tensor
$$
\begin{split}
\boldsymbol C &= \bar C^{ijkl} \boldsymbol e_i \otimes \boldsymbol e_j \otimes \boldsymbol e_k \otimes \boldsymbol e_l \\
&= \bar C^{ijkl} \frac{\partial \boldsymbol x}{\partial x_i} \otimes \frac{\partial \boldsymbol x}{\partial x_j} \otimes \frac{\partial \boldsymbol x}{\partial x_k} \otimes \frac{\partial \boldsymbol x}{\partial x_l} \\
&= \bar C^{ijkl} 
\frac{\partial \boldsymbol x}{\partial \xi^a} \frac{\partial \xi^a}{\partial x_i} \otimes 
\frac{\partial \boldsymbol x}{\partial \xi^b} \frac{\partial \xi^b}{\partial x_j} \otimes 
\frac{\partial \boldsymbol x}{\partial \xi^c} \frac{\partial \xi^c}{\partial x_k} \otimes 
\frac{\partial \boldsymbol x}{\partial \xi^d} \frac{\partial \xi^d}{\partial x_l} \\
&= \bar C^{ijkl} \frac{\partial \xi^a}{\partial x_i} \frac{\partial \xi^b}{\partial x_j} \frac{\partial \xi^c}{\partial x_k} \frac{\partial \xi^d}{\partial x_l}
\boldsymbol g_a \otimes \boldsymbol g_b \otimes \boldsymbol g_c \otimes \boldsymbol g_d \\
&= C^{ijkl} \boldsymbol g_i \otimes \boldsymbol g_j \otimes \boldsymbol g_k \otimes \boldsymbol g_l \\
\end{split}
$$
where
$$
\bar C^{ijkl} = \lambda \delta^{ij} \delta^{kl} + \mu (\delta^{ik}\delta^{jl} + \delta^{il}\delta^{jk})
$$
$$
C^{ijkl} = \lambda g^{ij} g^{kl} + \mu (g^{ik}g^{jl} + g^{il}g^{jk})
$$
where $\lambda$ and $\mu$ are [[Linear Elasticity|Lamé coefficient]].

# Stress measure
$$
\begin{split}
\sigma^{ij} &= C^{ijkl} \epsilon_{kl} \\
\end{split}
$$
$$
\begin{Bmatrix}
    \sigma^{11} \\ \sigma^{22} \\ \sigma^{33} \\ \sigma^{12} \\ \sigma^{13} \\ \sigma^{23}
\end{Bmatrix} = 
\begin{bmatrix}
    (\lambda+2\mu)g^{11}g^{11} & \lambda g^{11}g^{22}+2\mu g^{12}g^{12} & \lambda g^{11}g^{33}+2\mu g^{13}g^{13} & \lambda g^{11}g^{12}+2\mu g^{11}g^{12} & \lambda g^{11}g^{13}+2\mu g^{11}g^{13} & \lambda g^{11}g^{23}+2\mu g^{12}g^{13} \\
     & (\lambda+2\mu)g^{22}g^{22} & \lambda g^{22}g^{33}+2\mu g^{23}g_{23} & \lambda g^{22}g^{12}+2\mu g^{12}g^{22} & \lambda g^{22}g^{13}+2\mu g^{12}g^{23} & \lambda g^{22}g^{23}+2\mu g^{22}g^{23} \\
     &  & (\lambda+2\mu)g^{33}g^{33} & \lambda g^{33}g^{12}+2\mu g^{13}g^{23} & \lambda g^{33}g^{13}+2\mu g^{13}g^{33} & \lambda g^{33}g^{23}+2\mu g^{23}g^{33} \\
     &  &  & \lambda g^{12}g^{12}+\mu (g^{11}g^{22}+g^{12}g^{12}) & \lambda g^{12}g^{13}+\mu (g^{11}g^{23}+g^{13}g^{23}) & \lambda g^{12}g^{23}+\mu (g^{12}g^{23}+g^{13}g^{22}) \\
     &  &  &  & \lambda g^{13}g_{13}+\mu (g^{11}g^{33}+g^{13}g^{13}) & \lambda g^{13}g^{23}+\mu (g^{12}g^{33}+g^{13}g^{23}) \\
     &  &  &  &  & \lambda g^{23}g^{23}+\mu (g^{22}g^{33}+g^{23}g^{23})
\end{bmatrix}
\begin{Bmatrix}
    \epsilon_{11} \\\epsilon_{22} \\ 0 \\ \epsilon_{12} \\ 0 \\ 0
\end{Bmatrix}
$$
**Internal force**
$$
\begin{split}
\int_{\bar \Omega} \delta \epsilon_{ij} \sigma^{ij} d\Omega &= \int_{\bar \Omega} \delta \epsilon_{\alpha \beta} \sigma_{\alpha \beta} d\Omega \\
&= \int_{\bar \Omega} \delta \epsilon_{\alpha \beta} C^{\alpha \beta \gamma \eta} \epsilon_{\gamma \eta} d\Omega \\
&= \int_{\Omega}\int_{-\frac{h}{2}}^{\frac{h}{2}} (\delta \varepsilon_{\alpha \beta} + \kappa_{\alpha \beta}\xi^3) C^{\alpha \beta \gamma \eta} (\varepsilon_{\gamma \eta} + \kappa_{\gamma \eta}\xi^3) d\xi^3 d\Omega \\
&= h\int_{\Omega} \delta \varepsilon_{\alpha \beta} C^{\alpha \beta \gamma \eta} \varepsilon_{\gamma \eta} d\Omega + \frac{h^3}{12} \int_{\Omega} \delta \kappa_{\alpha \beta} C^{\alpha \beta \gamma \eta} \kappa_{\gamma \eta} d\Omega \\
&= \int_{\Omega} \delta \varepsilon_{\alpha \beta} N^{\alpha \beta} d\Omega + \int_{\Omega} \delta \kappa_{\alpha \beta} M^{\alpha \beta} d\Omega \\
\end{split}
$$
for plane stress assumption, the stress can be expressed as
$$
N^{\alpha \beta} = h C^{\alpha \beta \gamma \eta} \varepsilon_{\gamma \eta},\quad \boldsymbol N = \frac{Eh}{1-\nu^2} \boldsymbol D \boldsymbol \varepsilon
$$
$$
M^{\alpha \beta} = \frac{h^3}{12} C^{\alpha \beta \gamma \eta} \kappa_{\gamma \eta},\quad \boldsymbol M = \frac{Eh^3}{12(1-\nu^2)} \boldsymbol D \boldsymbol \kappa
$$
$$
\boldsymbol D =
\begin{bmatrix}
    a^{11}a^{11} & \nu a^{11}a^{22} + (1-\nu)a^{12}a^{12} & a^{11}a^{12} \\
     & a^{22}a^{22} & a^{22}a^{12} \\
     &  & \frac{1}{2}((1-\nu)a^{11}a^{22}+(1+\nu)a^{12}a^{12})
\end{bmatrix}
$$

# Approximation
**Membrane strain**
$$
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix} = 
\begin{Bmatrix}
\boldsymbol a_1 \cdot \boldsymbol v_{,1} \\ \boldsymbol a_2 \cdot \boldsymbol v_{,2} \\ \boldsymbol a_1 \cdot \boldsymbol v_{,2} + \boldsymbol a_2 \cdot \boldsymbol v_{,1}
\end{Bmatrix} = \sum_{I=1}^{n_p}
\begin{bmatrix}
a_{11} \Psi_{I,1} & a_{12} \Psi_{I,1} & a_{13} \Psi_{I,1} \\
a_{21} \Psi_{I,2} & a_{22} \Psi_{I,2} & a_{23} \Psi_{I,2} \\
a_{11} \Psi_{I,2} + a_{21} \Psi_{I,1} & a_{12} \Psi_{I,2} + a_{22} \Psi_{I,1} & a_{13} \Psi_{I,2} + a_{23} \Psi_{I,1} \\
\end{bmatrix}
\begin{Bmatrix}
d_{1I} \\ d_{2I} \\ d_{3I}
\end{Bmatrix}
$$
**Bending strain**
$$
\begin{Bmatrix}
\kappa_{11} \\ \kappa_{22} \\ 2\kappa_{12}
\end{Bmatrix} =
\begin{Bmatrix}
(\Gamma_{11}^\gamma \boldsymbol v_{,\gamma} - \boldsymbol v_{,11}) \cdot \boldsymbol a_3 \\
(\Gamma_{22}^\gamma \boldsymbol v_{,\gamma} - \boldsymbol v_{,22}) \cdot \boldsymbol a_3 \\
2(\Gamma_{12}^\gamma \boldsymbol v_{,\gamma} - \boldsymbol v_{,12}) \cdot \boldsymbol a_3 \\
\end{Bmatrix} = \sum_{I=1}^{n_p}
\begin{bmatrix}
(\Gamma_{11}^\gamma \Psi_{I,\gamma} - \Psi_{I,11}) a_{31} &
(\Gamma_{11}^\gamma \Psi_{I,\gamma} - \Psi_{I,11}) a_{32} &
(\Gamma_{11}^\gamma \Psi_{I,\gamma} - \Psi_{I,11}) a_{33}\\
(\Gamma_{22}^\gamma \Psi_{I,\gamma} - \Psi_{I,22}) a_{31} &
(\Gamma_{22}^\gamma \Psi_{I,\gamma} - \Psi_{I,22}) a_{32} &
(\Gamma_{22}^\gamma \Psi_{I,\gamma} - \Psi_{I,22}) a_{33}\\
2(\Gamma_{12}^\gamma \Psi_{I,\gamma} - \Psi_{I,12}) a_{31} &
2(\Gamma_{12}^\gamma \Psi_{I,\gamma} - \Psi_{I,12}) a_{32} &
2(\Gamma_{12}^\gamma \Psi_{I,\gamma} - \Psi_{I,12}) a_{33}\\
\end{bmatrix}
\begin{Bmatrix}
d_{1I} \\ d_{2I} \\ d_{3I}
\end{Bmatrix}
$$
**normal rotation**
$$
\theta = \boldsymbol v_{,\gamma} n^\gamma \cdot \boldsymbol a_3 = \sum_{I=1}^{n_p}
\begin{Bmatrix}
a_{31} n^\gamma\Psi_{I,\gamma} \\
a_{32} n^\gamma\Psi_{I,\gamma} \\
a_{33} n^\gamma\Psi_{I,\gamma}
\end{Bmatrix}^T
\begin{Bmatrix}
d_{1I} \\ d_{2I} \\ d_{3I}
\end{Bmatrix}
$$

# [[Curvilinear Coordinates|Gauss-Ostrogradsky theorem]]
$$
\begin{split}
\int_\Omega f_{,\alpha} g^\alpha d\Omega &= \int_\Omega f_{,\alpha} \delta_\beta^\alpha g^\beta d\Omega \\
&= \int_\Omega f_{,\alpha} \boldsymbol a^\alpha \cdot \boldsymbol a_\beta g^\beta d\Omega \\
&= \int_\Gamma f g^\alpha n_\alpha d\Gamma - \int_\Omega f \boldsymbol a^\alpha \cdot (\boldsymbol a_\beta g^\beta)_{,\alpha} d\Omega \\
&= \int_\Gamma f g^\alpha n_\alpha d\Gamma 
- \int_\Omega f \boldsymbol a^\alpha \cdot \boldsymbol a_\beta g^\beta_{,\alpha} d\Omega
- \int_\Omega f \boldsymbol a^\alpha \cdot \boldsymbol a_{\beta,\alpha} g^\beta d\Omega \\
&= \int_\Gamma f g^\alpha n_\alpha d\Gamma 
- \int_\Omega f g^\alpha_{,\alpha} d\Omega
- \int_\Omega f \Gamma_{\alpha\beta}^\alpha g^\beta d\Omega \\
&= \int_\Gamma f g^\alpha n_\alpha d\Gamma 
- \int_\Omega f g^\alpha\vert_{\alpha} d\Omega
\end{split}
$$
$$
\begin{split}
\boldsymbol v_{,\beta} &= (v^\alpha \boldsymbol a_\alpha)_{,\beta} = v^\alpha_{,\beta}\boldsymbol a_\alpha + v^\alpha \boldsymbol a_{\alpha,\beta} \\
&= v^\alpha_{,\beta} \boldsymbol a_\alpha + \Gamma_{\alpha\beta}^\gamma v^\alpha \boldsymbol a_\gamma + b_{\alpha \beta} v^\alpha \boldsymbol a_3 \\
&= (v^\alpha_{,\beta} + \Gamma_{\beta\gamma}^\alpha v^\gamma) \boldsymbol a_\alpha + b_{\alpha \beta} v^\alpha \boldsymbol a_3
\end{split}
$$
$$
v^\alpha\vert_\beta = v^\alpha_{,\beta} + \Gamma_{\beta \gamma}^\alpha v^\gamma
$$
$$
\begin{split}
\int_\Omega f_{,\alpha} A^{\alpha \beta} \boldsymbol a_\beta d\Omega &=
\int_\Omega f_{,\alpha} \delta_\gamma^\alpha A^{\gamma \beta} \boldsymbol a_\beta d\Omega \\
&= \int_\Omega f_{,\alpha} \boldsymbol a^\alpha \cdot \boldsymbol a_\gamma A^{\gamma \beta} \boldsymbol a_\beta d\Omega \\
&= \int_\Gamma f A^{\alpha \beta} \boldsymbol a_\beta n_\alpha d\Gamma
- \int_\Omega f \boldsymbol a^\alpha \cdot (\boldsymbol a_\gamma A^{\gamma \beta} \boldsymbol a_\beta)_{,\alpha} d\Omega \\
&= \int_\Gamma f A^{\alpha \beta} n_\alpha d\Gamma
- \int_\Omega f \boldsymbol a^\alpha \cdot \boldsymbol a_\gamma A^{\gamma \beta}_{,\alpha} \boldsymbol a_\beta d\Omega
- \int_\Omega f \boldsymbol a^\alpha \cdot \boldsymbol a_{\gamma,\alpha} A^{\gamma \beta} \boldsymbol a_\beta d\Omega
- \int_\Omega f \boldsymbol a^\alpha \cdot \boldsymbol a_\gamma A^{\gamma \beta} \boldsymbol a_{\beta,\alpha} d\Omega \\
&= \int_\Gamma f A^{\alpha \beta} \boldsymbol a_\beta n_\alpha d\Gamma
- \int_\Omega f \boldsymbol A^{\alpha \beta}_{,\alpha} \boldsymbol a_\beta d\Omega
- \int_\Omega f \Gamma_{\alpha\gamma}^\alpha A^{\gamma \beta} \boldsymbol a_\beta d\Omega
- \int_\Omega f \Gamma_{\alpha\beta}^\gamma A^{\alpha \beta} \boldsymbol a_\gamma d\Omega 
- \int_\Omega f b_{\alpha\beta} A^{\alpha \beta} \boldsymbol a_3 d\Omega \\
&= \int_\Gamma f A^{\alpha \beta}\boldsymbol a_\beta n_\alpha d\Gamma
- \int_\Omega f \boldsymbol A^{\alpha \beta}\vert{\alpha}\boldsymbol a_\beta d\Omega
- \int_\Omega f b_{\alpha \beta} \boldsymbol A^{\alpha \beta}\boldsymbol a_3 d\Omega
\end{split}
$$
$$
\begin{split}
\int_\Omega f_{,\alpha} A^{\alpha\beta} \boldsymbol a_\beta d\Omega = \int_\Gamma f A^{\alpha \beta} \boldsymbol a_\beta n_\alpha d\Gamma - \int_\Omega f (A^{\alpha\beta}\boldsymbol a_\beta)\vert_\alpha d\Omega 
\end{split}
$$
$$
(A^{\alpha\beta}\boldsymbol a_\beta)\vert_\alpha = (A^{\alpha\beta}\boldsymbol a_\beta)_{,\alpha} + \Gamma_{\alpha\gamma}^\alpha A^{\gamma\beta} \boldsymbol a_\beta = (A^{\alpha\beta}_{,\alpha} + \Gamma_{\alpha \gamma}^\alpha A^{\gamma\beta} + \Gamma_{\alpha\gamma}^\beta A^{\alpha\gamma})\boldsymbol a_\beta + b_{\alpha\beta}A^{\alpha\beta}\boldsymbol a_3 = A^{\alpha\beta}\vert_\alpha \boldsymbol a_\beta + b_{\alpha\beta}A^{\alpha\beta}\boldsymbol a_3
$$
$$
\begin{split}
(A^{\alpha\beta}\boldsymbol a_3)\vert_\beta &= (A^{\alpha\beta}\boldsymbol a_3)_{,\beta} + \Gamma_{\beta\gamma}^\beta A^{\alpha\gamma}\boldsymbol a_3 + \Gamma_{\beta\gamma}^\alpha A^{\beta\gamma} \boldsymbol a_3 \\
&= A^{\alpha\beta}\vert_\beta\boldsymbol a_3 + b_{\beta\gamma}A^{\alpha\beta}\boldsymbol a^\gamma
\end{split}
$$
$$
(f^\alpha\boldsymbol a_3)\vert_\alpha = (f^\alpha\boldsymbol a_3)_{,\alpha} + \Gamma_{\alpha\beta}^\alpha f^\beta \boldsymbol a_3 = (f^\alpha_{,\alpha} + \Gamma_{\alpha\beta}^\alpha f^\beta) \boldsymbol a_3 - f^\alpha b_{\alpha\beta} \boldsymbol a^\beta = f^\alpha \vert_\alpha \boldsymbol a_3 - f^\alpha b_{\alpha\beta} \boldsymbol a^\beta
$$
$$
(f^\alpha g)\vert_\beta = (f^\alpha g)_{,\beta} + \Gamma_{\beta\gamma}^\alpha f^\gamma g = f^\alpha_{,\beta} g + \Gamma^\alpha_{\beta\gamma} f^\gamma g + f^\alpha g_{,\beta} = f^\alpha\vert_\beta g + g_{,\beta}
$$
$$
\begin{split}
\boldsymbol A_{,\gamma} &= (A^{\alpha \beta}\boldsymbol a_\alpha \boldsymbol a_\beta)_{,\gamma}
= A^{\alpha \beta}_{,\gamma}\boldsymbol a_\alpha \boldsymbol a_\beta + A^{\alpha \beta}\boldsymbol a_{\alpha,\gamma} \boldsymbol a_\beta + A^{\alpha \beta}\boldsymbol a_\alpha \boldsymbol a_{\beta,\gamma} \\
&= A^{\alpha \beta}_{,\gamma}\boldsymbol a_\alpha \boldsymbol a_\beta + A^{\alpha \beta}\boldsymbol a_{\alpha,\gamma} \boldsymbol a_\beta + A^{\alpha \beta}\boldsymbol a_\alpha \boldsymbol a_{\beta,\gamma} \\
&= (A^{\alpha \beta}_{,\gamma} + \Gamma_{\gamma \eta}^\alpha A^{\eta \beta} + \Gamma_{\gamma \eta}^\beta A^{\alpha \eta}) \boldsymbol a_\alpha \boldsymbol a_\beta + b_{\alpha \gamma} A^{\alpha \beta} \boldsymbol a_3 \boldsymbol a_\beta+ b_{\gamma\beta} A^{\alpha \beta} \boldsymbol a_\alpha \boldsymbol a_3 \\ 
&= A^{\alpha \beta}\vert_\gamma + b_{\alpha \gamma} A^{\alpha \beta} \boldsymbol a_3 \boldsymbol a_\beta+ b_{\gamma\beta} A^{\alpha \beta} \boldsymbol a_\alpha \boldsymbol a_3 \\ 
\end{split}
$$
$$
\begin{split}
A^{\alpha\beta}\vert_{\gamma\eta} &= (A^{\alpha\beta}\vert_\gamma)\vert_{\eta} \\
&= (A^{\alpha\beta}_{,\gamma}+\Gamma_{\gamma\zeta}^\alpha A^{\zeta\beta} + \Gamma_{\gamma\zeta}^\beta A^{\alpha\zeta})\vert_\eta \\
&= A^{\alpha\beta}_{,\gamma\eta} + \Gamma_{\eta\zeta}^\alpha A^{\zeta\beta}_{,\gamma} + \Gamma_{\eta\zeta}^\beta A^{\alpha\zeta}_{,\gamma} \\
&+ \Gamma_{\gamma\zeta,\eta}^\alpha A^{\zeta\beta} + \Gamma_{\gamma\zeta}^\alpha A^{\zeta\beta}_{,\eta} + \Gamma_{\eta\varsigma}^\alpha \Gamma_{\gamma\zeta}^\varsigma A^{\zeta\beta} + \Gamma_{\eta\varsigma}^\beta \Gamma_{\gamma\zeta}^\alpha A^{\varsigma\zeta} \\
&+ \Gamma_{\gamma\zeta,\eta}^\beta A^{\alpha\zeta} + \Gamma_{\gamma\zeta}^\beta A^{\alpha\zeta}_{,\eta} + \Gamma_{\eta\varsigma}^\alpha \Gamma_{\gamma\zeta}^\beta A^{\varsigma\zeta} + \Gamma_{\eta\varsigma}^\beta \Gamma_{\gamma\zeta}^\varsigma A^{\alpha\zeta}
\end{split}
$$
$$
\begin{split}
A^{\alpha\beta}\vert_{\alpha\beta} 
&= (A^{\alpha\beta}\vert_\alpha)\vert_\beta \\
&= (A^{\alpha\beta}_{,\alpha} + \Gamma_{\alpha\gamma}^\alpha A^{\gamma\beta} + \Gamma_{\alpha\gamma}^\beta A^{\alpha\gamma})\vert_\beta \\
&= A^{\alpha\beta}_{,\alpha\beta} + \Gamma_{\beta\eta}^\beta A^{\alpha\eta}_{,\alpha} \\
&+ \Gamma^\alpha_{\alpha\gamma,\beta} A^{\gamma\beta} + \Gamma^\alpha_{\alpha\gamma}A^{\gamma\beta}_{,\beta} + \Gamma^\beta_{\beta\eta} \Gamma^\alpha_{\alpha\gamma}A^{\gamma\eta} \\
&+ \Gamma^\beta_{\alpha\gamma,\beta}A^{\alpha\gamma} + \Gamma^\beta_{\alpha\gamma}A^{\alpha\gamma}_{,\beta} + \Gamma^{\beta}_{\beta\eta}\Gamma^{\eta}_{\alpha\gamma}A^{\alpha\gamma} \\
&= A^{\alpha\beta}_{,\alpha\beta} + (2\Gamma^\eta_{\eta\alpha}\delta^{\gamma}_\beta + \Gamma^\gamma_{\alpha\beta})A^{\alpha\beta}_{,\gamma} + (\Gamma^\gamma_{\gamma\alpha,\beta} + \Gamma^\gamma_{\alpha\beta,\gamma} + \Gamma^\gamma_{\gamma\alpha} \Gamma^\eta_{\eta\beta} + \Gamma^\gamma_{\gamma\eta}\Gamma^\eta_{\alpha\beta})A^{\alpha\beta}
\end{split}
$$
$$
\begin{split}
\int_\Omega \delta \varepsilon_{\alpha \beta} N^{\alpha \beta} 
&= \int_\Omega \frac{1}{2}(\boldsymbol a_{\alpha} \cdot \delta \boldsymbol v_{,\beta} + \delta \boldsymbol v_{,\alpha} \cdot \boldsymbol a_{\beta}) N^{\alpha \beta} d\Omega \\
&= \int_\Omega \delta \boldsymbol v_{,\beta} \cdot \boldsymbol a_\alpha N^{\alpha \gamma} \boldsymbol a_\gamma \cdot \boldsymbol a^\beta d\Omega \\
&= \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_\alpha N^{\alpha \beta} n_{\beta} d\Gamma -
\int_{\Omega} \delta \boldsymbol v \cdot (\boldsymbol a_\alpha N^{\alpha \gamma} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta d\Omega \\
&= \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_\alpha N^{\alpha \beta} n_{\beta} d\Gamma
- \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_\alpha N^{\alpha \beta}\vert_\beta d\Omega
- \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_3 b_{\alpha \beta} N^{\alpha \beta} d\Omega
\end{split}
$$
$$
\begin{split}
\int_{\Omega} \delta \kappa_{\alpha \beta} M^{\alpha \beta} &= \int_{\Omega} (\Gamma_{\alpha \beta}^\gamma \delta \boldsymbol v_{,\gamma} - \delta \boldsymbol v_{,\alpha \beta}) \cdot \boldsymbol a_{3} M^{\alpha \beta} d\Omega \\
&= \int_{\Gamma} \delta \boldsymbol v \cdot \boldsymbol a_3 \Gamma_{\alpha \beta}^{\gamma} M^{\alpha \beta} n_{\gamma} d\Gamma -
\int_{\Omega} \delta \boldsymbol v \cdot (\boldsymbol a_3 \Gamma_{\alpha \beta}^{\gamma} M^{\alpha \beta})_{,\gamma} d\Omega \\
&- \int_{\Gamma} \delta \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha \beta} n_\beta d\Gamma + \int_{\Gamma} \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta})_{,\beta} n_\alpha d\Gamma - \int_{\Omega} \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta})_{,\alpha \beta} d\Omega \\
\end{split}
$$
$$
\begin{split}
\int_\Omega \delta \boldsymbol v_{,\gamma} \cdot \boldsymbol a_3 \Gamma_{\alpha \beta}^\gamma M^{\alpha \beta} d\Omega 
&= \int_\Omega \delta \boldsymbol v_{,\gamma} \cdot \boldsymbol a_3 M^{\alpha \beta} \Gamma_{\alpha \beta}^\eta \boldsymbol a_\eta \cdot \boldsymbol a^\gamma d\Omega \\
&= \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta} \Gamma_{\alpha \beta}^\gamma n_\gamma d\Gamma 
- \int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta} \Gamma_{\alpha \beta}^\eta \boldsymbol a_\eta)_{,\gamma} \cdot \boldsymbol a^\gamma d\Omega \\
\end{split}
$$
$$
\int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta} \Gamma_{\alpha \beta}^\eta \boldsymbol a_\eta)_{,\gamma} \cdot \boldsymbol a^\gamma d\Omega = 
 \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_\eta b_\gamma^\eta M^{\alpha \beta} \Gamma_{\alpha \beta}^\gamma  d\Omega
+ \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_3 (M^{\alpha \beta} \Gamma_{\alpha \beta}^\gamma)_{,\gamma} d\Omega
+ \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta} \Gamma_{\alpha \beta}^\eta \Gamma_{\gamma\eta}^\gamma d\Omega
$$
$$
\begin{split}
\int_\Omega \delta \boldsymbol v_{,\alpha \beta} \cdot \boldsymbol a_3 M^{\alpha \beta} d\Omega
&= \int_\Omega \delta \boldsymbol v_{,\alpha \beta} \cdot \boldsymbol a_3 M^{\alpha \gamma} \boldsymbol a_\gamma \cdot \boldsymbol a^\beta d\Omega \\
&= \int_\Gamma \delta \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha \beta} n_\beta d\Omega
- \int_\Omega \delta \boldsymbol v_{,\alpha} \cdot (\boldsymbol a_3 M^{\alpha \gamma} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta d\Omega \\
&= \int_\Gamma \delta \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha \beta} n_\beta d\Omega
- \int_\Omega \delta \boldsymbol v_{,\alpha} \cdot (\boldsymbol a_3 M^{\gamma\eta} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta \boldsymbol a_\eta \cdot \boldsymbol a^\alpha d\Omega \\
&= \int_\Gamma \delta \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha \beta} n_\beta d\Omega
- \int_\Gamma \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\gamma} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta n_\alpha d\Gamma 
+ \int_\Omega \delta \boldsymbol v \cdot ((\boldsymbol a_3 M^{\gamma\eta} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta \boldsymbol a_\eta)_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega \\
\end{split}
$$
$$
\begin{split}
\int_\Omega \delta \boldsymbol v \cdot ((\boldsymbol a_3 M^{\gamma\eta} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta \boldsymbol a_\eta)_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega &=
\int_\Omega \delta \boldsymbol v \cdot (-\boldsymbol a_\gamma b_\beta^\gamma M^{\beta \eta} \boldsymbol a_\eta + \boldsymbol a_3 M^{\beta \eta}_{,\beta} \boldsymbol a_\eta + \boldsymbol a_3 M^{\gamma \eta}\Gamma_{\gamma \beta}^\beta \boldsymbol a_\eta)_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega 
\end{split}
$$
$$
\begin{split}
\int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_\gamma b_\beta^\gamma M^{\beta\eta}\boldsymbol a_\eta)_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega &= 
\int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_\gamma (\Gamma_{\alpha\eta}^\gamma b_\beta^\eta M^{\alpha\beta}
+ (b_\beta^\gamma M^{\alpha\beta})_{,\alpha}
+ b_\beta^\gamma M^{\beta\eta}\Gamma_{\alpha\eta}^\alpha) d\Omega
+ \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_3 b_{\alpha \gamma} b_\beta^\gamma M^{\alpha\beta} d\Omega \\
&=\int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_\alpha (b_\gamma^\alpha M^{\gamma \beta})\vert_\beta d\Omega
+ \int_\Omega \delta \boldsymbol v \cdot \boldsymbol a_3 b_{\alpha\gamma}b_\beta^\gamma M^{\alpha\beta} d\Omega

\end{split}
$$
$$
\begin{split}
\int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_3 (M^{\beta \eta}_{,\beta} \boldsymbol a_\eta + M^{\gamma \eta}\Gamma_{\gamma \beta}^\beta \boldsymbol a_\eta))_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega
+ \int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta}\Gamma_{\alpha\beta}^\eta \boldsymbol a_\eta)_{,\gamma} \cdot \boldsymbol a^\gamma d\Omega &=
\int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_3 (M^{\alpha\beta}_{,\beta} + \Gamma_{\beta \gamma}^\alpha M^{\beta \gamma} + \Gamma_{\beta\gamma}^\beta M^{\alpha\gamma}) \boldsymbol a_\alpha)_{,\eta} \cdot \boldsymbol a^\eta d\Omega \\
&= \int_\Omega \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\beta}\vert_\beta \boldsymbol a_\alpha)_{,\eta} \cdot \boldsymbol a^\eta d\Omega \\
&= \int_\Omega \delta \boldsymbol v \cdot (-\boldsymbol a_\gamma b_\alpha^\gamma M^{\alpha\beta}\vert_\beta + \boldsymbol a_3 (M^{\alpha\beta}\vert_\beta \boldsymbol a_\alpha)_{,\eta} \cdot \boldsymbol a^\eta) d\Omega \\
\end{split}
$$
where
$$
\begin{split}
\int_\Gamma \delta \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha \beta} n_\beta d\Gamma &= 
\int_\Gamma \delta \boldsymbol v_{,\gamma} \cdot \boldsymbol a_3 \delta_\alpha^\gamma M^{\alpha \beta} n_\beta d\Gamma = 
\int_\Gamma \delta \boldsymbol v_{,\gamma} \cdot \boldsymbol a_3 (n_\alpha n^\gamma + s_\alpha s^\gamma) M^{\alpha \beta} n_\beta d\Gamma \\
&= \int_\Gamma \delta \boldsymbol v_{,\gamma} n^\gamma \cdot \boldsymbol a_3 M^{\alpha \beta} n_\alpha n_\beta d\Gamma
- \int_\Gamma \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta} s_\alpha n_\beta)_{,\gamma} s^\gamma d\Gamma
+ \left . \delta \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta} s_\alpha n_\beta \right \vert_{c} \\
&= \int_\Gamma \delta \boldsymbol v_{,\gamma} n^\gamma \cdot \boldsymbol a_3 M^{\alpha \beta} n_\alpha n_\beta d\Gamma 
+ \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_\eta b_\gamma^\eta M^{\alpha \beta} s_\alpha n_\beta s^\gamma d\Gamma 
- \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta}_{,\gamma} s_\alpha n_\beta s^\gamma d\Gamma 
+ \left . \delta \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta} s_\alpha n_\beta \right \vert_{c}
\end{split}
$$
$$
\int_\Gamma \delta \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \gamma} \boldsymbol a_\gamma)_{,\beta} \cdot \boldsymbol a^\beta n_\alpha d\Gamma = 
-\int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_\gamma b_\beta^\gamma M^{\alpha \beta} n_\alpha d\Gamma + \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3 M_{,\beta}^{\alpha \beta} n_\alpha d\Gamma + \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \gamma} \Gamma_{\beta \gamma}^\beta n_\alpha d\Gamma
$$
For $\delta \boldsymbol v \cdot \boldsymbol a_\alpha$ on boundary
$$
\int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_\alpha(N^{\alpha \beta}n_\beta 
- b^\alpha_\beta M^{\beta \gamma} n_\gamma - b^\alpha_\beta M_{ns} s^\beta
)d\Gamma = \int_\Gamma \delta \boldsymbol v \cdot (\boldsymbol N \cdot \boldsymbol n - \boldsymbol b \cdot (\boldsymbol M \cdot \boldsymbol n + M_{ns} \boldsymbol s) d\Gamma 
$$
For $\delta \boldsymbol v \cdot \boldsymbol a_3$ on boundary
$$
\begin{split}
\int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3((M^{\alpha \beta}_{,\beta} + \Gamma^\alpha_{\beta \gamma}M^{\beta \gamma} + \Gamma_{\beta \gamma}^\beta M^{\alpha \gamma})n_\alpha +M_{ns,\alpha} s^\alpha) d\Gamma 
&= \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3 (M^{\alpha \beta}\vert_\beta n_\alpha + M_{ns,s})d\Gamma \\
&= \int_\Gamma \delta \boldsymbol v \cdot \boldsymbol a_3 (\boldsymbol n \cdot \boldsymbol M \cdot \bar\nabla+ M_{ns,s})d\Gamma
\end{split}
$$
For $\delta \vartheta_n$
$$
\int_\Gamma \delta \boldsymbol v_{,\gamma} n^\gamma \cdot \boldsymbol a_3 M^{\alpha \beta}n_\alpha n_\beta d\Gamma = \int_\Gamma \delta \vartheta_n M_{nn} d\Gamma
$$
For $\delta \boldsymbol v$ in domain 
$$
\begin{split}
&\int_\Omega \delta \boldsymbol v \cdot (-\boldsymbol a_\alpha N^{\alpha \beta}\vert_\beta - \boldsymbol a_3 b_{\alpha \beta} N^{\alpha \beta} - \boldsymbol a_\alpha (b^\alpha_\gamma M^{\gamma\beta})\vert_\beta - \boldsymbol a_3 b_{\alpha\gamma} b_\beta^\gamma M^{\alpha\beta} + \boldsymbol a_\gamma b_\alpha^\gamma M^{\alpha\beta}\vert_\beta - \boldsymbol a_3(M^{\alpha\beta}\vert_\beta\boldsymbol a_\alpha)_{,\eta} \cdot \boldsymbol a^\eta) d\Omega \\
=& \int_\Omega \delta \boldsymbol v \cdot (-\boldsymbol N \cdot \bar \nabla - \boldsymbol a_3 \boldsymbol b : \boldsymbol  N - (\boldsymbol b \cdot \boldsymbol M) \cdot \bar \nabla - \boldsymbol a_3 (\boldsymbol b \cdot \boldsymbol b):\boldsymbol M + \boldsymbol b \cdot \boldsymbol M \cdot \bar \nabla - \boldsymbol a_3 \nabla \cdot (\boldsymbol M \cdot \bar \nabla)) d\Omega \\
=& \int_\Omega \delta \boldsymbol v \cdot (-\boldsymbol N \cdot \bar \nabla
- (\boldsymbol b \cdot \boldsymbol M) \cdot \bar \nabla
+ \boldsymbol b \cdot \boldsymbol M \cdot \bar \nabla 
+ \boldsymbol a_3 (-\boldsymbol b : \boldsymbol  N
- (\boldsymbol b \cdot \boldsymbol b):\boldsymbol M
- \nabla \cdot (\boldsymbol M \cdot \bar \nabla))) d\Omega \\
\end{split}
$$
## Ersatz forces
$$
\boldsymbol v = \bar{\boldsymbol v} + v_3 \boldsymbol a_3
$$
$$
\begin{split}
\int_\Omega \nabla \boldsymbol v : \boldsymbol A d\Omega &= \int_\Omega \frac{\partial \boldsymbol v}{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega \\
&= \int_\Omega \frac{\partial \bar{\boldsymbol v}}{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega + \int_\Omega \frac{\partial (v_3 \boldsymbol a_3) }{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega \\
&= \int_\Omega \frac{\partial \bar{\boldsymbol v}}{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega 
+ \int_\Omega \frac{\partial v_3}{\partial \xi^\alpha} \boldsymbol a_3 \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega
+ \int_\Omega v_3 \boldsymbol a_{3,\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega \\
&= \int_\Omega \frac{\partial \bar{\boldsymbol v}}{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega 
+ \int_\Omega \frac{\partial v_3}{\partial \xi^\alpha} \boldsymbol a_3 \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega
- \int_\Omega v_3 \boldsymbol b : \boldsymbol A d\Omega \\
&= \int_\Omega \frac{\partial \bar{\boldsymbol v}}{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega 
- \int_\Omega v_3 \boldsymbol b : \boldsymbol A d\Omega \\
\end{split}
$$
$$
\begin{split}
\int_\Omega \frac{\partial \bar{\boldsymbol v}}{\partial \xi^\alpha} \otimes \boldsymbol a^\alpha : \boldsymbol A d\Omega &= \int_\Omega (\bar{\boldsymbol v} \cdot \boldsymbol A)_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega - \int_\Omega \bar{\boldsymbol v} \cdot \boldsymbol A_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega \\
&=\int_\Gamma\bar{\boldsymbol v} \cdot \boldsymbol A \cdot \boldsymbol a^\alpha n_\alpha d\Gamma - \int_\Omega \bar{\boldsymbol v} \cdot \boldsymbol A \cdot \boldsymbol a^\alpha_{,\alpha} d\Omega - \int_\Omega \bar{\boldsymbol v} \cdot \boldsymbol A_{,\alpha} \cdot \boldsymbol a^\alpha d\Omega \\

\end{split}
$$
$$
\begin{split}
(\boldsymbol A \cdot \boldsymbol a^\alpha)_{,\alpha} &= \boldsymbol A_{,\alpha} \cdot \boldsymbol a^\alpha + \boldsymbol A \cdot \boldsymbol a^\alpha_{,\alpha} \\
&= \nabla \cdot \boldsymbol A + \boldsymbol A \cdot \boldsymbol b \cdot \boldsymbol a_3 \\
\end{split}
$$
$$
\begin{split}
\int_\Omega \boldsymbol \varepsilon : \boldsymbol N d\Omega
&= \int_\Omega \boldsymbol v_{,\alpha} \boldsymbol a^\alpha : \boldsymbol N d\Omega
= \int_\Omega \boldsymbol v_{,\alpha} \cdot \boldsymbol N \cdot \boldsymbol a^\alpha d\Omega \\
&= \int_\Gamma \boldsymbol v \cdot \boldsymbol N \cdot \boldsymbol n d\Gamma
- \int_\Omega \boldsymbol v \cdot \boldsymbol N \cdot \nabla d\Omega \\
\end{split}
$$
$$
\begin{split}
\int_\Omega \boldsymbol \kappa : \boldsymbol M d\Omega &= \int_\Omega (\nabla \boldsymbol \vartheta - \boldsymbol b \cdot \nabla \boldsymbol v):\boldsymbol M d\Omega \\
&= \int_\Omega \nabla \boldsymbol \vartheta:\boldsymbol M d\Omega - \int_\Omega \boldsymbol b \cdot \nabla \boldsymbol v :\boldsymbol M d\Omega \\
&= \int_\Omega \nabla \boldsymbol \vartheta:\boldsymbol M d\Omega - \int_\Omega \boldsymbol b^T \cdot \boldsymbol M : \nabla \boldsymbol v d\Omega \\
&= \int_\Omega \nabla \boldsymbol \vartheta:\boldsymbol M d\Omega - \int_\Omega \boldsymbol b \cdot \boldsymbol M : \nabla \boldsymbol v d\Omega \\
\end{split}
$$
$$
\begin{split}
\int_\Omega \boldsymbol b \cdot \boldsymbol M : \nabla \boldsymbol v d\Omega 
&= \int_\Omega \boldsymbol b \cdot \boldsymbol M :\frac{1}{2}(\boldsymbol a^\gamma \boldsymbol v_{,\gamma} + \boldsymbol v_{,\gamma} \boldsymbol a^{\gamma}) d\Omega \\
&= \int_\Omega \frac{1}{2}(\boldsymbol a^\gamma \cdot \boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol v_{,\gamma} + \boldsymbol v_{,\gamma} \cdot \boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol a^{\gamma}) d\Omega \\
&= \int_\Gamma \boldsymbol v \cdot \boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol a^\gamma n_\gamma d\Gamma
- \int_\Omega \boldsymbol v \cdot (\boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol a^\gamma)_{,\gamma} d\Omega \\
&= \int_\Gamma \boldsymbol v \cdot \boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol a^\gamma n_\gamma d\Gamma
+ \int_\Omega \boldsymbol v \cdot (\boldsymbol a_{3,\alpha} M^{\alpha \beta})_{,\beta} d\Omega \\
&= - \int_\Gamma \boldsymbol v \cdot \boldsymbol a_{3,\alpha}\boldsymbol a^\alpha \cdot \boldsymbol M \cdot \boldsymbol a^\beta n_\beta d\Gamma + \int_\Omega \boldsymbol v \cdot (\boldsymbol a_{3,\beta} M^{\alpha \beta})_{,\alpha} d\Omega
\end{split}
$$
$$
\boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol a^\beta = - \boldsymbol a_{3,\alpha}\boldsymbol a^\alpha \cdot \boldsymbol M \cdot \boldsymbol a^\beta = -\boldsymbol a_{3,\alpha} M^{\alpha \beta}
$$
$$
\begin{split}
\int_\Omega \nabla \boldsymbol \vartheta :\boldsymbol M d\Omega &= \int_\Omega \boldsymbol a^\beta \boldsymbol \vartheta_{,\beta} : \boldsymbol M d\Omega \\
&= \int_{\Gamma} \boldsymbol \vartheta \boldsymbol a^\beta : \boldsymbol M n_\beta d\Gamma - \int_\Omega \boldsymbol \vartheta \cdot (\boldsymbol M \cdot \boldsymbol a^\beta)_{,\beta} d\Omega \\
&= - \int_{\Gamma} \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 \boldsymbol a^\alpha \cdot \boldsymbol M \cdot \boldsymbol a^\beta n_\beta d\Gamma 
+ \int_\Omega \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 \boldsymbol a^\alpha \cdot (\boldsymbol M \cdot \boldsymbol a^\beta)_{,\beta} d\Omega \\
&= - \int_{\Gamma} \boldsymbol v_{,\gamma}n^\gamma \cdot \boldsymbol a_3 M^{\alpha \beta} n_\alpha n_\beta d\Gamma 
- \int_{\Gamma} \boldsymbol v_{,\gamma}s^\gamma \cdot \boldsymbol a_3 M^{\alpha \beta} s_\alpha n_\beta d\Gamma \\
&+ \int_\Gamma \boldsymbol v \cdot \boldsymbol a_3 (M^{\alpha \beta}_{,\beta} + \Gamma_{\gamma\beta}^{\alpha} M^{\gamma \beta}) n_\alpha d\Gamma
- \int_\Omega \boldsymbol v \cdot (\boldsymbol a_3 (M^{\alpha \beta}_{,\beta} + \Gamma_{\gamma\beta}^{\alpha} M^{\gamma \beta}))_{,\alpha} d\Omega \\
&= - \int_{\Gamma} \vartheta_n M_{nn} d\Gamma + \int_\Gamma \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha \beta} s_\alpha n_\beta)_{,\gamma} s^\gamma d\Gamma - \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta} s_\alpha n_\beta \vert_c \\
&+ \int_\Gamma \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha \beta}_{,\beta} n_\alpha d\Gamma + \int_\Gamma \boldsymbol v \cdot \boldsymbol a_3 \Gamma_{\alpha \beta}^{\gamma} M^{\alpha \beta} n_\gamma d\Gamma \\
&- \int_\Omega \boldsymbol v \cdot ((\boldsymbol a_3 M^{\alpha \beta}_{,\beta})_{,\alpha} + (\boldsymbol a_3 \Gamma_{\alpha \beta}^\gamma M^{\alpha \beta})_{,\gamma})d\Omega
\end{split}
$$
$$
\begin{split}
\boldsymbol a^\alpha \cdot (\boldsymbol M \cdot \boldsymbol a^\beta)_{,\beta}
&= \boldsymbol a^\alpha \cdot (M^{\gamma \beta} \boldsymbol a_\gamma)_{,\beta} \\
&= \boldsymbol a^\alpha \cdot M^{\gamma \beta}_{,\beta} \boldsymbol a_\gamma
+ \boldsymbol a^\alpha \cdot M^{\gamma \beta} \boldsymbol a_{\gamma,\beta} \\
&= M^{\alpha \beta}_{,\beta} + \Gamma_{\gamma\beta}^{\alpha} M^{\gamma \beta} \\
\end{split}
$$
$$
\boldsymbol b \cdot \boldsymbol M \cdot \boldsymbol n = \boldsymbol a_\gamma \boldsymbol a_3 \cdot \boldsymbol a_{,\alpha}^\gamma M^{\alpha \beta} n_\beta = - \boldsymbol a_\gamma \boldsymbol a_{3,\alpha} \cdot \boldsymbol a^\gamma M^{\alpha \beta} n_\beta = - \boldsymbol a_\gamma \Gamma_{3\beta}^\gamma M^{\alpha \beta} n_\beta
$$
$$
\boldsymbol b \cdot \boldsymbol s M_{ns} = \boldsymbol a_\gamma \boldsymbol a_3 \cdot \boldsymbol a_{,\eta}^\gamma s^\eta M^{\alpha \beta} s_\alpha n_\beta = - \boldsymbol a_\gamma \Gamma_{3\eta}^\gamma M^{\alpha \beta} s_\alpha n_\beta s^\eta
$$

# Ersatz Implementation
$$
\boldsymbol \varepsilon = \nabla^S \boldsymbol v = \frac{1}{2}(\boldsymbol a^\alpha \boldsymbol v_{,\alpha} + \boldsymbol v_{,\alpha}\boldsymbol a^\alpha)
$$
$$
\boldsymbol M \cdot \bar\nabla = \boldsymbol C : \boldsymbol \kappa \cdot \bar \nabla
$$

# New derivation
$$
\begin{split}
\int_\Omega \varepsilon_{\alpha\beta} N^{\alpha\beta}d\Omega &=
\int_\Omega \frac{1}{2}(\boldsymbol a_\alpha \cdot \boldsymbol v_{,\beta} + \boldsymbol v_{,\alpha} \cdot \boldsymbol a_\beta) N^{\alpha\beta} d\Omega \\
&= \int_\Gamma \boldsymbol v \cdot \boldsymbol a_\alpha N^{\alpha\beta} n_\beta d\Gamma - \int_\Omega \boldsymbol v \cdot (\boldsymbol a_\alpha N^{\alpha\beta})\vert_\beta d\Omega \\
\end{split}
$$
$$
\int_\Omega \boldsymbol v \cdot (\boldsymbol a_\alpha N^{\alpha\beta})_{,\beta} d\Omega = \int_\Omega \boldsymbol v \cdot \boldsymbol a_\alpha N^{\alpha\beta}\vert_\beta d\Omega + \int_\Omega \boldsymbol v \cdot \boldsymbol a_3 b_{\alpha\beta} N^{\alpha\beta}d\Omega
$$
$$
\begin{split}
\int_\Omega \kappa_{\alpha\beta} M^{\alpha\beta} d\Omega &= - \int_\Omega \boldsymbol a_\alpha \cdot (\boldsymbol a^\gamma \boldsymbol v_{,\gamma})_{,\beta} \cdot \boldsymbol a_3 M^{\alpha\beta}d\Omega \\
&= - \int_\Gamma \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha\beta} n_\beta d\Gamma
+ \int_\Omega \boldsymbol a^\gamma \boldsymbol v_{,\gamma} : (\boldsymbol a_\alpha \boldsymbol a_3 M^{\alpha\beta})\vert_\beta d\Omega \\
&= - \int_\Gamma \boldsymbol v_{,\alpha} \cdot \boldsymbol a_3 M^{\alpha\beta} n_\beta d\Gamma
+ \int_\Omega \boldsymbol v_{,\alpha} \cdot (\boldsymbol a_3 M^{\alpha\beta})\vert_\beta d\Omega \\
&= - \int_\Gamma \boldsymbol v_{,\gamma} n^\gamma \cdot \boldsymbol a_3 M^{\alpha\beta} n_\alpha n_\beta d\Gamma 
+ \int_\Gamma \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\beta} s_\alpha n_\beta s^\gamma)\vert_\gamma d\Gamma
- [[\boldsymbol v \cdot \boldsymbol a_3 M^{\alpha\beta} s_\alpha n_\beta]]_c \\
&+ \int_\Gamma \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\beta})\vert_\beta n_\alpha d\Gamma
- \int_\Omega \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\beta})\vert_{\alpha\beta} d\Omega \\
\end{split}
$$
$$
\int_\Gamma \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\beta} s_\alpha n_\beta s^\gamma)\vert_\gamma d\Gamma =
\int_\Gamma \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha\beta}_{,\gamma} s_\alpha n_\beta s^\gamma d\Gamma 
- \int_\Gamma \boldsymbol v \cdot \boldsymbol a_\eta b_\gamma^\eta M^{\alpha\beta} s_\alpha n_\beta s^\gamma d\Gamma \\
$$
$$
\int_\Gamma \boldsymbol v \cdot (\boldsymbol a_3 M^{\alpha\beta})\vert_\beta n_\alpha d\Gamma =
 \int_\Gamma \boldsymbol v \cdot \boldsymbol a_3 M^{\alpha\beta}\vert_\beta n_\alpha d\Gamma
- \int_\Gamma \boldsymbol v \cdot \boldsymbol a_\gamma b_\beta^\gamma M^{\alpha\beta} n_\alpha d\Gamma
$$
$$
\begin{split}
\int_\Omega \boldsymbol v \cdot ((\boldsymbol a_3 M^{\alpha\beta})\vert_{\alpha})\vert_\beta d\Omega &=
\int_\Omega \boldsymbol v \cdot (M^{\alpha\beta}\vert_\alpha \boldsymbol a_3 + b_{\alpha\gamma}M^{\alpha\beta}\boldsymbol a^\gamma)\vert_\beta d\Omega \\ 
&= \int_\Omega \boldsymbol v \cdot (
(M^{\alpha\beta}\vert_\alpha)\vert_\beta \boldsymbol a_3 - \boldsymbol a_\gamma b_\beta^\gamma M^{\alpha\beta}\vert_\alpha 
+ \boldsymbol a_\gamma (b_\alpha^\gamma M^{\alpha\beta})\vert_\beta + \boldsymbol a_3 b_{\alpha\gamma} b_\beta^\gamma M^{\alpha\beta})d\Gamma
\end{split}
$$
# New derivation 2
$$
\begin{split}
\boldsymbol v_{,\alpha} &= (v_i \boldsymbol a^i)_{,\alpha} \\
&= v_{i,\alpha} \boldsymbol a^i + \boldsymbol a^i_{,\alpha} v_i \\
&= v_{i,\alpha} \boldsymbol a^i - \Gamma^i_{\alpha j} v_i \boldsymbol a^j \\
&= (v_{i,\alpha} - \Gamma^j_{\alpha i} v_j) \boldsymbol a^i \\
&= (v_{\beta,\alpha} - \Gamma^j_{\alpha \beta} v_j) \boldsymbol a^\beta \\
&+ (v_{3,\alpha} - \Gamma^\gamma_{\alpha 3} v_\gamma) \boldsymbol a^3 \\
&= (v_{\beta,\alpha} - \Gamma^\gamma_{\alpha \beta} v_\gamma - \Gamma^3_{\alpha \beta} v_3) \boldsymbol a^\beta \\
&+ (v_{3,\alpha} - \Gamma^\gamma_{\alpha 3} v_\gamma) \boldsymbol a^3 \\
&= (v_\beta\vert_\alpha - b_{\alpha\beta}v_3) \boldsymbol a^\beta
+ (v_{3,\alpha} + b_\alpha^\gamma v_\gamma) \boldsymbol a^3
\end{split}
$$
$$
\begin{split}
(\boldsymbol v_{,\alpha})\vert_\beta
\end{split}
$$
$$
\begin{split}
\kappa_{\alpha\beta} &= - (\boldsymbol v_{,\alpha})\vert_\beta \cdot \boldsymbol a_3 \\
&= - (\boldsymbol a^i v_i)_{,\alpha}\vert_\beta \cdot \boldsymbol a_3 \\
&= - (v_i\vert_{\alpha}\boldsymbol a^i)\vert_\beta \cdot \boldsymbol a_3 \\
&= -v_i\vert_{\alpha\beta} \boldsymbol a^i \cdot \boldsymbol a_3 \\
&= - v_3\vert_{\alpha\beta}

\end{split}
$$
# Mixed formulation
![[∞ Mixed formulation for shell problem]]
