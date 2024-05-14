---
icon: OcInfinity16
---

#Approximation/Crouzeix-Raviart 
## Triangular element

Suppose that a variable $u$ in a triangular domain $\Omega_{C}$ approximates by a linear function as

$$
u^{h} = a_{1} \xi_{1} + a_{2} \xi_{2} + a_{3} \xi_{3}, \quad \xi_{1} + \xi_{2} + \xi_{3} = 1
$$
 where the $a_{i},i=1,2,3$ are constant parameters. $\xi$ and $\eta$ are two parametric coordinates based upon triangular element. The mapping between Cartesian coordinates $x,y$ and parametric coordinates $\xi,\eta$ can be expressed as
 
$$
\left \{ \begin{array}{l}
x = x_{1} \xi_{1} + x_{2} \xi_{2} + x_{3} \xi_{3} \\
y = y_{1} \xi_{1} + y_{2} \xi_{2} + x_{3} \xi_{3}
\end{array}\right .
$$
In traditional triangular element approximation, the parameters $a_{i}$ equal to the value of $u$ at the vertex in triangular domain, as

$$
\left \{ \begin{array}{l}
a_{1} = u(\boldsymbol{x}_{1}) = u_{1} \\
a_{2} = u(\boldsymbol{x}_{2}) = u_{2} \\
a_{3} = u(\boldsymbol{x}_{3}) = u_{3}
\end{array} \right.
$$
 since this expression of the approximant $u^{h}$ interpolate the function $u$, and can exactly represent a linear function.

In this work, we aim to build a new approximation framework that its parameters $a_{i}$ is determined by a integration instead of interpolation. The consistent condition is replaced by 

$$
\begin{align}
\int_{\Gamma_{C}^{i}} u^{h} d\boldsymbol{x} = \int_{\Gamma_{C}^{i}} u d\boldsymbol{x}\\
\left \{ \begin{array}{left}
a_{2} + a_{3} = \frac{2}{\ell_{1}}\int_{\Gamma_{C}^{1}} u d\boldsymbol{x} = 2m_{1}\\
a_{3} + a_{1} = \frac{2}{\ell_{2}}\int_{\Gamma_{C}^{2}} u d\boldsymbol{x} = 2m_{2}\\
a_{1} + a_{2} = \frac{2}{\ell_{3}}\int_{\Gamma_{C}^{3}} u d\boldsymbol{x} = 2m_{3}
\end{array} \right .\\
\left \{ \begin{array}{left}
m_{1} = \frac{1}{\ell_{1}}\int_{\Gamma_{C}^{1}} u d\boldsymbol{x}\\
m_{2} = \frac{1}{\ell_{2}}\int_{\Gamma_{C}^{2}} u d\boldsymbol{x}\\
m_{3} = \frac{1}{\ell_{3}}\int_{\Gamma_{C}^{3}} u d\boldsymbol{x}
\end{array} \right .\\
\ell_{1} m_{1} + \ell_{2} m_{2} + \ell_{3} m_{3} = 0
\end{align}
$$

$$
a_{1} = m_{2} + m_{3} - m_{1} \quad 
a_{2} = m_{3} + m_{1} - m_{2} \quad 
a_{3} = m_{1} + m_{2} - m_{3}
$$

then the approximant $u^{h}$ has the form that

$$
\begin{split}
u^{h} &= (\xi_{2}+\xi_{3}-\xi_{1})m_{1} + 
(\xi_{3}+\xi_{1}-\xi_{2})m_{2} + 
(\xi_{1}+\xi_{2}-\xi_{3})m_{3}\\
&= N_{1} m_{1} + N_{2} m_{2} + N_{3} m_{3}
\end{split}
$$
where $N_{I}$ are the shape functions. The gradient of the approximant $u^{h}$ is given by

$$
\nabla u^{h} = 
\begin{Bmatrix}
u_{,x}^{h} \\ u_{,y}^{h}
\end{Bmatrix} = 
\frac{1}{A_{C}}
\begin{bmatrix}
D_{11} & D_{21} & D_{31} \\
D_{12} & D_{22} & D_{32}
\end{bmatrix}
\begin{Bmatrix}
m_{1} \\ m_{2} \\ m_{3}
\end{Bmatrix}
$$

$$
\boldsymbol{B}_{1} = \frac{1}{A_{C}} \begin{Bmatrix} D_{11} \\ D_{12} \end{Bmatrix} \quad 
\boldsymbol{B}_{2} = \frac{1}{A_{C}} \begin{Bmatrix} D_{21} \\ D_{22} \end{Bmatrix} \quad
\boldsymbol{B}_{3} = \frac{1}{A_{C}} \begin{Bmatrix} D_{31} \\ D_{32} \end{Bmatrix} \quad
$$

## Galerkin method

We lead the new approximation to the following Galerkin weak form

$$
\int_{\Omega} \nabla \delta u^{h} \cdot \nabla u^{h} d\Omega = 
\int_{\Gamma^{t}} \delta u^{h} \bar{t} d\Gamma +
\int_{\Omega} \delta u^{h} \bar{b} d\Omega
$$
in each element, the local Galerkin weak form can be rewritten as

$$
\int_{\Omega_{C}} \nabla \delta u^{h} \cdot \nabla u^{h} d\Omega = 
\int_{\Gamma_{C}} \delta u^{h} \nabla u \cdot \boldsymbol{n} d\Gamma -
\int_{\Omega_{C}} \delta u^{h} \Delta u d\Omega
$$

Internal force
$$
\int_{\Omega_C} \delta u^h_{,k} u^h_{,k} d\Omega =
\delta m_i \frac{1}{A_C} D_{ik} D_{jk} m_j
$$

## Least square

$$
\begin{equation}
J=\frac{1}{2}\int_{\Omega} (\nabla u^{h} - \nabla u)^{2} \mathrm{d} \boldsymbol{x}
\end{equation}
$$


$$
\begin{equation}
\frac{\partial J}{\partial m_{I}} = \int_{\Omega} \boldsymbol{B}_{I}^{T} \boldsymbol{B}_{J} \mathrm{d} \boldsymbol{x} m_{J} 
- \int_{\Omega} \boldsymbol{B}_{I}^{T} \nabla u \mathrm{d} \boldsymbol{x} = 0
\end{equation}
$$


$$
\begin{equation}
\int_{\Omega} \boldsymbol{B}_{I}^{T} \boldsymbol{B}_{J} \mathrm{d} \boldsymbol{x} m_{J} = 
\int_{\Gamma} N_{I} u_{,\boldsymbol{n}} \mathrm{d}\boldsymbol{x} - \int_{\Omega} N_{I} \nabla \cdot \nabla u \mathrm{d} \boldsymbol{x}
\end{equation}
$$

$$
\begin{equation}
\int_{\Gamma} N_{I} u_{,\boldsymbol{n}} \mathrm{d}\boldsymbol{x} = 
\int_{\Gamma_{1}+\Gamma_{2}+\Gamma_{3}} N_{I} u_{,\boldsymbol{n}} \mathrm{d}\boldsymbol{x} =
g_{1} + g_{2} + g_{3}
\end{equation}
$$

## Example


**Cell 1:**



$$
\begin{equation}
A = 0.25
\end{equation}
$$

$$
\begin{equation}
\begin{bmatrix}
D_{11} & D_{12} & D_{13} \\
D_{21} & D_{22} & D_{23}
\end{bmatrix} = 
\begin{bmatrix}
-1 &  0.5 & 0.5 \\
 0 & -0.5 & 0.5
\end{bmatrix} 
\end{equation}
$$


Stiffness

$$
\begin{equation}
\boldsymbol{K} = 
\begin{bmatrix}
   1 & -0.5 & -0.5 \\
-0.5 &  0.5 &    0 \\
-0.5 &    0 &  0.5
\end{bmatrix}
\end{equation}
$$

Force vector

$$
\begin{equation}
f_{I} = \int_{\Gamma} N_{I} \bar{t} \mathrm{d} \boldsymbol{x} + \int_{\Omega} N_{I} \bar{b} \mathrm{d} \boldsymbol{x}
\end{equation}
$$

# (test::Boundary recovery 1)
(data::2024-04-22)
$$
\begin{split}
\int_{\Gamma_j} N_I f_{,k} n_k d\Gamma
&= -\frac{1}{2A} \int_{\Gamma_j} N_I f_{,i} D_{ik} \bar D_{jk} d\Gamma \\
&= -\frac{1}{2A} D_{ik} \bar D_{jk} \int_{\Gamma_j} N_I f_{,i} d\Gamma \\
\end{split}
$$
$$
N_I = \begin{cases}
1 & I = k \\
2\xi_{k-1} = - 2\xi_{k+1} = 2\xi & I = k-1 \\
2\xi_{k+1} = - 2\xi_{k-1} = -2\xi & I = k+1 \\
\end{cases}
$$
$$
f = \sum_{n=0}^p f^n, \quad f^n(\lambda \boldsymbol x) = \lambda^n f^n(\boldsymbol x)
$$
$$
\begin{split}
\frac{1}{L_j}\int_{\Gamma_j} \xi f_{,\xi} d\Gamma &= \sum_{n=0}^p \int_{\Gamma_j} \xi f_{,\xi}^n d\Gamma \\
&= \sum_{n=0}^p \frac{1}{L_j} \int_{\Gamma_j} n f^n d\Gamma
&= \sum_{n=0}^p n m_j^n
\end{split}
$$

# (test::Boundary recovery 2)
(data::2024-05-03)
$$
\begin{split}
\boldsymbol x &= (\xi_2+\xi_3-\xi_1) \frac{\boldsymbol x_2+\boldsymbol x_3}{2} + (\xi_3+\xi_1-\xi_2) \frac{\boldsymbol x_3+\boldsymbol x_1}{2} + (\xi_1+\xi_2-\xi_3) \frac{\boldsymbol x_1+\boldsymbol x_2}{2} \\
&= N_1 \frac{\boldsymbol x_2+\boldsymbol x_3}{2} + N_2 \frac{\boldsymbol x_3+\boldsymbol x_1}{2} + N_3 \frac{\boldsymbol x_1+\boldsymbol x_2}{2}
\end{split}
$$
$$
\begin{Bmatrix}
x \\ y
\end{Bmatrix} =\frac{1}{2}
\begin{bmatrix}
x_3-x_1 & x_3-x_2 \\ y_3-y_1 & y_3-y_2
\end{bmatrix}
\begin{Bmatrix}
N_1 \\ N_2
\end{Bmatrix}
$$
$$
\begin{Bmatrix}
N_1 \\ N_2
\end{Bmatrix} =\frac{1}{A}
\begin{bmatrix}
y_3-y_2 & y_1-y_3 \\
x_2-x_3 & x_3-x_1
\end{bmatrix}
\begin{Bmatrix}
x \\ y
\end{Bmatrix}
$$
$$
\begin{Bmatrix}
x \\ y
\end{Bmatrix} =\frac{1}{2}
\begin{bmatrix}
x_2-x_1 & x_2-x_3 \\ y_2-y_1 & y_2-y_3
\end{bmatrix}
\begin{Bmatrix}
N_1 \\ N_3
\end{Bmatrix}
$$
$$
\begin{Bmatrix}
N_1 \\ N_3
\end{Bmatrix} =\frac{1}{A}
\begin{bmatrix}
y_3-y_2 & y_2-y_1 \\
x_2-x_3 & x_1-x_2
\end{bmatrix}
\begin{Bmatrix}
x \\ y
\end{Bmatrix}
$$
$$
\begin{split}
\int_{\Gamma_j} N_I f_{,k} n_k d\Gamma &=\frac{1}{A}\frac{1}{L_j}\int_{\Gamma_j} N_I f_{,N_i} D_{ik}D_{jk} d\Gamma
\end{split}
$$
