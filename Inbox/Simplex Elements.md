---
icon: OcInfinity16
---
#Approximation 

Consider a triangular parametric element, the Cartesian coordinates can be represented by:
$$
\begin{equation}
\boldsymbol{x} = \xi_1 \boldsymbol{x}_1 + \xi_2 \boldsymbol{x}_2 + \xi_3 \boldsymbol{x}_3
\end{equation}
$$
where
$$
\begin{equation}
\boldsymbol{x} = \{ x, y \}
\end{equation}
$$
$$
\begin{equation}
\xi_1 + \xi_2 + \xi_3 = 1
\end{equation}
$$
$$
\begin{equation}
\frac{\partial \xi_\alpha}{\partial x_i} = - \frac{D_{\alpha i}}{2A}
\end{equation}
$$
where $A$ is the area of triangular element and $D_{\alpha i}$ are  geometric parameters:
$$
\begin{equation}
\begin{Bmatrix}
D_{11} \\ D_{12}
\end{Bmatrix} =
\begin{Bmatrix}
y_3 - y_2 \\ x_2 - x_3
\end{Bmatrix},\quad
\begin{Bmatrix}
D_{21} \\ D_{22}
\end{Bmatrix} =
\begin{Bmatrix}
y_1 - y_3 \\ x_3 - x_1
\end{Bmatrix},\quad
\begin{Bmatrix}
D_{31} \\ D_{32}
\end{Bmatrix} =
\begin{Bmatrix}
y_2 - y_1 \\ x_1 - x_2
\end{Bmatrix}
\end{equation}
$$
meanwhile, an approximant of a variable $u$ denoted by $u^h$ can read as:
$$
\begin{equation}
\begin{split}
u^h &= \xi_1 a_1 + \xi_2 a_2 + \xi_3 a_3 = \xi_\alpha a_\alpha \\
u^h_{,i} &= \frac{\partial u^h}{\partial x_i} = \frac{\partial u^h}{\partial \xi_\alpha} \frac{\partial \xi_\alpha}{\partial x_i} = - \frac{a_\alpha D_{\alpha i}}{2A}
\end{split}
\end{equation}
$$
in which $a_i$'s are the unknown coefficients.
The *questions* are that
1. What is the optimal solution of $a_i$ for Galerkin method?
2. How could the error of approximation limit in each elements?
According to these questions, we lead the above approximation to Galerkin weak form, yields:
$$
\begin{equation}
E = \int_\Omega (u_{,i}-u^h_{,i})^2 d \Omega
\end{equation}
$$
$$
\begin{equation}
\frac{\partial E}{\partial a_\alpha} = 2a_\alpha \int_\Omega \frac{1}{2A} D_{\alpha i}(u_{,i} - \frac{1}{2A}D_{\beta i}a_\beta) d\Omega = 0
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\frac{1}{2A}D_{\alpha i} D_{\beta i} a_{\beta} &= \frac{1}{A} D_{\alpha i} \int_\Omega u_{,i} d\Omega \\
&=\frac{1}{A} D_{\alpha i} \sum_{\gamma = 1}^{3} \int_{\Gamma_\gamma} u n_{\gamma i} d\Gamma
\end{split}
\end{equation}
$$
where $n_i$ is the unit outward norm:
$$
\begin{equation}
n_{\gamma i} = \frac{D_{\gamma i}}{L_\gamma}
\end{equation}
$$
and $L_k$ is the length of the $k$-th side.
$$
\begin{equation}
D_{\beta i}a_\beta = D_{\gamma i} \frac{1}{L_\gamma} \int_{\Gamma_\gamma} u d\Gamma
\end{equation}
$$
$$
\begin{equation}
\sum_{\alpha = 1}^{3} a_{\alpha} = \sum_{\beta = 1}^{3} \frac{1}{L_{\beta}} \int_{\Gamma_{\beta}} u d\Gamma
\end{equation}
$$
## Consistency condition
We propose a new consistency condition for the new approximation to determine the expression of unknown coefficients:
$$
\begin{equation}
\int_{\Gamma_{\alpha}} u^h d\Gamma = \int_{\Gamma_{\alpha}} u d\Gamma
\end{equation}
$$
$$
\begin{equation}
\frac{1}{2}(a_\beta + a_\gamma) = \frac{1}{L_{\alpha}} \int_{\Gamma_{\alpha}} u d\Gamma = m_{\alpha}
\end{equation}
$$
$$
\begin{equation}
a_{\alpha} = m_{\beta} + m_{\gamma} - m_{\alpha}
\end{equation}
$$
$$
\begin{equation}
u^h = \sum_{\alpha=1}^{3} N_{\alpha} m_{\alpha}
\end{equation}
$$
$$
\begin{equation}
N_{\alpha} = \xi_\beta + \xi_\gamma - \xi_\alpha
\end{equation}
$$
$$
\begin{equation}
\begin{split}
N_{\alpha,i} &= - \frac{1}{2A} N_{\alpha,\beta} D_{\beta i} \\
&= \frac{1}{2A}(D_{\alpha i} - D_{\beta i} - D_{\gamma i}) \\
&= \frac{1}{A}D_{\alpha i}
\end{split}
\end{equation}
$$
## Galerkin method
$$
\begin{equation}
\begin{split}
K_{\alpha \beta } &= \int_{\Omega} N_{\alpha,i} N_{\beta,i} d\Omega \\
\end{split}
\end{equation}
$$
$$
\begin{equation}
f_{\alpha} = \int_{\Gamma} N_{\alpha}t d\Gamma +
\int_{\Omega} N_{\alpha} b d\Omega
\end{equation}
$$
### Boundary
Suppose that $t$ is consisted by polynomials and can be expressed by parametric coordinates:
$$
\begin{equation}
u = c_{ab} \xi_{\alpha}^a \xi_{\beta}^b, \quad
u_{,i} = -\frac{c_{ab}}{2A}(\frac{aD_{\alpha i}}{\xi_{\alpha}} + \frac{bD_{\beta i}}{\xi_{\beta}}) \xi_{\alpha}^a \xi_{\beta}^b
\end{equation}
$$
$$
\begin{equation}
t = u_{,i}n_{i} = u_{,i}\frac{D_{\alpha i}}{L_{\alpha}}, \quad \alpha = 1, 2, 3
\end{equation}
$$
For a particular boundary $L_{\gamma}$, $\xi_{\gamma} = 0$:
$$
\begin{equation}
t = u_{,i} \frac{D_{\gamma i}}{L_{\gamma}} =
- u_{,i} \frac{D_{\alpha i} + D_{\beta i}}{\Vert \boldsymbol{x}_{\alpha} - \boldsymbol{x}_{\beta} \Vert} =
\frac{c_{ab}}{2A} \frac{D_{\alpha i} + D_{\beta i}}{\Vert \boldsymbol{x}_{\alpha} - \boldsymbol{x}_{\beta} \Vert}(\frac{aD_{\alpha i}}{\xi_{\alpha}} + \frac{bD_{\beta i}}{\xi_{\beta}}) \xi_{\alpha}^a \xi_{\beta}^b
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\int_{\Gamma_{\gamma}} N_{\gamma} t d\Gamma &= \
\int_{\Gamma_{\gamma}} t d\Gamma =
\int_{\Gamma_{\gamma}} \frac{c_{ab}(D_{\alpha i} + D_{\beta i})}{2AL_{\gamma}} \frac{a!b!}{(a+b+1)!}(D_{\alpha i} + D_{\beta i}) d\Gamma \\ &=
- \frac{D_{\gamma i}^2}{2 A} c_{ab} \frac{a!b!}{(a+b+1)!} \\ &=
- \frac{D_{\gamma i}^2}{2AL_{\gamma}} \int_{\Gamma_{\gamma}} u d\Gamma
\end{split}
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\int_{\Gamma_{\gamma}} N_{\alpha} t d\Gamma &= \int_{\Gamma_{\gamma}} (\xi_{\beta}-\xi_{\alpha}) t d\Gamma \\ &=
- \frac{c_{ab} D_{\gamma i}}{2A L_{\gamma}} \int_{\Gamma_{\gamma}} (aD_{\alpha i}(\xi_{\alpha}^{a-1}\xi_{\beta}^{b+1} - \xi_{\alpha}^a \xi_{\beta}^b) +
bD_{\beta i}(\xi_{\alpha}^{a}\xi_{\beta}^{b} - \xi_{\alpha}^{a+1}\xi_{\beta}^{b-1})) d\Gamma \\ &=
- \frac{c_{ab} D_{\gamma i}}{2A L_{\gamma}} (D_{\alpha i}(b-a+1) + D_{\beta i}(b-a-1)) \frac{a!b!}{(a+b+1)!}
\end{split}
\end{equation}
$$
