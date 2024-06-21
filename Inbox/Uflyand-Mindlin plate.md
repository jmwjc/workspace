---
icon: OcInfinity16
---

#Elasticity/Plate/Thick-plate 

# Kinematics
Consider a thick plate $\bar \Omega$ with thickness $h$, the displacement $\bar u_i, i=1,2,3$, can always be reduced to a linear function with respect to $x_3$. It can be expressed in terms of mid-plate displacement $u_\alpha$ and rotation $\varphi_\alpha$, $\alpha=1,2$, as follows
$$
\left \{
\begin{array}{l}
\bar{u}_{\alpha}(\boldsymbol{x}) = u_{\alpha}(x_1,x_2) - x_3 \varphi_{\alpha}(x_1,x_2) \\
\bar{u}_{3}(\boldsymbol{x}) = w(x_1,x_2)
\end{array}
\right .
,\quad \alpha = 1,2
$$
Substituting this displacement into [[Linear Elasticity#^605c91|kinematics relation]] yields the corresponding strain
$$
\left \{
\begin{split}
\epsilon_{\alpha \beta} &=\varepsilon_{\alpha\beta} + \kappa_{\alpha\beta} x_3 = \frac{1}{2}\left(u_{\alpha, \beta}+u_{\beta, \alpha}\right)-\frac{x_{3}}{2}\left(\varphi_{\alpha, \beta}+\varphi_{\beta, \alpha}\right) \\
\epsilon_{\alpha 3} &=\frac{1}{2}k\gamma_{\alpha} = \frac{1}{2}\left(w_{, \alpha}-\varphi_{\alpha}\right) \\
\epsilon_{33} &=0
\end{split}
\right .
$$
where
$$
\varepsilon_{\alpha\beta} =\frac{1}{2}(u_{\alpha,\beta} + u_{\beta,\alpha})
$$
$$
\kappa_{\alpha\beta} = -\frac{1}{2}(\varphi_{\alpha,\beta} + \varphi_{\beta,\alpha})
$$
$$
\gamma_\alpha = w_{,\alpha} - \varphi_\alpha
$$
Here, $k$ represents the *shear correction factor*, correcting the amount of internal energy. $\varepsilon_{\alpha\beta}$, $\kappa_{\alpha\beta}$ and $\gamma_\alpha$ are in-plate strain, curvature and shear strain, respectively. Unlike with [[Kirchhoff-Love Plate|Kirchhoff-Love hypothesis]], the shear strain of Uflyand-Mindlin hypothesis cannot be eliminated, i.e. $\gamma_\alpha \ne 0$, $\varphi_\alpha \ne w_{,\alpha}$. 

# Galerkin weak form
The internal force in [[Linear Elasticity#Galerkin formulation|elasticity weak form]] can be rephrased using strains and stresses in thick plate's mid-plate
$$
\begin{split}
\int_{\bar \Omega} \delta \epsilon_{ij} \sigma_{ij} d\Omega &=
\int_{\Omega}\int_{-\frac{h}{2}}^{\frac{h}{2}} \delta \epsilon_{\alpha\beta} \sigma_{\alpha\beta} + 2\delta \epsilon_{3 \alpha} \sigma_{3\alpha} dx_3 d\Omega \\
&=\int_{\Omega}\int_{-\frac{h}{2}}^{\frac{h}{2}} (\delta \varepsilon_{\alpha\beta} + \delta \kappa_{\alpha\beta} x_3) \sigma_{\alpha\beta} dx_3 d\Omega + \int_\Omega\int_{-\frac{h}{2}}^{\frac{h}{2}} k\delta \gamma_\alpha \sigma_{3\alpha} dx_3 d\Omega \\
&=\int_{\Omega}(\delta \varepsilon_{\alpha\beta}\underbrace{\int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{\alpha\beta} dx_3}_{N_{\alpha\beta}}
+ \delta \kappa_{\alpha\beta} \underbrace{\int_{-\frac{h}{2}}^{\frac{h}{2}} x_3 \sigma_{\alpha\beta} dx_3}_{M_{\alpha\beta}}) d\Omega 
+ \int_\Omega\delta \gamma_\alpha \underbrace{k\int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{3\alpha} dx_3}_{Q_\alpha} d\Omega\\
&= \int_\Omega \delta \varepsilon_{\alpha\beta} N_{\alpha\beta} + \delta \kappa_{\alpha\beta} M_{\alpha\beta} + \delta \gamma_\alpha Q_\alpha d\Omega
\end{split}
$$
where $N_{\alpha\beta}$, $M_{\alpha\beta}$ and $Q_\alpha$ are in-plane stress-, moment- and shear-resultants, respectively. For an isotropic elastic material, the stress components, assuming $\sigma_{33}=0$, are given by
$$
\left \{
\begin{split}
\sigma_{\alpha\beta} &= \frac{E}{1-\nu^2} (\nu\delta_{\alpha\beta} \epsilon_{\gamma\gamma} + (1-\nu) \epsilon_{\alpha\beta}) = D_{\alpha\beta\gamma\eta} \epsilon_{\alpha\beta} \\
\sigma_{\alpha 3} &=\frac{E}{2(1+\nu)} \gamma_\alpha
\end{split}
\right .
$$
in which $D_{\alpha\beta\gamma\eta}$ denotes to the components of the fourth order elasticity tensor, and has the following form
$$
D_{\alpha\beta\gamma\eta} = \frac{E}{1-\nu^2}(\nu \delta_{\alpha\beta}\delta_{\gamma\eta} +\frac{1}{2}(1-\nu)(\delta_{\alpha\gamma}\delta_{\beta\eta} + \delta_{\alpha\eta}\delta_{\beta\gamma}))
$$
and the stress resultants can be further expressed using in-plane strain, curvature and shear strain as
$$
N_{\alpha\beta} = \int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{\alpha\beta} dx_3 = h D_{\alpha\beta\gamma\eta} \varepsilon_{\gamma\eta}
$$
$$
M_{\alpha\beta} = \int_{-\frac{h}{2}}^{\frac{h}{2}} x_3 \sigma_{\alpha\beta} dx_3 = \frac{h^3}{12}D_{\alpha\beta\gamma\eta} \kappa_{\gamma\eta}
$$
$$
Q_\alpha = k\int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{3\alpha} dx_3 = k\frac{Eh}{2(1+\nu)} \gamma_\alpha = kGh \gamma_\alpha
$$

At this circumstance, the weak form of thick plate formulation can be reduced using integration by parts
$$
\begin{split}
&\int_\Omega \delta \varepsilon_{\alpha\beta} N_{\alpha\beta} + \delta \kappa_{\alpha\beta} M_{\alpha\beta} + \delta \gamma_\alpha Q_\alpha d\Omega \\
=& \int_{\Gamma_N} \delta u_\alpha \bar T_\alpha d\Gamma - \int_{\Gamma_M} \delta \varphi_\alpha \bar M_{\alpha} d\Gamma + \int_{\Gamma_Q} \delta w \bar Q d\Gamma - \int_\Omega \delta w \bar q d\Omega \\
\Rightarrow& \int_{\Gamma_N} \delta u_\alpha (N_{\alpha\beta} n_\beta - \bar T_\alpha) d\Gamma
- \int_\Omega \delta u_\alpha (N_{\alpha\beta,\beta} + \bar b_\alpha) d\Omega \\
-& \int_{\Gamma_M} \delta \varphi_\alpha(M_{\alpha\beta} n_\beta - \bar M_\alpha) d\Gamma 
+ \int_\Omega \delta \varphi_\alpha(M_{\alpha\beta,\beta} - Q_\alpha)d\Omega \\
+& \int_{\Gamma_Q} \delta w (Q_\alpha n_\alpha - \bar Q) d\Gamma
- \int_\Omega \delta w (Q_{\alpha,\alpha} + \bar q) d\Omega = 0
\end{split}
$$
It can be observed from the above equation that, the corresponding strong form regarding in-plane displacement is almost identical with that of [[Linear Elasticity#Plane strain and plane stress|plane stress problems]]. In constrast, the strong form regarding deflection and rotation can be got as follows
$$
\begin{cases}
M_{\alpha\beta,\beta} - Q_\alpha = 0 & \textrm{in}\; \Omega \\
Q_{\alpha,\alpha} + \bar q = 0 & \textrm{in}\; \Omega \\
Q_\alpha n_\alpha = \bar Q & \textrm{on}\; \Gamma_Q \\
M_{\alpha\beta} n_\beta = \bar M_\alpha & \textrm{on}\; \Gamma_M \\
\varphi_\alpha = \bar \varphi_\alpha & \textrm{on}\; \Gamma_\varphi \\
w = \bar w & \textrm{on}\; \Gamma_w \\
\end{cases}
$$

# Numerical formulation
In numerical formulation, the displacement and rotation can be approximated in terms of shape functions and nodal coefficients
$$
w^h(\boldsymbol x) = \sum_{I=1}^{n_p} N_I(\boldsymbol x) w_I, \quad
\varphi^h_\alpha(\boldsymbol x) = \sum_{I=1}^{n_p} N_I(\boldsymbol x) \varphi_{\alpha I}
$$
the corresponding approximated strains can be rephrased as
$$
\boldsymbol \kappa^h = 
\begin{Bmatrix}
\kappa^h_{11} \\ \kappa^h_{22} \\ 2\kappa^h_{12} 
\end{Bmatrix} = -\sum_{I=1}^{n_p}
\begin{bmatrix}
0 & N_{I,1} & 0 \\ 0 & 0 & N_{I,2} \\ 0 & N_{I,2} & N_{I,1}
\end{bmatrix}
\begin{Bmatrix}
w_I \\ \varphi_{1I} \\ \varphi_{2I}
\end{Bmatrix} = - \sum_{I=1}^{n_p} \boldsymbol B^b_I \boldsymbol d_I
$$
$$
\boldsymbol \gamma^h = 
\begin{Bmatrix}
\gamma^h_1 \\ \gamma^h_2
\end{Bmatrix} = \sum_{I=1}^{n_p}
\begin{bmatrix}
N_{I,1} & N_I & 0 \\
N_{I,2} & 0 & N_I
\end{bmatrix}
\begin{Bmatrix}
w_I \\ \varphi_{1I} \\ \varphi_{2I}
\end{Bmatrix} = \sum_{I=1}^{n_p} \boldsymbol B^s_I \boldsymbol d_I
$$
Substituting discrete strain into weak form leads to the following discrete equilibrium equation
$$
(\boldsymbol K^b + \boldsymbol K^s) \boldsymbol d = \boldsymbol f
$$
where $\boldsymbol K^b$ and $\boldsymbol K^s$ are the stiffness matrices with following components
$$
\boldsymbol K^b_{IJ} = \frac{h^3}{12} \int_\Omega \boldsymbol B^{bT}_I \boldsymbol D \boldsymbol B^b_J d\Omega
$$
$$
\boldsymbol K^s_{IJ} = h \int_\Omega \boldsymbol B^{sT}_I kG \boldsymbol B^s_J d\Omega
$$
with $\boldsymbol D$ is the [[Linear Elasticity#^91dd38|plane stress elasticity matrix]].
And $\boldsymbol f$ is the force vector, its components have the following form
$$
\boldsymbol f_I = \int_{\Gamma_Q} N_I \bar{\boldsymbol Q} d\Gamma - \int_{\Gamma_M} N_I \bar{\boldsymbol M} d\Gamma + \int_\Omega N_I \bar{\boldsymbol q} d\Omega
$$
with
$$
\bar{\boldsymbol Q} = 
\begin{Bmatrix}
\bar Q \\ 0 \\ 0
\end{Bmatrix}, \quad
\bar{\boldsymbol M} =
\begin{Bmatrix}
0 \\ \bar M_1 \\ \bar M_2
\end{Bmatrix}, \quad
\bar{\boldsymbol q} =
\begin{Bmatrix}
\bar q \\ 0 \\ 0
\end{Bmatrix}
$$
# Mixed formulation
To alleviate the shear locking cause by the reduction of thickness, the approximation of shear-resultant $Q_\alpha$'s is usually independent with displacement and rotation 
$$
Q^h_\alpha(\boldsymbol x) = \sum_{K=1}^{n_q} \Psi_K(\boldsymbol x) q_{\alpha K}
$$
The corresponding weak form and discrete equilibrium equations are formulated accordingly as follows
$$
\begin{align}
\int_\Omega \delta \kappa_{\alpha\beta} M_{\alpha\beta} d\Omega + \int_\Omega \delta \gamma_\alpha Q_\alpha d\Omega
&= \int_{\Gamma_N} \delta u_\alpha \bar T_\alpha d\Gamma - \int_{\Gamma_M} \delta \varphi_\alpha \bar M_{\alpha} d\Gamma + \int_{\Gamma_Q} \delta w \bar Q d\Gamma - \int_\Omega \delta w \bar q d\Omega \\
\int_\Omega \delta Q_\alpha \gamma_\alpha d\Omega -\frac{1}{kGh} \int_\Omega \delta Q_\alpha Q_\alpha d\Omega &= 0
\end{align}
$$
$$
\begin{bmatrix}
\boldsymbol K^b & \boldsymbol K^{wq} \\
\boldsymbol K^{wqT} & \boldsymbol K^{qq}
\end{bmatrix}
\begin{Bmatrix}
\boldsymbol d \\ \boldsymbol q
\end{Bmatrix}= 
\begin{Bmatrix}
\boldsymbol f \\ \boldsymbol 0
\end{Bmatrix}
$$
where the components of $\boldsymbol K^{wq}$ and $\boldsymbol K^{qq}$ can be evaluated by
$$
\boldsymbol K^{wq}_{IK} = \int_\Omega \boldsymbol B^{sT}_I \Psi_K d\Omega
$$
$$
\boldsymbol K^{qq}_{KL} = -\frac{1}{kGh} \int_\Omega \Psi_K \Psi_L \boldsymbol 1 d\Omega
$$
where $\boldsymbol 1$ is second order identity tensor.
