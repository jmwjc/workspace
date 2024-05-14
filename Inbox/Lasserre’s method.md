---
icon: OcInfinity16
---

#Math/Integration #Approximation/RKGSI #Approximation/Arbitrary-polygon

# Integration of $p$-homogeneous function
A function $f: \mathbb{R}^n\rightarrow \mathbb{R}$ is said to be $p$-homogeneous, such that $f(\lambda \boldsymbol x) = \lambda^p f(\boldsymbol x), \; \forall \lambda>0,\boldsymbol x \in \mathbb{R}^n$. For a $p$-homogeneous function $f$ that is continuously differentiable, **Euler's formula** states that
$$
p f(\boldsymbol x) = \nabla f(\boldsymbol x) \cdot \boldsymbol x = f_{,i}x_i, \quad \forall \boldsymbol x
$$
Introducing the *Riemann-Green* formula herein
$$
\int_{\Omega} pf d\Omega = \int_{\Omega} x_i f_{,i} d\Omega = \int_{\partial \Omega} f x_i n_i d\partial \Omega - n \int_{\Omega} f d\Omega
$$
or equivalent
$$
\int_{\Omega} f d\Omega = \frac{1}{p+n}\int_{\partial \Omega} f x_i n_i d\partial \Omega
$$

As a conclusion, a boundary integration scheme with $p+1$-th order, like **Gauss-Lobatto**, can be applied in this formula to integrate $f$ in $\Omega$.

# Integration of a linear combination of $p$-homogeneous functions
Let $f$ set to be a linear combination of $p$-homogeneous functions, as
$$
f(\boldsymbol x) = \sum_{i=0}^p f_i(\boldsymbol x), \quad f_i(\lambda \boldsymbol x) = \lambda^i f_i(\boldsymbol x)
$$
the integration of $f$ referring to $\lambda \boldsymbol x$ in $\Omega$ is given by
$$
\int_{\Omega} f(\lambda \boldsymbol x) d\Omega = \sum_{i=1}^p \int_{\Omega} f_i(\lambda \boldsymbol x) d\Omega = \sum_{i=0}^p \lambda^i \int_{\Omega} f_i(\boldsymbol x) d\Omega
$$
combining the equation in previous section yields
$$
\int_{\partial \Omega}f(\lambda \boldsymbol x) x_j n_j d\partial \Omega = \sum_{i=1}^p \lambda^i(i+n) \int_{\Omega} f_i(\boldsymbol x)d\Omega
$$
with $p$ different $\lambda$, the above equation can be rewritten as the following linear equations
$$
\sum_{j=1}^p \lambda_i^j(n+j) \int_{\Omega} f_j(\boldsymbol x) d\Omega = \int_{\partial \Omega} f(\lambda_i \boldsymbol x) x_k n_k d\partial \Omega
$$
that can be expressed by a matrix form
$$
\boldsymbol A \boldsymbol I = \boldsymbol q
$$
where
$$
\left \{
\begin{split}
&A_{ij} = \lambda_i^j(n+j) \\
&q_i = \int_{\partial \Omega} f(\lambda_i \boldsymbol x) x_k n_k d\partial \Omega \\
&I_j = \int_{\Omega} f_j(\boldsymbol x) d\Omega
\end{split}
\right .
$$
the final integration of $f$ can be evaluated by
$$
\int_{\Omega} f d\Omega = \sum_{i=0}^p I_i
$$

# Further reduction for integration of homogeneous function
For two dimensional case, $n=2$, the boundary integration in above equations can further reduce to integration by points
$$
\begin{split}
\int_{\Omega} f d\Omega &= \frac{x_i n_i}{p+2}\int_{\partial \Omega} f d\partial \Omega \\
&=\frac{1}{p+2} \sum_{k} \frac{x_ky_{k+1}-x_{k+1}y_k}{L_k}\int_{\partial \Omega_k} f d\partial \Omega \\
\end{split}
$$
where $\boldsymbol x_k$'s is the vertices. Again, the *Riemann-Green* formula with $n=1$ is used herein
$$
\int_{\partial \Omega_k} f d\partial \Omega = \frac{L_k}{p+1} f(\boldsymbol x_{k+1})
$$
combining these two equations yields
$$
\int_{\Omega} f d\Omega = \frac{1}{(p+2)(p+1)} \sum_{k} (x_ky_{k+1}-x_{k+1}y_k) f(\boldsymbol x_{k+1}) \\
$$

# Reduction for 1D case
For one dimensional case, $n=1$, a integration of $p$-homogeneous$ function $f$ can be evaluated by
$$
\int_{x_1}^{x_2} pf dx = \int_{x_1}^{x_2} x f_{,x} dx = f x n_x \vert_{x_1}^{x_2} - \int_{x_1}^{x_2} f dx
$$
or equivalently
$$
\int_{x_1}^{x_2} f dx = \frac{1}{p+1} (f(x_2) x_2 - f(x_1) x_1)
$$
where $n_x(x_1) = -1$, $n_x(x_2) = 1$.

It is noted that, as we involve the parametric coordinate $s, s\in[0,1]$, such that $x = sx_2 + (1-s)x_1$, and $f$ lose the property of $p$-homogeneous referring to $s$ as
$$
f(\lambda s) = c(\lambda s x_2 + (1-\lambda s)x_1)^p = c (\lambda Ls+x_1)^p 
$$

# (test::Boundary integration in 2D, basis function:$k(x-x_1)+y_1$)
(data::2023-1-26)
$$
\begin{split}
\frac{1}{L}\int_{\Gamma} f d\Gamma &= \frac{\sqrt{1+k^2}}{L} \int_{x_1}^{x_2} f(x,k(x-x_1)+y_1) dx
\end{split}
$$
$$
f(\tilde x, \tilde y) = f(x,k(x-x_1)+y_1)
$$
$$
\tilde x = x,\quad \tilde y = k(x-x_1)+y_1
$$
$$
k = \frac{y_2-y_1}{x_2-x_1}
$$
$$
\begin{split}
f_{,x} &= f_{,\tilde x} \frac{d\tilde x}{dx} + f_{,\tilde y} \frac{d\tilde y}{dx} \\
&= f_{,\tilde x} + kf_{,\tilde y}
\end{split}
$$
$$
\begin{split}
\int_{x_1}^{x_2} pf(\tilde x,\tilde y) d\Gamma &= \int_{x_1}^{x_2} (x f_{,\tilde x}+y f_{,\tilde y}) dx \\
&= \int_{x_1}^{x_2} (x f_{,\tilde x}+(k(x-x_1)+y_1) f_{,\tilde y}) dx \\
&= \int_{x_1}^{x_2} (x (f_{,\tilde x}+kf_{,\tilde y})+(y_1-kx_1)f_{,\tilde y}) dx \\
    
\end{split}
$$

# (test::Boundary integration in 2D, basis function:$(1-s)\boldsymbol x_1 + s \boldsymbol x_2$)
(data::2023-1-26)

$$
\boldsymbol x = (1-s) \boldsymbol x_1 + s \boldsymbol x_2
$$
$$
f(x,y) = f((1-s)x_1+sx_2,(1-s)y_1+sy_2)
$$
$$
\begin{split}
f_{,s} &= f_{,x} \frac{dx}{ds} + f_{,y} \frac{dy}{ds} \\
&= (x_2-x_1) f_{,x} + (y_2-y_1) f_{,y} \\
\end{split}
$$
$$
\begin{split}
\int_{\Gamma} p f d\Gamma &= L\int_0^1 pf ds \\
&= L\int_0^1 (xf_{,x}+yf_{,y}) ds \\
&= L\int_0^1 (((1-s)x_1+sx_2)f_{,x}+((1-s)y_1+sy_2)f_{,y}) ds \\
&= L\int_0^1 (s((x_2-x_1)f_{,x}+(y_2-y_1)f_{,y})+x_1f_{,x}+y_1f_{,y}) ds \\
&= L\int_0^1 (sf_{,s}+x_1f_{,x}+y_1f_{,y}) ds \\
&= Lf(x_2,y_2) - \int_{\Gamma} f d\Gamma + \int_{\Gamma} (x_1f_{,x}+y_1f_{,y}) d\Gamma \\
\end{split}
$$
$$
\int_{\Gamma} f d\Gamma = \frac{1}{p+1}(L f(x_2,y_2) + \int_{\Gamma}(x_1f_{,x}+y_1f_{,y})d\Gamma)
$$

# (test::Boundary integration in 2D, basis function:$\frac{1-\xi}{2}\boldsymbol x_1 + \frac{1+\xi}{2} \boldsymbol x_2$)
(data::2023-1-26)
$$
\boldsymbol x = \frac{1-\xi}{2} \boldsymbol x_1 + \frac{1+\xi}{2} \boldsymbol x_2
$$
$$
f(x,y) = f(\frac{1-\xi}{2}x_1+\frac{1+\xi}{2}x_2,\frac{1-\xi}{2}y_1+\frac{1+\xi}{2}y_2)
$$
$$
\begin{split}
f_{,\xi} &= f_{,x} \frac{dx}{d\xi} + f_{,y} \frac{dy}{d\xi} \\
&= \frac{x_2-x_1}{2} f_{,x} + \frac{y_2-y_1}{2} f_{,y} \\
\end{split}
$$
$$
\begin{split}
\int_{\Gamma} p f d\Gamma &= \int_{\Gamma} (xf_{,x}+yf_{,y}) d\Gamma \\
&= \int_{\Gamma} ((\frac{1-\xi}{2}x_1+\frac{1+\xi}{2}x_2)f_{,x}
+(\frac{1-\xi}{2}y_1+\frac{1+\xi}{2}y_2)f_{,y}) d\Gamma \\
&= \int_{\Gamma} (\xi(\frac{x_2-x_1}{2}f_{,x}+\frac{y_2-y_1}{2}f_{,y})
+\frac{x_1+x_2}{2}f_{,x}+\frac{y_1+y_2}{2}f_{,y}) d\Gamma \\
&= \int_{\Gamma} (\xi f_{,\xi}
+x_0f_{,x}+y_0f_{,y}) d\Gamma \\
&= \frac{L}{2}(f(\boldsymbol x_1)+f(\boldsymbol x_2)) - \int_{\Gamma} f d\Gamma + \int_{\Gamma} (x_0f_{,x}+y_0f_{,y}) d\Gamma \\
\end{split}
$$
$$
\int_{\Gamma} f d\Gamma = \frac{1}{p+1}(\frac{L}{2} (f(\boldsymbol x_1)+f(\boldsymbol x_2)) + \int_{\Gamma}(x_0f_{,x}+y_0f_{,y})d\Gamma)
$$
Furthermore $f_{,x}$ and $f_{,y}$ are $(p-1)$-homogeneous, and have the following relation
$$
\begin{split}
\int_{\Gamma} (p-1)f_{,i} d\Gamma &= \int_{\Gamma} (xf_{,ix}+yf_{,iy}) d\Gamma \\
&= \frac{L}{2}(f_{,i}(\boldsymbol x_1)+f_{,i}(\boldsymbol x_2)) - \int_{\Gamma} f_{,i} d\Gamma + \int_{\Gamma} (x_0f_{,ix}+y_0f_{,iy}) d\Gamma \\
\end{split}
$$
$$
\int_{\Gamma} f_{,i} d\Gamma = \frac{1}{p}(\frac{L}{2} (f_{,i}(\boldsymbol x_1)+f_{,i}(\boldsymbol x_2)) + \int_{\Gamma}(x_0f_{,ix}+y_0f_{,iy})d\Gamma)
$$

# (test::Triangular element)
(data::2023-1-26)

$$
\int_{\Gamma} f d\Gamma = \sum_{i=1}^3 \int_{\Gamma_i} f d\Gamma
$$

For $\boldsymbol x \in \Gamma_i$
$$
f(\boldsymbol x) = f(\frac{1-\xi}{2}\boldsymbol x_1 + \frac{1+\xi}{2}\boldsymbol x_2) = g_i(\xi)
$$
$$
g(\xi) = \sum_{j=0}^p g_{ij}(\xi)
$$
where $g_{ij}(\lambda \xi) = \lambda^j g_{ij}(\xi)$
$$
\begin{split}
\int_{\Gamma_i} j g_{ij} d\Gamma &= \int_{\Gamma_i} \xi g_{ij,\xi} d\Gamma \\
&= \frac{L_i}{2} \xi g_{ij}n_\xi \vert_{-1}^{1} - \int_{\Gamma_i} g_{ij} d\Gamma \\
&= \frac{L_i}{2} (g_{ij}(\boldsymbol x_1)+g_{ij}(\boldsymbol x_2)) - \int_{\Gamma_i} g_{ij} d\Gamma \\
\end{split}
$$
$$
\int_{\Gamma_i} g_{ij} d\Gamma = \frac{1}{j+1} \frac{L_i}{2}(g_{ij}(\boldsymbol x_1)+g_{ij}(\boldsymbol x_2))
$$
$$
\int_{\Gamma_i} f d\Gamma = \sum_{j=0}^p \int_{\Gamma_i} g_{ij} d\Gamma
$$
