---
icon: OcInfinity16
---

#Example #Elasticity/Plate/Thin-plate 

The dynamics equilibrium equation of a circular thin-plate with its radius $a$:
$$
D \nabla^4 w + \rho h \ddot w = f
$$
where D is flexural rigidity. The forcing function $f$, is assumed to be harmonic with frequency $\Theta$, is given by
$$
f(t) = F_0 e^{\iota \Theta t}
$$
$\iota$ is the imaginary unit, $\iota^2=-1$. The corresponding solution can be attained by applying Hankel transforms as
$$
w(r,t) = W(r)e^{i\Theta t}
$$
with
$$
W(r) = \frac{2}{a^2D} \sum_{i=1}^\infty\frac{J_0(\lambda_i r)\bar F(\lambda_i)}{J_1^2(\lambda_1 a)(\lambda_i^4-\lambda^4)}
$$
$$
\begin{split}
\bar F(\lambda) &= \int_0^a r F_0 J_0(\lambda r)dr \\
&= \frac{F_0}{\lambda^2} \int_0^{\frac{a}{\lambda}} (\bar r)J_0(\bar r) d\bar r \\
&= \frac{F_0}{\lambda^2} 
\left .
\bar r J_1(\bar r)
\right |_{\bar r = 0}^{\frac{a}{\lambda}} \\
&= \frac{F_0 a}{\lambda^3} J_1(\frac{a}{\lambda}) 
\end{split}
, \quad \bar r = \lambda r
$$
$$
\lambda^4 = \frac{\Theta^2 \rho h}{D}
$$
in which $J_\alpha$ is the *Bessel functions* of the first kind. With the aid of the above relationships, the $W$ can be deduced as
$$
W(r) = \frac{2F_0}{aD} \sum_{i=1}^\infty\frac{J_0(\lambda_i r)J_1(\frac{a}{\lambda_i})}{J_1^2(\lambda_1 a)(\lambda_i^4-\lambda^4)\lambda_i^3}
$$
