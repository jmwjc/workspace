---
icon: OcInfinity16
---

#Approximation/Meshfree

# Fixed form
A variable can be discrete by meshfree shape functions $\Psi_I$'s and nodal coefficients $d_I$'s as
$$
u(\boldsymbol x) = \sum_{I=1}^{n_p} \Psi_I(\boldsymbol x) d_I
$$
In accordance with **reproducing kernel approximation**, the shape functions $\Psi_I$'s is constructed by follow
$$
\Psi_I(\boldsymbol x) = \boldsymbol c^T(\boldsymbol x) \boldsymbol p(\boldsymbol x_I) \phi(\boldsymbol x_I,\boldsymbol x)
$$
where $\boldsymbol p$ is the basis function vector, $\phi$ is the kernel function to control the smoothness and locality of shape functions. $\boldsymbol c$ is the coefficient vector to be determined by following **consistency conditions**
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \boldsymbol p(\boldsymbol x_I) = \boldsymbol p(\boldsymbol x)
$$
substituting this equation into the expression of the shape function leads to
$$
\sum_{I=1}^{n_p} \boldsymbol p(\boldsymbol x_I) \boldsymbol p^T(\boldsymbol x_I)\phi(\boldsymbol x_I,\boldsymbol x) \boldsymbol c(\boldsymbol x) = \boldsymbol p(\boldsymbol x)
$$
from here, $\boldsymbol c$ can be attain by
$$
\boldsymbol c(\boldsymbol x) = \boldsymbol M^{-1}(\boldsymbol x) \boldsymbol p(\boldsymbol x)
$$
where $\boldsymbol M$ is the moment matrix expressed by
$$
\boldsymbol M(\boldsymbol x) = \sum_{I=1}^{n_p}\boldsymbol p(\boldsymbol x_I) \boldsymbol p^T(\boldsymbol x_I) \phi(\boldsymbol x_I,\boldsymbol x)
$$
Consequently, the shape functions can be evaluated by
$$
\Psi_I(\boldsymbol x) = \boldsymbol p^T(\boldsymbol x_I) \boldsymbol M^{-1}(\boldsymbol x) \boldsymbol p(\boldsymbol x) \phi(\boldsymbol x_I,\boldsymbol x)
$$

# Shifted form
This expression can be rephrased with a shift-form basis function, where the shift-form **consistency conditions** also should be introduced herein
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \boldsymbol p(\boldsymbol x_I - \boldsymbol x) = \boldsymbol p(\boldsymbol 0)
$$
According to this consistency conditions, the assumed expression of shape functions is given by
$$
\Psi_I(\boldsymbol x) = \boldsymbol c^T(\boldsymbol x_I,\boldsymbol x) \boldsymbol p(\boldsymbol x_I-\boldsymbol x) \phi(\boldsymbol x_I-\boldsymbol x)
$$
under this circumstances, the coefficient vector $\boldsymbol c$ can be rephrased as
$$
\boldsymbol c(\boldsymbol x_I,\boldsymbol x) = \boldsymbol M^{-1}(\boldsymbol x)\boldsymbol p(\boldsymbol x_I-\boldsymbol x)
$$
where the moment matrix $\boldsymbol M$ has the following form
$$
\boldsymbol M(\boldsymbol x) = \sum_{I=1}^{n_p} \boldsymbol p(\boldsymbol x_I-\boldsymbol x) \boldsymbol p^T(\boldsymbol x_I-\boldsymbol x) \phi(\boldsymbol x_I-\boldsymbol x)
$$
and the shape functions with the shifted form is attained to
$$
\Psi_I(\boldsymbol x) = \boldsymbol p^T(\boldsymbol 0) \boldsymbol M^{-1}(\boldsymbol x)\boldsymbol p(\boldsymbol x_I-\boldsymbol x) \phi(\boldsymbol x_I-\boldsymbol x)
$$
# Wave-based shape functions
As for the basis vector $\boldsymbol p(\boldsymbol x)$,to precisely capture the Helmholtz solutions, the following plane wave basis vector is employed
$$
\boldsymbol 𝒑(\boldsymbol𝒙) = (1, \sin(\boldsymbol 𝒌^1 ⋅ \boldsymbol 𝒙), \cos(\boldsymbol 𝒌^1 ⋅ \boldsymbol 𝒙), … ,\sin(\boldsymbol 𝒌^{n_𝜃}⋅ \boldsymbol 𝒙), \cos(\boldsymbol 𝒌^{n_𝜃} ⋅ \boldsymbol 𝒙))^𝑇 
$$
with 
$$
\boldsymbol 𝒌^𝑛 = (𝑘 \cos 𝜃_𝑛, 𝑘 \sin 𝜃_𝑛 )
$$
where $𝜃_n, n=1, …, n_𝜃 ,$and $n_𝜃$ is the total number of wave directions included in the meshfree approximation

substituting $\boldsymbol p(x)$ into the function 
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \boldsymbol p(\boldsymbol x_I) = \boldsymbol p(\boldsymbol x)
$$
$$
=\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x)\begin{Bmatrix} 1 \\ \sin(\boldsymbol 𝒌^1 ⋅ \boldsymbol 𝒙_I)\\ \cos(\boldsymbol 𝒌^1 ⋅ \boldsymbol 𝒙_I)\\...\\ \sin(\boldsymbol 𝒌^{n_𝜃}⋅ \boldsymbol 𝒙_I)\\ \cos(\boldsymbol 𝒌^{n_𝜃} ⋅ \boldsymbol 𝒙_I)\end{Bmatrix}=\begin{Bmatrix} 1 \\ \sin(\boldsymbol 𝒌^1 ⋅ \boldsymbol 𝒙)\\ \cos(\boldsymbol 𝒌^1 ⋅ \boldsymbol 𝒙)\\...\\ \sin(\boldsymbol 𝒌^{n_𝜃}⋅ \boldsymbol 𝒙)\\ \cos(\boldsymbol 𝒌^{n_𝜃} ⋅ \boldsymbol 𝒙)\end{Bmatrix}
$$
$\boldsymbol 𝒑(\boldsymbol𝒙)$ can be rephrased with a shift-form basis function
$$
\boldsymbol 𝒑(\boldsymbol x_I - \boldsymbol x) = (1, \sin(\boldsymbol 𝒌^1 ⋅ (\boldsymbol x_I - \boldsymbol x)), \cos(\boldsymbol 𝒌^1 ⋅ (\boldsymbol x_I - \boldsymbol x)), … ,\sin(\boldsymbol 𝒌^{n_𝜃}⋅ (\boldsymbol x_I - \boldsymbol x)), \cos(\boldsymbol 𝒌^{n_𝜃}⋅ (\boldsymbol x_I - \boldsymbol x)))^𝑇 
$$
substituting $\boldsymbol 𝒑(\boldsymbol x_I - \boldsymbol x)$ into the function 
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \boldsymbol p(\boldsymbol x_I-\boldsymbol x)
$$
$$
=\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x)\begin{Bmatrix} 1 \\ \sin(\boldsymbol 𝒌^1 ⋅ (\boldsymbol 𝒙-\boldsymbol 𝒙_I))\\ \cos(\boldsymbol 𝒌^1 ⋅ (\boldsymbol 𝒙-\boldsymbol 𝒙_I))\\...\\ \sin(\boldsymbol 𝒌^{n_𝜃}⋅ (\boldsymbol 𝒙-\boldsymbol 𝒙_I))\\ \cos(\boldsymbol 𝒌^{n_𝜃}⋅ (\boldsymbol 𝒙-\boldsymbol 𝒙_I))\end{Bmatrix}
$$

and the terms in the function  can be rephrased as
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \sin(\boldsymbol 𝒌^n⋅ (\boldsymbol x_I - \boldsymbol x))
$$
$$=\sin(\boldsymbol 𝒌^n⋅ \boldsymbol x)\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \cos(\boldsymbol 𝒌^n⋅ \boldsymbol x_I)-\cos(\boldsymbol 𝒌^n⋅ \boldsymbol x)\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \sin(\boldsymbol 𝒌^n⋅ \boldsymbol x_I)
$$
$$
=\sin(\boldsymbol 𝒌^n⋅ \boldsymbol x)\cos(\boldsymbol 𝒌^n⋅ \boldsymbol x)-\cos(\boldsymbol 𝒌^n⋅ \boldsymbol x)\sin(\boldsymbol 𝒌^n⋅ \boldsymbol x)=0
$$
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \cos(\boldsymbol 𝒌^n⋅ (\boldsymbol x_I - \boldsymbol x))
$$
$$=\cos(\boldsymbol 𝒌^n⋅ \boldsymbol x)\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \cos(\boldsymbol 𝒌^n⋅ \boldsymbol x_I)+\sin(\boldsymbol 𝒌^n⋅ \boldsymbol x)\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \sin(\boldsymbol 𝒌^n⋅ \boldsymbol x_I)
$$
$$
=\cos(\boldsymbol 𝒌^n⋅ \boldsymbol x)\cos(\boldsymbol 𝒌^n⋅ \boldsymbol x)+\sin(\boldsymbol 𝒌^n⋅ \boldsymbol x)\sin(\boldsymbol 𝒌^n⋅ \boldsymbol x)=1
$$
Consequently, two function are equivalent
$$
\sum_{I=1}^{n_p}\Psi_I(\boldsymbol x) \boldsymbol p(\boldsymbol x_I-\boldsymbol x)=\begin{Bmatrix} 1 \\0\\1\\...\\0\\ 1\end{Bmatrix}=\boldsymbol p(\boldsymbol 0)
$$


