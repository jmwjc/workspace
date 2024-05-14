---
icon: OcInfinity16
---

#Elasticity  #Example 

Displacement

$$
\left \{
\begin{align}
    x &= r \cos \theta \\
    y &= r \sin \theta \\
\end{align}
\right .
$$
$$
\frac{\partial r}{\partial x} = \frac{x}{r} = \cos \theta, \quad
\frac{\partial r}{\partial y} = \frac{y}{r} = \sin \theta, \quad
\frac{\partial \theta}{\partial x} = - \frac{\sin \theta}{r}, \quad
\frac{\partial \theta}{\partial y} =   \frac{\cos \theta}{r}
$$
$$
\left \{
\begin{split}
u(r,\theta) &= \frac{Ta}{8\mu}(\frac{r}{a}(\kappa+1)\cos\theta + \frac{2a}{r}((1+\kappa)\cos\theta + \cos3\theta) - \frac{2a^{3}}{r^{3}}\cos3\theta) \\
v(r,\theta) &= \frac{Ta}{8\mu}(\frac{r}{a}(\kappa-3)\sin\theta + \frac{2a}{r}((1-\kappa)\sin\theta + \sin3\theta) - \frac{2a^{3}}{r^{3}}\sin3\theta)
\end{split}
\right .
$$
$$
\kappa = \frac{3-\nu}{1+\nu}, \quad \mu = \frac{E}{2(1+\nu)}
$$
$$
\left \{
\begin{split}
u(r,\theta) &= \frac{Ta(1+\nu)}{2E}(\frac{r}{a}\frac{2}{1+\nu}\cos\theta + \frac{a}{r}(\frac{4}{1+\nu}\cos\theta + \cos3\theta) - \frac{a^{3}}{r^{3}}\cos3\theta) \\
v(r,\theta) &= \frac{Ta(1+\nu)}{2E}(-\frac{r}{a}\frac{2\nu}{1+\nu}\sin\theta - \frac{a}{r}(2\frac{1-\nu}{1+\nu}\sin\theta - \sin3\theta) - \frac{a^{3}}{r^{3}}\sin3\theta)
\end{split}
\right .
$$
$$
\left \{
\begin{split}
    u_{,x} &= \frac{T}{E}(1+\frac{a^2}{2r^2}((\nu-3)\cos 2 \theta - 2(1+\nu)\cos 4 \theta) + \frac{3a^4}{2r^4}(1+\nu)\cos 4 \theta) \\
    u_{,y} &= \frac{T}{E}(-\frac{a^2}{r^2}(\frac{1}{2}(\nu+5)\sin 2 \theta + (1+\nu)\sin 4 \theta) + \frac{3a^4}{2r^4}(1+\nu)\sin 4 \theta) \\
    v_{,x} &= \frac{T}{E}(-\frac{a^2}{r^2}(\frac{1}{2}(\nu-3)\sin 2 \theta + (1+\nu)\sin 4 \theta) + \frac{3a^4}{2r^4}(1+\nu)\sin 4 \theta) \\
    v_{,y} &= \frac{T}{E}(-\nu-\frac{a^2}{2r^2}((1-3\nu)\cos 2 \theta - 2(1+\nu)\cos 4 \theta) - \frac{3a^4}{2r^4}(1+\nu)\cos 4 \theta)
\end{split}
\right .
$$
Stress
$$
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{12}
\end{Bmatrix} =
\begin{Bmatrix}
T-T \frac{a^2}{r^2}(\frac{3}{2}\cos 2 \theta + \cos 4 \theta) + T \frac{3a^4}{2r^4} \cos 4 \theta \\
-T \frac{a^2}{r^2} (\frac{1}{2} \cos 2 \theta - \cos 4 \theta) - T \frac{3a^4}{2r^4} \cos 4 \theta \\
-T \frac{a^2}{r^2}  (\frac{1}{2} \sin 2 \theta + \sin 4 \theta) + T \frac{3a^4}{2r^4} \sin 4 \theta
\end{Bmatrix}
$$
