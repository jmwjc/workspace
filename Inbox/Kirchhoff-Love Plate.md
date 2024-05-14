---
icon: OcInfinity16
---
#Elasticity/Plate/Thin-plate 

$$
\left \{
\begin{array}{l}
\bar{u}_{\alpha}(\boldsymbol{x}) = u_{\alpha}(x_1,x_2) - x_3 w_{,\alpha} \\
\bar{u}_{3}(\boldsymbol{x}) = w(x_1,x_2)
\end{array}
\right .
,\quad \alpha = 1,2
$$
$$
\left \{
\begin{aligned}
\varepsilon_{\alpha \beta} &=\frac{1}{2}(u_{\alpha, \beta}+u_{\beta, \alpha})-x_{3}w_{, \alpha \beta} \\
\varepsilon_{\alpha 3} &=\frac{1}{2}\left(w_{, \alpha}-w_{,\alpha}\right) = 0 \\
\varepsilon_{33} &=0
\end{aligned}
\right .
$$
$$
\begin{align}
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12} \\ \sigma_{13} \\ \sigma_{23}
\end{Bmatrix} &= 
\frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu &   \nu &   \nu & 0 & 0 & 0 \\
  \nu & 1-\nu &   \nu & 0 & 0 & 0 \\
  \nu &   \nu & 1-\nu & 0 & 0 & 0 \\
    0 &     0 &     0 & \frac{(1-2\nu)}{2} & 0 & 0 \\
    0 &     0 &     0 & 0 & \frac{(1-2\nu)}{2} & 0 \\
    0 &     0 &     0 & 0 & 0 & \frac{(1-2\nu)}{2}
\end{bmatrix}
\begin{Bmatrix}
u_{1,1} - x_3 w_{,11} \\ u_{2,2} - x_3 w_{,22} \\ 0 \\ u_{1,2}+u_{2,1}-2x_3 w_{,12} \\ 0 \\ 0
\end{Bmatrix} \\ &=
\begin{Bmatrix}
u_{1,1} - x_3 w_{,11} \\ u_{2,2} - x_3 w_{,22} \\ 0 \\ u_{1,2}+u_{2,1}-2x_3 w_{,12} \\ 0 \\ 0
\end{Bmatrix}
\end{align}
$$

# Strong form

$$
\left \{
\begin{array}{ll}
    M_{\alpha\beta,\alpha\beta}+\bar{q}=0 & \text{in} \; \Omega \\
    w = \bar{w} & \text{on} \; \Gamma^w \\
    w_{,\boldsymbol{n}} = \bar{\theta}_{\boldsymbol{n}} & \text{on} \; \Gamma^\theta \\
    M_{\boldsymbol{nn}} = \bar{M}_{\boldsymbol{nn}} & \text{on} \; \Gamma^M \\
    Q_{\boldsymbol{n}} + M_{\boldsymbol{ns},\boldsymbol{s}} = \bar{V}_{\boldsymbol{n}} & \text{on} \; \Gamma^V \\
    w_{i} = \bar{w}_{i} & i=1,2,\dots \\
    P_{j} = \bar{P}_{j} & j=1,2,\dots
\end{array}
\right .
$$
where
$$
w_{,\boldsymbol{n}} = w_{,\alpha} n_{\alpha}, \; M_{\boldsymbol{nn}} = M_{\alpha\beta} n_{\alpha} n_{\beta}, \; Q_{\boldsymbol{n}} = M_{\alpha\beta,\beta} n_{\alpha}, \; M_{\boldsymbol{ns},\boldsymbol{s}} = M_{\alpha\beta,\gamma} s_{\alpha} n_{\beta} s_{\gamma}, \; P_{j} = - \Delta_{j} M_{\boldsymbol{ns}}
$$
$$
\begin{Bmatrix}
    M_{11} \\ M_{22} \\ M_{12}
\end{Bmatrix} = -D
\begin{bmatrix}
    1 & \nu & 0 \\
    \nu & 1 & 0 \\
    0 & 0 & \frac{1-\nu}{2}
\end{bmatrix}
\begin{Bmatrix}
    w_{,11} \\ w_{,22} \\ 2w_{,12}
\end{Bmatrix}
$$
$$
D=\frac{h^3E}{12(1-\nu^2)}
$$

# Weak form

Energy functional:
$$
\Pi(M_{\alpha\beta}) = \int_{\Omega} \frac{1}{2} M_{\alpha\beta} d_{\alpha\beta\gamma\eta}M_{\gamma\eta}d\Omega - 
\int_{\Gamma^w} V_{\boldsymbol{n}} \bar{w} d\Gamma +
\int_{\Gamma^\theta} M_{\boldsymbol{nn}} \bar{\theta}_{\boldsymbol{n}} d\Gamma - \sum_i P_i \bar{w}_i
$$
$$
\begin{multline}
\Pi'(M_{\alpha\beta},w) = \Pi(M_{\alpha\beta}) + \int_{\Omega} w (M_{\alpha\beta,\alpha\beta}+\bar{q})d\Omega \\ +
\int_{\Gamma^M} w_{,\boldsymbol{n}}(M_{\boldsymbol{nn}} - \bar{M}_{\boldsymbol{nn}}) d\Gamma -
\int_{\Gamma^V} w(V_{\boldsymbol{n}} - \bar{V}_{\boldsymbol{n}}) d\Gamma - \sum_{j} w_j (P_j-\bar{P}_j)
\end{multline}
$$
weak form:
$$
\begin{align}
\int_\Omega \delta M_{\alpha\beta} d_{\alpha\beta\gamma\eta}M_{\gamma\eta} d\Omega + 
\int_{\Omega} \delta M_{\alpha\beta,\alpha\beta} w d\Omega +
\int_{\Gamma^M} \delta M_{\boldsymbol{nn}} w_{,\boldsymbol{n}} d\Gamma -
\int_{\Gamma^V} \delta V_{\boldsymbol{n}} w d\Gamma - \sum_{j} \delta P_j w_j =
\int_{\Gamma^w} \delta V_{\boldsymbol{n}} \bar{w} d\Gamma -
\int_{\Gamma^\theta} \delta M_{\boldsymbol{nn}} \bar{\theta}_{\boldsymbol{n}} d\Gamma + \sum_i \delta P_i \bar{w}_i \\
-\int_{\Omega} \delta w M_{\alpha\beta,\alpha\beta}d\Omega -
\int_{\Gamma^M} \delta w_{,\boldsymbol{n}}M_{\boldsymbol{nn}} d\Gamma +
\int_{\Gamma^V} \delta w V_{\boldsymbol{n}} d\Gamma + \sum_{j} \delta w_j P_j = 
\int_{\Omega} \delta w \bar{q}d\Omega -
\int_{\Gamma^M} \delta w_{,\boldsymbol{n}}\bar{M}_{\boldsymbol{nn}} d\Gamma +
\int_{\Gamma^V} \delta w \bar{V}_{\boldsymbol{n}} d\Gamma + \sum_{j} \delta w_j \bar{P}_j
\end{align}
$$
assuming that
$$
M_{\alpha\beta}(\boldsymbol{x}) = \boldsymbol{a}_{\alpha\beta}^T \boldsymbol{q}({\boldsymbol{x}}), \; w(\boldsymbol{x}) = \sum_{I=1}^{n_p} \Psi_I(\boldsymbol{x}) d_I
$$
$$
\delta \boldsymbol{a}_{\alpha\beta}^T (d_{\alpha\beta\gamma\eta}\int_{\Omega} \boldsymbol{q} \boldsymbol{q}^T d\Omega \boldsymbol{a}_{\gamma\eta} + \sum_{I=1}^{n_p}(\boldsymbol{g}_{\alpha\beta I} - \boldsymbol{g}_{\alpha\beta I}^{\theta} + \boldsymbol{g}_{\alpha\beta I}^{w} + \boldsymbol{g}_{\alpha\beta I}^{w_i}) d_{I}) = \boldsymbol{a}_{\alpha\beta}^T f_{\alpha\beta}
$$
$$
\boldsymbol{g}_{\alpha\beta I} = \int_{\Gamma} \Psi_{I,\gamma} \boldsymbol{q} n_\alpha n_\beta n_\gamma d\Gamma - \int_{\Gamma} \Psi_I (\boldsymbol{q}_{,\beta} n_\alpha + \boldsymbol{q}_{,\gamma} s_\alpha n_\beta s_\gamma) d\Gamma + \sum_k \Psi_I(\boldsymbol{x}_k)\Delta (\boldsymbol{q} s_\alpha n_\beta)
$$
$$
\boldsymbol{g}_{\alpha\beta I}^\theta = \int_{\Gamma^\theta} \Psi_{I,\gamma} \boldsymbol{q} n_\alpha n_\beta n_\gamma d\Gamma
$$
$$
\boldsymbol{g}_{\alpha\beta I}^w = \int_{\Gamma^w} \Psi_I (\boldsymbol{q}_{,\beta} n_\alpha + \boldsymbol{q}_{,\gamma} s_\alpha n_\beta s_\gamma) d\Gamma
$$
$$
\boldsymbol{g}_{\alpha\beta I}^{w_i} = \sum_j \Psi_I(\boldsymbol{x}_j) \Delta (\boldsymbol{q} s_\alpha n_\beta)
$$
$$
\boldsymbol{a}_{\alpha\beta} = d_{\alpha\beta\gamma\eta}^{-1} \boldsymbol{G}^{-1}(f_{\alpha\beta} - \sum_{I=1}^{n_p}(\boldsymbol{g}_{\alpha\beta I} - \boldsymbol{g}_{\alpha\beta I}^{\theta} + \boldsymbol{g}_{\alpha\beta I}^{w} + \boldsymbol{g}_{\alpha\beta I}^{w_i}) d_{I})
$$
$$
\sum_{I=1}^{n_p} \delta d_I(\boldsymbol{g}_{\alpha\beta I}^T - \boldsymbol{g}_{\alpha\beta I}^{\theta T} + \boldsymbol{g}_{\alpha\beta I}^{w T} + \boldsymbol{g}_{\alpha\beta I}^{w_i T}) \boldsymbol{a}_{\alpha\beta} = \sum_{I=1}^{n_p} \delta d_I f_I
$$
