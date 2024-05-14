---
icon: OcInfinity16
---

#Approximation/Meshfree  #Approximation/Hermite

In meshfree approximation, a variable $u$ can be approximated by:
$$
u^h(\boldsymbol{x}) = \sum_{I=1}^{n_p} \Psi_I(\boldsymbol{x}) d_I
$$
where $\Psi_I$ and $d_I$ are the shape function and coefficients at node $\boldsymbol{x}_I$. The shape function is constructed to meet the consistency conditions:
$$
\sum_{I=1}^{n_p} \Psi_I(\boldsymbol{x}) \boldsymbol{p}(\boldsymbol{x}_I) = \boldsymbol{p}(\boldsymbol{x})
$$
or
$$
\sum_{I=1}^{n_p} \Psi_I(\boldsymbol{x}) \boldsymbol{p}(\boldsymbol{x}_I-\boldsymbol{x}) = \boldsymbol{p}(\boldsymbol{0})
$$
where $\boldsymbol p$ is the polynomial basis function
$$
\boldsymbol p(\boldsymbol x) = \{1,x,y,x^2,xy,y^2,\dots \}^T
$$
Assuming the shape function has the following reproducing kernel form
$$
\Psi_I(\boldsymbol{x}) = \boldsymbol{p}^T(\boldsymbol{x}_{I} - \boldsymbol{x}) \boldsymbol{c}(\boldsymbol{x}) \phi(\boldsymbol{x}_{I} - \boldsymbol{x})
$$
where $\phi$ is kernel function and $c$ is coefficient vector determined by consistency condition
$$
\boldsymbol c(\boldsymbol x) = \boldsymbol A^{-1}\boldsymbol p(\boldsymbol 0)
$$
$$
\boldsymbol A(\boldsymbol x_I-\boldsymbol x) = \sum_{I=1}^{n_p} \boldsymbol p(\boldsymbol x_I-\boldsymbol x)\boldsymbol p^T(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol{x}_{I} - \boldsymbol{x})
$$
Consequently, the reproducing kernel shape function has the following form
$$
\Psi_I(\boldsymbol x) = \boldsymbol p^T(\boldsymbol 0)\boldsymbol A^{-1}(\boldsymbol x_I-\boldsymbol x)\boldsymbol p(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol x_I-\boldsymbol x)
$$

# Hermite reproducing kernel approximation
For Hermite-type reproducing kernel approximation, the variable $u$ can be approximated by
$$
u^h(\boldsymbol x) = \sum_{I=1}^{n_p} (\Psi_I d_I + \Psi_{xI} d_{xI} + \Psi_{yI}d_{yI})
$$
the corresponding Hermite-type consistency condition is given by
$$
\sum_{I=1}^{n_p} (\Psi_I(\boldsymbol{x}) \boldsymbol{p}(\boldsymbol{x}_I)+\Psi_{xI}(\boldsymbol{x}) \boldsymbol{p}_{,x}(\boldsymbol{x}_I)+\Psi_{yI}(\boldsymbol{x}) \boldsymbol{p}_{,y}(\boldsymbol{x}_I)) = \boldsymbol{p}(\boldsymbol{x})
$$
$$
\sum_{I=1}^{n_p} (\Psi_I(\boldsymbol{x}) \boldsymbol{p}(\boldsymbol{x}_I-\boldsymbol x)+\Psi_{xI}(\boldsymbol{x}) \boldsymbol{p}_{,x}(\boldsymbol{x}_I-\boldsymbol x)+\Psi_{yI}(\boldsymbol{x}) \boldsymbol{p}_{,y}(\boldsymbol{x}_I-\boldsymbol x)) = \boldsymbol{p}(\boldsymbol{0})
$$
the shape functions are assumed by the reproducing kernel form
$$
\left \{
\begin{split}
\Psi_I(\boldsymbol x) &= \boldsymbol{p}^T(\boldsymbol{x}_{I} - \boldsymbol{x}) \boldsymbol{c}(\boldsymbol{x}) \phi(\boldsymbol{x}_{I} - \boldsymbol{x}) \\
\Psi_{xI}(\boldsymbol x) &= \boldsymbol{p}^T_{,x}(\boldsymbol{x}_{I} - \boldsymbol{x}) \boldsymbol{c}(\boldsymbol{x}) \phi(\boldsymbol{x}_{I} - \boldsymbol{x}) \\
\Psi_{yI}(\boldsymbol x) &= \boldsymbol{p}^T_{,y}(\boldsymbol{x}_{I} - \boldsymbol{x}) \boldsymbol{c}(\boldsymbol{x}) \phi(\boldsymbol{x}_{I} - \boldsymbol{x})
\end{split}
\right .
$$
substituting them to consistency condition yields
$$
\boldsymbol c(\boldsymbol x) = \boldsymbol A^{-1}\boldsymbol p(\boldsymbol 0)
$$
where
$$
\begin{split}
\boldsymbol A(\boldsymbol x_I-\boldsymbol x) &= \sum_{I=1}^{n_p} \boldsymbol p(\boldsymbol x_I-\boldsymbol x)\boldsymbol p^T(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol{x}_{I} - \boldsymbol{x}) \\
&+\sum_{I=1}^{n_p} \boldsymbol p_{,x}(\boldsymbol x_I-\boldsymbol x)\boldsymbol p^T_{,x}(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol{x}_{I} - \boldsymbol{x}) \\
&+\sum_{I=1}^{n_p} \boldsymbol p_{,y}(\boldsymbol x_I-\boldsymbol x)\boldsymbol p^T_{,y}(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol{x}_{I} - \boldsymbol{x}) \\
\end{split}
$$
Finally, the expression of Hermite reproducing kernel shape functions are
$$
\left \{
\begin{split}
\Psi_I(\boldsymbol x) &= \boldsymbol p^T(\boldsymbol 0)\boldsymbol A^{-1}(\boldsymbol x_I-\boldsymbol x)\boldsymbol p(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol x_I-\boldsymbol x) \\
\Psi_{xI}(\boldsymbol x) &= \boldsymbol p^T(\boldsymbol 0)\boldsymbol A^{-1}(\boldsymbol x_I-\boldsymbol x)\boldsymbol p_{,x}(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol x_I-\boldsymbol x) \\
\Psi_{yI}(\boldsymbol x) &= \boldsymbol p^T(\boldsymbol 0)\boldsymbol A^{-1}(\boldsymbol x_I-\boldsymbol x)\boldsymbol p_{,y}(\boldsymbol x_I-\boldsymbol x)\phi(\boldsymbol x_I-\boldsymbol x) \\
\end{split}
\right .
$$

# Nodal interpolation reproducing kernel shape function
Traditional reproducing kernel shape function
$$
\Psi_I(\boldsymbol x) = \boldsymbol p^T(\boldsymbol 0) \boldsymbol A^{-1}(\boldsymbol x) \boldsymbol p(\boldsymbol x_I - \boldsymbol x) \phi(\boldsymbol x_I - \boldsymbol x)
$$
this shape function split into two functions, one has nodal interpolation property, the other is corrected function
$$
\Psi_I(\boldsymbol x) = \hat \Psi_I(\boldsymbol x) + \bar \Psi_I(\boldsymbol x)
$$
where $\hat \Psi_I$ has the Kronecker delta property
$$
\hat \Psi_I(\boldsymbol x_J) = \delta_{IJ}
$$

# (test::Another form for reproducing kernel shape function)
(data::2023-08-29)
Approximation
$$
u^h(\boldsymbol x) = \sum_{I=1}^{n_p} \Psi(\boldsymbol x_I,\boldsymbol x) d_I
$$
Consistency condition
$$
\sum_{I=1}^{n_p} \Psi(\boldsymbol x_I, \boldsymbol x) \boldsymbol p(\boldsymbol x_I) = \boldsymbol p(\boldsymbol x)
$$
$$
\sum_{I=1}^{n_p} \Psi_{,i}(\boldsymbol x_I, \boldsymbol x) \boldsymbol p(\boldsymbol x_I) = \boldsymbol p_{,i}(\boldsymbol x)
$$
Integration constraint
$$
\int_{\Omega(\boldsymbol s)} \Psi_{,i}(\boldsymbol x, \boldsymbol s) \boldsymbol q(\boldsymbol s) d\Omega = \int_{\Gamma(\boldsymbol s)} \Psi(\boldsymbol x, \boldsymbol s) \boldsymbol q(\boldsymbol s) n_i d\Gamma - \int_{\Omega(\boldsymbol x)} \Psi(\boldsymbol x, \boldsymbol s) \boldsymbol q_{,i}(\boldsymbol s) d\Omega
$$
$$
\sum_K \Psi_{,i}(\boldsymbol x, \boldsymbol x_K) \boldsymbol q(\boldsymbol x_K) w_K = \sum_L \Psi(\boldsymbol x, \boldsymbol x_L) \boldsymbol q(\boldsymbol x_L) n_i (\boldsymbol x_L) w_L - \sum_B \Psi(\boldsymbol x, \boldsymbol x_B) \boldsymbol q_{,i}(\boldsymbol x_B) w_B = \boldsymbol g_{i}(\boldsymbol x)
$$
Stiffness matrix
$$
K(\boldsymbol x_I,\boldsymbol x_J) = \int_{\Omega(\boldsymbol s)} \Psi_{,i}(\boldsymbol x_I, \boldsymbol s) \Psi_{,i}(\boldsymbol x_J, \boldsymbol s) d\Omega = \sum_K \Psi_{,i}(\boldsymbol x_I, \boldsymbol x_K) \Psi_{,i}(\boldsymbol x_J, \boldsymbol x_K) w_K
$$
To satisfied consistency condition, the shape functions can be constructed by reproducing kernel framework
$$
\Psi(\boldsymbol x_I, \boldsymbol x) = \boldsymbol p^T(\boldsymbol x_I) \boldsymbol A^{-1} \boldsymbol p(\boldsymbol x)\phi(\boldsymbol x_I - \boldsymbol x)
$$
$$
\Psi_{,i}(\boldsymbol x_I, \boldsymbol x) = \boldsymbol p_{,i}^T(\boldsymbol x_I) \boldsymbol A^{-1} \boldsymbol p(\boldsymbol x)\phi(\boldsymbol x_I - \boldsymbol x)
$$
Assuming that $w_K=1, \forall K$. Based on integration constraint, the shape functions has the following form
$$
\Psi_{,i}(\boldsymbol x, \boldsymbol x_J) = \boldsymbol g_{i}^T(\boldsymbol x) \boldsymbol G^{-1} \boldsymbol q(\boldsymbol x_J) \phi(\boldsymbol x_J-\boldsymbol x)
$$

# (test::Generalized reproducing kernel)
(data::2023-02-23)
## 1D case
Assuming that the variable $u$ is discretized by
$$
u^h = \sum_{I=1}^{n_p}(\Psi_Id_I+\Psi_{(1)I}d_{(1)I}+\Psi_{(2)I}d_{(2)I}+\dots) = \sum_{I=1}^{n_p}\sum_{i=0}^{p} \Psi_{(i)I}d_{(i)I}
$$
the derivative of $u$ can be discretized by
$$
u^{(j)h} = \sum_{I=1}^{n_p}\sum_{i=0}^{p} \Psi_{(i)I}^{(j)}d_{(i)I}
$$
where
$$
\Psi_{(i)I}^{(j)}(x) = \boldsymbol p^{(i)T}(x_I) \boldsymbol A^{-1}(x_I,x) \boldsymbol p^{(j)}(x) \phi(x_I-x)
$$
$$
\boldsymbol A(x_I,x) = \sum_{I=1}^{n_p} \sum_{k=0}^p \boldsymbol p^{(k)}(x_I) \boldsymbol p^{(k)T}(x_I) \phi(x_I-x)
$$
It is noted that 
$$u^{(j)h}\ne(u^h)^{(j)}$$
$$\Psi_{(i)I}^{(j)}(x_J)=\Psi_{(j)J}^{(i)}(x_I)$$
Assuming that
$$
u(x) = \boldsymbol a^T \boldsymbol p(x), \quad b(x) = \boldsymbol b^T \boldsymbol p(x)
$$
$$
\begin{split}
\int_{\Omega} u^h b d\Omega &= \sum_{J=1}^{n_p} \sum_{j=0}^{p} (u^{h}(x_J)b(x_J))^{(j)} \frac{A_J^{(j)}}{j!} \\
&= \sum_{j=0}^p \sum_{J=1}^{n_p} \sum_{k=0}^{j} C_j^k u^{(k)h}(x_J)b^{(j-k)}(x_J) A_J^{(j)} \\
&= \sum_{j=0}^p \sum_{I,J=1}^{n_p} \sum_{i=0}^p \sum_{k=0}^{j} C_j^k \Psi_{(i)I}^{(k)}(x_J)b^{(j-k)}(x_J) A_J^{(j)}d_{(i)I} \\
&= \boldsymbol b^T \sum_{j=0}^p \sum_{I,J=1}^{n_p} \sum_{i=0}^p \sum_{k=0}^{j} C_j^k \boldsymbol p^{(j-k)}(x_J) \boldsymbol p^{(i)T}(x_I) \boldsymbol A^{-1}(x_I,x_J) \boldsymbol p^{(k)}(x_J) \phi(x_I-x_J) A_J^{(j)}d_{(i)I} \\
&= \boldsymbol b^T \sum_{j=0}^p \sum_{I,J=1}^{n_p} \sum_{i=0}^p \sum_{k=0}^{j} C_j^k \boldsymbol p^{(j-k)}(x_J) \boldsymbol p^{(k)T}(x_J) \boldsymbol A^{-1}(x_I,x_J) \boldsymbol p^{(i)}(x_I) \phi(x_I-x_J) A_J^{(j)}d_{(i)I} \\
&= \boldsymbol b^T \sum_{I,J=1}^{n_p} \sum_{i,j=0}^p 2^j \boldsymbol p^{(j)}(x_J) \boldsymbol p^{(j)T}(x_J) \boldsymbol A^{-1}(x_I,x_J) \boldsymbol p^{(i)}(x_I) \phi(x_I-x_J) A_J^{(j)}d_{(i)I} \\
&= \boldsymbol b^T \sum_{(I,i)=(1,0)}^{(n_p,p)} (\sum_{(J,j)=(1,0)}^{(n_p,p)} 2^j A_J^{(j)} \boldsymbol p^{(j)}(x_J) \boldsymbol p^{(j)T}(x_J)\phi(x_I-x_J)) \boldsymbol A^{-1}(x_I,x_J) \boldsymbol p^{(i)}(x_I) d_{(i)I} \\
&= \sum_{(I,i)=(1,0)}^{(n_p,p)} b^{(i)}(x_I) d_{(i)I} \\
\end{split}
$$

Taylor expansion of $u$ at $x_I$
$$
\begin{split}
\Psi_{(i)I}(x) &= \Psi_{(i)I}(x_I) + (x-x_I)\Psi_{(i)I}^{(1)}(x_I) + \frac{(x-x_I)^2}{2}\Psi_{(i)I}^{(2)}(x_I) + \frac{(x-x_I)^3}{6}\Psi_{(i)I}^{(3)}(x_I) + \dots \\
&= \sum_{j=0}^{\infty}\frac{(x-x_I)^j}{j!} \Psi_{(i)I}^{(j)}(x_I)
\end{split}
$$

## 2D case
$$
u^h = \sum_{I=1}^{n_p}(\Psi_Id_I+\Psi_{xI}d_{xI}+\Psi_{yI}d_{yI}+\dots) = \sum_{I=1}^{n_p}\sum_{i+j=0}^{p} \Psi_{ijI}d_{ijI}
$$

# (test::Integration with reproducing kernel shape function)
(data::2023-02-24)
Reproducing kernel shape function with fixed form
$$
\Psi_I(x) = \boldsymbol p^T(x_I) \boldsymbol A^{-1}(x) \boldsymbol p(x) \phi(x_I-x)
$$
where
$$
\boldsymbol A(x) = \sum_{K=1}^{n_p} \boldsymbol p(x_K) \boldsymbol p^T(x_K) \phi(x_K-x)
$$
a variable constructed by polynomial $\boldsymbol p$
$$
f(x) = \boldsymbol a^T \boldsymbol p(x)
$$
one-point integration with $\Psi_I$ and $f$
$$
\begin{split}
\int_{\Omega} \Psi_I(x) f(x) d\Omega &= \sum_J A_J \Psi_I(x_J) f(x_J) \\
&= \sum_J A_J \boldsymbol p^T(x_I) \boldsymbol A^{-1}(x_J) \boldsymbol p(x_J) \phi(x_I-x_J) \boldsymbol p^T(x_J) \boldsymbol a \\
&= \boldsymbol p^T(x_I) \sum_J \boldsymbol A^{-1}(x_J) A_J \boldsymbol p(x_J) \boldsymbol p^T(x_J) \phi(x_I-x_J) \boldsymbol a \\
\end{split}
$$
the kernel function is chosen as
$$
\phi(x_K-x) =
\left \{
\begin{array}{l}
    A_K & x\in \mathrm{supp}(x_K) \\
    0 & x\notin \mathrm{supp}(x_K)
\end{array}
\right .
$$
thus
$$
\boldsymbol A(x) = \sum_{K,x\in \mathrm{supp}(x_K)} \boldsymbol p(x_K) \boldsymbol p^T(x_K) A_K
$$
$$
\begin{split}
\int_{\Omega} \Psi_I(x) f(x) d\Omega &= \sum_{J,x\in \mathrm{supp}(x_K)} A_J \Psi_I(x_J) f(x_J) \\
&= \sum_{J,x\in \mathrm{supp}(x_K)} A_J \boldsymbol p^T(x_I) \boldsymbol A^{-1}(x_J) \boldsymbol p(x_J) A_I \boldsymbol p^T(x_J) \boldsymbol a \\
&= A_I \boldsymbol p^T(x_I) \sum_{J,x\in \mathrm{supp}(x_K)} \boldsymbol A^{-1}(x_J) A_J \boldsymbol p(x_J) \boldsymbol p^T(x_J) \boldsymbol a \\
&= A_I \boldsymbol p^T(x_I) \boldsymbol a \\
&= A_I f(x_I) \\
\end{split}
$$
# (test::High order integration with reproducing kernel shape function)
(data::2023-02-24)
Reproducing kernel shape function with fixed form
$$
\Psi_I(x) = \boldsymbol p^T(x_I) \boldsymbol A^{-1}(x) \boldsymbol p(x) A_I
$$
where
$$
\boldsymbol A(x) = \sum_{K=1}^{n_p} \boldsymbol p(x_K) \boldsymbol p^T(x_K) A_K
$$
the variable discretized by shape functions
$$
v = \sum_{I} \Psi_I v_I
$$
a variable constructed by polynomial $\boldsymbol p$
$$
f(x) = \boldsymbol a^T \boldsymbol p(x)
$$
one-point high order integration with $v$ and $f$
$$
\begin{split}
\int_{\Omega} v f(x) d\Omega &= \sum_I v_I \int_{\Omega} \Psi_I f d\Omega \\
&= \sum_{IJ} v_I (A_J \Psi_I(x_J) f(x_J) + A_J^{(1)}(\Psi_I^{(1)}(x_J) f(x_J) + \Psi_I(x_J) f^{(1)}(x_J))) \\
&= \sum_{IJ} v_I 
\left (
\begin{split}
A_J\boldsymbol p^T(x_I)\boldsymbol A^{-1}(x_J)\boldsymbol p(x_J)A_I \boldsymbol p^{T}(x_J) \\
+ A_J^{(1)}\boldsymbol p^T(x_I)\boldsymbol A^{-1}(x_J)\boldsymbol p^{(1)}(x_J)A_I \boldsymbol p^{T}(x_J) \\
+ A_J^{(1)}\boldsymbol p^T(x_I)\boldsymbol A^{-1}(x_J)\boldsymbol p(x_J)A_I \boldsymbol p^{(1)T}(x_J) \\
\end{split}
\right )\boldsymbol a \\
&= \sum_I A_I v_I \boldsymbol p^T(x_I) \sum_J \boldsymbol A^{-1}(x_J)
\left (
\begin{split}
A_J\boldsymbol p(x_J) \boldsymbol p^{T}(x_J) \\
+ A_J^{(1)}\boldsymbol p^{(1)}(x_J) \boldsymbol p^{T}(x_J) \\
+ A_J^{(1)}\boldsymbol p(x_J) \boldsymbol p^{(1)T}(x_J) \\
\end{split}
\right )\boldsymbol a \\
\end{split}
$$

# (test::Integration with Hermite reproducing kernel shape function)
(data::2023-02-24)
Hermite-type reproducing kernel shape function with fixed form
$$
\Psi_{(i,k)I}(x) = \boldsymbol p^{(k)T}(x_I) \boldsymbol A^{-1}(x) \boldsymbol p(x) A_I^{(i)}
$$
where
$$
\boldsymbol A(x) = \sum_{K} (A_K \boldsymbol p(x_K) \boldsymbol p^{T}(x_K) + A_K^{(1)} (\boldsymbol p^{(1)}(x_K) \boldsymbol p^{T}(x_K) + \boldsymbol p(x_K) \boldsymbol p^{(1)T}(x_K)))
$$
the variable discretized by shape functions
$$
v = \sum_{I} \Psi_I v_I + \Psi_{(1,1)I} v_I + \Psi_{(1,0)I} v_{(1)I}
$$
a variable constructed by polynomial $\boldsymbol p$
$$
f(x) = \boldsymbol a^T \boldsymbol p(x)
$$
one-point high order integration with $v$ and $f$
$$
\int_{\Omega} v f(x) d\Omega = \sum_I (v_I \int_{\Omega} (\Psi_I+\Psi_{(1,1)I}) f d\Omega + v_{(1)I}\int_{\Omega}\Psi_{(1,0)I}fd\Omega)
$$
$$
\begin{split}
\int_{\Omega} (\Psi_I+\Psi_{(1,1)I}) f d\Omega &= \sum_J
\left (
\begin{split}
 A_J(\Psi_I(x_J)+\Psi_{(1,1)I}(x_J))f(x_J) \\
+A_J^{(1)}(\Psi_I^{(1)}(x_J)+\Psi_{(1,1)I}^{(1)}(x_J))f(x_J) \\
+A_J^{(1)}(\Psi_I(x_J)+\Psi_{(1,1)I}(x_J))f^{(1)}(x_J) \\
\end{split}
\right ) \\
&= (A_I \boldsymbol p^T(x_I) + A_I^{(1)} \boldsymbol p^{(1)T}(x_I))\sum_J \boldsymbol A^{-1}(x_J)
\left (
\begin{split}
 A_J\boldsymbol p(x_J)\boldsymbol p^T(x_J) \\
+A_J^{(1)}\boldsymbol p^{(1)}(x_J)\boldsymbol p^T(x_J) \\
+A_J^{(1)}\boldsymbol p(x_J)\boldsymbol p^{(1)T}(x_J) \\
\end{split}
\right )\boldsymbol a \\
&= A_I f(x_I) + A_I^{(1)} f^{(1)}(x_I)
\end{split}
$$
$$
\int_{\Omega}\Psi_{(1,0)I}fd\Omega = A_I^{(1)}f(x_I)
$$

# (test::Smoothed gradient of reproducing kernel shape function)
(data::2023-02-25)
$$
\int_{\Omega} \Psi_{I,i} f d\Omega = \int_{\Gamma} v f n_i d\Gamma - \int_{\Omega} v f_{,i} d\Omega
$$
