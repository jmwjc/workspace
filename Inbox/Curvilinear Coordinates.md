---
icon: OcInfinity16
---

#Math/Tensor #Elasticity/Shell
# Dual and Irregular bases
In the Cartesian system, the position can be expressed by Cartesian coordinates $(x_1,x_2,x_3)$ or other parametric coordinates $(\xi^1,\xi^2,\xi^3)$ :
$$
\begin{equation}
\begin{split}
\boldsymbol{x} &= x_1 \boldsymbol{e}_1 + x_2 \boldsymbol{e}_2 + x_3 \boldsymbol{e}_3 \\ &=
\xi^1 \boldsymbol{g}_1 + \xi^2 \boldsymbol{g}_2 + \xi^3 \boldsymbol{g}_3 
\end{split}
\end{equation}
$$
Similarly, a variable $u$ can be depicted by  Cartesian coordinates:
$$
\begin{equation}
u = d_1 \boldsymbol{e}_1 + d_2 \boldsymbol{e}_2 + d_3 \boldsymbol{e}_3
\end{equation}
$$
where $d_i$ is the constant coefficient, $\boldsymbol{e}_i$ is **orthogonal** basis vector, and has the following properties:
$$
\begin{equation}
\boldsymbol{e}_1 = \begin{Bmatrix}
1 \\ 0 \\ 0
\end{Bmatrix}, \quad
\boldsymbol{e}_2 = \begin{Bmatrix}
0 \\ 1 \\ 0
\end{Bmatrix}, \quad
\boldsymbol{e}_3 = \begin{Bmatrix}
0 \\ 0 \\ 1
\end{Bmatrix}, \quad
\end{equation}
$$
$$
\begin{equation}
\boldsymbol{e}_1 \cdot (\boldsymbol{e}_2 \times \boldsymbol{e}_3) = 1
\end{equation}
$$
$$
\begin{equation}
\boldsymbol{e}_i \cdot \boldsymbol{e}_j = \delta_{ij}
\end{equation}
$$
where $\delta_{ij}$ is Kronecker operator defined by:
$$
\begin{equation}
\delta_{ij} = \left \{
\begin{array}{l}
1,\quad i = j \\
0,\quad i \neq j
\end{array} \right.
\end{equation}
$$
For an irregular domain, a non-orthogonal basis vector is facilitated for deformation, yields:
$$
\begin{equation}
u = u^1 \boldsymbol{g}_1 + u^2 \boldsymbol{g}_2 + u^3 \boldsymbol{g}_3 = u_1 \boldsymbol{g}^1 + u_2 \boldsymbol{g}^2 + u_3 \boldsymbol{g}^3 
\end{equation}
$$
where $\boldsymbol{g}_i$ is the covariant basis vector, and $u^i$ is the corresponding coefficient. On the contrary, $\boldsymbol{g}^i$ and $u_i$ are the contravariant basis vector and coefficient, and the covariant and contravariant coordinates are defined by:
$$
\begin{equation}
\boldsymbol{g}_i = \frac{\partial \boldsymbol{x}}{\partial \xi^i}, \quad
\boldsymbol{g}^i = \frac{\partial \xi^i}{\partial \boldsymbol{x}}
\end{equation}
$$
$$
\begin{equation}
\boldsymbol{g}^1 = \frac{1}{J}\boldsymbol{g}_2 \times  \boldsymbol{g}_3, \quad
\boldsymbol{g}^2 = \frac{1}{J}\boldsymbol{g}_3 \times  \boldsymbol{g}_1, \quad
\boldsymbol{g}^3 = \frac{1}{J}\boldsymbol{g}_1 \times  \boldsymbol{g}_2
\end{equation}
$$
where
$$
\begin{equation}
J = \boldsymbol{g}_1 \cdot (\boldsymbol{g}_2 \times \boldsymbol{g}_3)
\end{equation}
$$
For the definition of the covariant and contravariant coordinates, the orthogonality exists between covariant and contravariant coordinates as:
$$
\begin{equation}
\boldsymbol{g}_i \cdot \boldsymbol{g}^j = \delta_i^j = \left \{
\begin{array}{l}
1,\quad i = j \\
0,\quad i \neq j
\end{array} \right.
\end{equation}
$$
and the *covariant metric coefficients* are defined by:
$$
\begin{equation}
g_{ij} = \boldsymbol{g}_i \cdot \boldsymbol{g}_j
\end{equation}
$$

^07e009

the *contravariant metric coefficients* are that:
$$
\begin{equation}
g^{ij} = \boldsymbol{g}^i \cdot \boldsymbol{g}^j
\end{equation}
$$
and the following relationship holds true:
$$
\begin{equation}
[g_{ij}] = [g^{ij}]^{-1}
\end{equation}
$$
The transformation between $\boldsymbol{g}_{i}$ and $\boldsymbol{g}^{j}$ is carried out by metric coefficients as:
$$
\boldsymbol{g}_{i} = g_{ij} \boldsymbol{g}^{j}
$$
Along the same path, the contravariant basis can be solved by:
$$
\boldsymbol{g}^{i} = g^{ij} \boldsymbol{g}_{j}
$$
$$
g^{ik}g_{kj} = g^{ki}g_{kj} = g^{ik}g_{jk} = g^{ki}g_{jk} = \delta_{j}^{i}
$$
# Derivatives
**Gradient of covariant and contravariant basis**
We introduce the $\boldsymbol{\Gamma}_{ij}$, $\Gamma_{ij}^{k}$ namely the first and second kind of the ***Christoffel Symbols*** evaluated by:
$$
\boldsymbol{\Gamma}_{ij} = \frac{\partial^{2} \boldsymbol{x}}{\partial \xi^{i} \partial \xi^{j}} = \frac{\partial \boldsymbol{g}_i}{\partial \xi^j} = \frac{\partial \boldsymbol{g}_j}{\partial \xi^i}
$$
$$
\Gamma_{ij}^{k} = \boldsymbol{g}^{k} \cdot \boldsymbol{\Gamma}_{ij}, \quad 
\boldsymbol{\Gamma}_{ij} = \Gamma_{ij}^{k} \boldsymbol{g}_{k}
$$

^05802b

**Gradient of scale**
The gradient(nabla) operator in curvilinear coordinates is defined as:
$$
\begin{equation}
\nabla = \frac{\partial}{\partial \boldsymbol{x}} = 
\frac{\partial}{\partial x_i} \boldsymbol{e}_i = \frac{\partial}{\partial \xi^i} \boldsymbol{g}^i
\end{equation}
$$
**Gradient of first order tensor**
$$
\begin{split}
\nabla \boldsymbol{u} &= \frac{\partial \boldsymbol{u}}{\partial \xi^{i}} \boldsymbol{g}^{i}
= \frac{\partial(u^{j} \boldsymbol{g}_{j})}{\partial \xi^{i}} \boldsymbol{g}^{i} \\
&= \frac{\partial u^{j}}{\partial \xi^{i}} \boldsymbol{g}^{i} \otimes \boldsymbol{g}_{j} + 
\frac{\partial \boldsymbol{g}_{j}}{\partial \xi^{i}} u^{j} \boldsymbol{g}^{i}
\end{split}
$$

  
such that
$$
\nabla \boldsymbol{u} = (\frac{\partial u^{j}}{\partial \xi^{i}} + \Gamma_{ik}^{j} u^{k})
\boldsymbol{g}^{i} \otimes \boldsymbol{g}_{j} = u^{j}|_{i} \boldsymbol{g}^{i} \otimes \boldsymbol{g}_{j}
$$
On the contrary,
$$
\begin{split}
\nabla \boldsymbol{u} &= \frac{\partial \boldsymbol{u}}{\partial \xi^{i}} \boldsymbol{g}^{i}
= \frac{\partial(u_{j} \boldsymbol{g}^{j})}{\partial \xi^{i}} \boldsymbol{g}^{i} \\
&= \frac{\partial u_{j}}{\partial \xi^{i}} \boldsymbol{g}^{i} \otimes \boldsymbol{g}^{j} + 
\frac{\partial \boldsymbol{g}^{j}}{\partial \xi^{i}} u_{j} \boldsymbol{g}^{i} \\
\end{split}
$$
due to the following relationship hold true:
$$
\frac{\partial (\boldsymbol{g}^{k} \cdot \boldsymbol{g}_{j})}{\partial \xi^{i}}
= \frac{\partial \boldsymbol{g}^{k}}{\partial \xi^{i}} \cdot \boldsymbol{g}_{j} + \boldsymbol{g}^{k} \cdot \frac{\partial \boldsymbol{g}_{j}}{\partial \xi^{i}} = 0
$$
  
$$
P_{ij}^{k} = \frac{\partial \boldsymbol{g}^{k}}{\partial \xi^{i}} \cdot \boldsymbol{g}_{j} = - \boldsymbol{g}^{k} \cdot
\frac{\partial \boldsymbol{g}_{j}}{\partial \xi^{i}} = - \Gamma_{ij}^{k}
$$
  
such that
$$
\begin{split}
\nabla \boldsymbol{u} &= (\frac{\partial u_{j}}{\partial \xi^{i}} + P_{ij}^{k} u_{k})
\boldsymbol{g}^{i} \otimes \boldsymbol{g}^{j}\\
&= (\frac{\partial u_{j}}{\partial \xi^{i}} - \Gamma_{ij}^{k} u_{k})
\boldsymbol{g}^{i} \otimes \boldsymbol{g}^{j} \\
&= u_{j}|_{i} \boldsymbol{g}^{i} \otimes \boldsymbol{g}^{j} 
\end{split}
$$
For a second order tensor $\boldsymbol A$, the gradient is evaluated by
$$
\begin{split}
\nabla \cdot \boldsymbol A &= \frac{\partial \boldsymbol A}{\partial \xi^j} \cdot \boldsymbol g^j \\
&= \frac{\partial (A^{ik}\boldsymbol g_i \boldsymbol g_k)}{\partial \xi^j} \cdot \boldsymbol g^j \\
&= (A^{ik}_{,j}\boldsymbol g_i \boldsymbol g_k + A^{ik}\boldsymbol g_{i,j} \boldsymbol g_k + A^{ik}\boldsymbol g_i \boldsymbol g_{k,j}) \cdot \boldsymbol g^j \\
&= A^{ij}_{,j}\boldsymbol g_i + A^{ij}\Gamma_{ij}^k\boldsymbol g_k + A^{ik}\Gamma_{kj}^j\boldsymbol g_i \\
&= (A^{ij}_{,j} + A^{kj}\Gamma_{kj}^i + A^{ik}\Gamma_{kj}^j)\boldsymbol g_i
\end{split}
$$
$$
\begin{split}
\nabla \cdot \boldsymbol A &= \frac{\partial \boldsymbol A}{\partial \xi^i} \cdot \boldsymbol g^i \\
&= \frac{\partial (\boldsymbol A \cdot \boldsymbol g^i)}{\partial \xi^i} - \boldsymbol A \cdot \boldsymbol g_{,i}^i \\
&= (\boldsymbol A \cdot \boldsymbol g^i)_{,\xi^i} - \boldsymbol g_i A^{ij} \boldsymbol g_j \cdot \boldsymbol g_{,k}^k \\
&= (\boldsymbol A \cdot \boldsymbol g^i)_{,\xi^i} + \boldsymbol g_i A^{ij} \boldsymbol g_{j,k} \cdot \boldsymbol g^k
\end{split}
$$
The **Gauss-Ostrogradsky theorem** can be recast as:
$$
\begin{split}
\int_\Omega \nabla v \cdot \boldsymbol u d\Omega &= \int_\Omega v_{,i} u^i d\Omega = \int_\Omega v_{,i}\boldsymbol a^i \cdot \boldsymbol a_j u^j d\Omega \\
&= \int_\Gamma v u^i n_i d\Gamma - \int_\Omega v (\boldsymbol a_j u^j)_{,i} \cdot \boldsymbol a^i d\Omega \\
&= \int_\Gamma v u^i n_i d\Gamma - \int_\Omega v (u^j_{,i} \boldsymbol a_j + \Gamma_{ij}^k u^j \boldsymbol a_k) \cdot \boldsymbol a^i d\Omega \\
&= \int_\Gamma v u^i n_i d\Gamma - \int_\Omega v (u^i_{,i} + \Gamma_{ij}^i u^j) d\Omega \\
&= \int_\Gamma v u^i n_i d\Gamma - \int_\Omega v u^i\vert_i d\Omega \\
&= \int_\Gamma v \boldsymbol u \cdot \boldsymbol n d\Gamma - \int_\Omega v \nabla \cdot \boldsymbol u d\Omega \\
\end{split}
$$

# Geometric parameters of cylinder shell
$$
\boldsymbol x = 
\begin{Bmatrix}
    (r+\xi^3)\sin \frac{\xi^1}{r} \\ \xi^2 \\ (r+\xi^3)\cos \frac{\xi^1}{r}
\end{Bmatrix} =
\begin{Bmatrix}
    r\sin\frac{\xi^1}{r} \\ \xi^2 \\ r\cos \frac{\xi^1}{r}
\end{Bmatrix} + \xi^3
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \\ 0 \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
\boldsymbol r =
\begin{Bmatrix}
    r\sin\frac{\xi^1}{r} \\ \xi^2 \\ r\cos \frac{\xi^1}{r}
\end{Bmatrix},\quad \boldsymbol a_3 =
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \\ 0 \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
\boldsymbol a_1 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \\ 0 \\ -\sin\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol a_2 =
\begin{Bmatrix}
    0 \\ 1 \\ 0
\end{Bmatrix},\quad
\boldsymbol a_3 =
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \\ 0 \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
\boldsymbol a^1 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \\ 0 \\ -\sin\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol a^2 =
\begin{Bmatrix}
    0 \\ 1 \\ 0
\end{Bmatrix},\quad
\boldsymbol a^3 =
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \\ 0 \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
a^{11} = a^{22} = a^{33} = 1, a^{12} = a^{13} = a^{23} = 0
$$
$$
J = 1
$$
$$
\boldsymbol \Gamma_{11} =
\begin{Bmatrix}
    - \frac{1}{r} \sin\frac{\xi^1}{r} \\ 0 \\ -\frac{1}{r}\cos\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol \Gamma_{22} =
\begin{Bmatrix}
    0 \\ 0 \\ 0
\end{Bmatrix},\quad
\boldsymbol \Gamma_{12} =
\begin{Bmatrix}
    0 \\ 0 \\ 0
\end{Bmatrix}
$$
$$
\boldsymbol \Gamma_{13} =
\begin{Bmatrix}
    \frac{1}{r} \cos\frac{\xi^1}{r} \\ 0 \\ -\frac{1}{r}\sin\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol \Gamma_{23} =
\begin{Bmatrix}
    0 \\ 0 \\ 0
\end{Bmatrix}
$$
$$
\Gamma_{11}^1 = \Gamma_{11}^2 = \Gamma_{\alpha 2}^i(b_{\alpha 2}) = 0, \; \Gamma_{11}^3(b_{11}) = -\frac{1}{r},\; \Gamma_{31}^1(-b_1^1) = \frac{1}{r}
$$

# Geometric parameters of spherical shell (case 1)
$$
\boldsymbol x =
\begin{Bmatrix}
    (r+\xi^3)\sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ (r+\xi^3)\sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ (r+\xi^3)\cos\frac{\xi^1}{r}
\end{Bmatrix} = r
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix} + \xi^3
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
\boldsymbol r = r
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix},\quad \boldsymbol a_3 =
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
\boldsymbol a_1 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ -\sin\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol a_2 =
\begin{Bmatrix}
    -\sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol a_3 =
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
$$
J = \boldsymbol a_1 \cdot (\boldsymbol a_2 \times \boldsymbol a_3) = \sin \frac{\xi^1}{r}
$$
$$
\boldsymbol a^1 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r}\cos\frac{\xi^2}{r} \\ -\cos\frac{\xi^1}{r}\sin\frac{\xi^2}{r} \\ -\sin\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol a^2 =
\begin{Bmatrix}
    -\csc \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \csc \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol a^3 =
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix}
$$
where $\csc x = \frac{1}{\sin x}$
$$
a^{11} = a^{33} = 1,\; a^{22} = \csc^2 \frac{\xi^1}{r},\;a^{12} = a^{13} = a^{23} = 0
$$
$$
\boldsymbol \Gamma_{11} = -\frac{1}{r}
\begin{Bmatrix}
    \sin\frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol \Gamma_{22} = -\frac{1}{r}
\begin{Bmatrix}
    \sin \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol \Gamma_{12} = \frac{1}{r}
\begin{Bmatrix}
    - \cos \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \cos \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ 0
\end{Bmatrix}
$$
$$
\boldsymbol \Gamma_{13} = \frac{1}{r}
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \cos \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ -\sin\frac{\xi^1}{r}
\end{Bmatrix},\quad
\boldsymbol \Gamma_{23} = \frac{1}{r}
\begin{Bmatrix}
    - \sin \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ 0
\end{Bmatrix}
$$
$$
\Gamma_{11}^1 = \Gamma_{11}^2 = \Gamma_{22}^2 = \Gamma_{12}^1 = 0, \; \Gamma_{22}^1 = - \frac{1}{r} \sin \frac{2\xi^1}{r},\; \Gamma_{12}^2 = \frac{1}{r} \cot \frac{\xi^1}{r}
$$

# Geometric parameters of spherical shell (case 2)
$$
\boldsymbol x =
\begin{Bmatrix}
    (r+\xi^3)\cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ (r+\xi^3)\sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ (r+\xi^3)\sin\frac{\xi^2}{r}
\end{Bmatrix} = r
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^2}{r}
\end{Bmatrix} + \xi^3
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^2}{r}
\end{Bmatrix}
$$
$$
\boldsymbol r = r
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^2}{r}
\end{Bmatrix},\quad \boldsymbol a_3 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^2}{r}
\end{Bmatrix}
$$
$$
\boldsymbol a_1 =
\begin{Bmatrix}
    -\sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol a_2 =
\begin{Bmatrix}
    -\cos\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ -\sin\frac{\xi^1}{r} \sin\frac{\xi^2}{r} \\ \cos\frac{\xi^2}{r}
\end{Bmatrix},\quad
\boldsymbol a_3 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^1}{r} \cos\frac{\xi^2}{r} \\ \sin\frac{\xi^2}{r}
\end{Bmatrix}
$$
$$
J = \boldsymbol a_1 \cdot (\boldsymbol a_2 \times \boldsymbol a_3) = \cos \frac{\xi^2}{r}
$$
$$
\boldsymbol a^1 =
\begin{Bmatrix}
    -\sin\frac{\xi^1}{r}\sec\frac{\xi^2}{r} \\ \cos\frac{\xi^1}{r}\sec\frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol a^2 =
\begin{Bmatrix}
    -\cos \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ -\sin \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \cos \frac{\xi^2}{r}
\end{Bmatrix},\quad
\boldsymbol a^3 =
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin\frac{\xi^2}{r}
\end{Bmatrix}
$$
where $\sec x = \frac{1}{\cos x}$
$$
a^{11} = \sec^2 \frac{\xi^2}{r} ,\; a^{22} = a^{33} = 1,\;a^{12} = a^{13} = a^{23} = 0
$$
$$
\boldsymbol \Gamma_{11} = -\frac{1}{r}
\begin{Bmatrix}
    \cos\frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol \Gamma_{22} = -\frac{1}{r}
\begin{Bmatrix}
    \cos \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \sin \frac{\xi^2}{r}
\end{Bmatrix},\quad
\boldsymbol \Gamma_{12} = \frac{1}{r}
\begin{Bmatrix}
    \sin \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ -\cos \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ 0
\end{Bmatrix}
$$
$$
\boldsymbol \Gamma_{13} = \frac{1}{r}
\begin{Bmatrix}
    -\sin\frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ \cos \frac{\xi^1}{r} \cos \frac{\xi^2}{r} \\ 0
\end{Bmatrix},\quad
\boldsymbol \Gamma_{23} = \frac{1}{r}
\begin{Bmatrix}
    - \cos \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ -\sin \frac{\xi^1}{r} \sin \frac{\xi^2}{r} \\ \cos \frac{\xi^2}{r}
\end{Bmatrix}
$$
$$
\Gamma_{11}^1 = \Gamma_{22}^1 = \Gamma_{22}^2 = \Gamma_{12}^2 = 0, \; \Gamma_{11}^2 = \frac{1}{2r} \sin \frac{2\xi^2}{r},\; \Gamma_{12}^1 = - \frac{1}{r} \tan \frac{\xi^2}{r}
$$
