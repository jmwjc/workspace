---
icon: OcInfinity16
---

#NonlinearElasticity/Plasticity 

![[Return mapping algorithm]]]
![[Mohr's circle]]
# Yield function 1
![[❅ mohr-coulomb.excalidraw]]
Yield function:
$$
f:= \tau + \sigma \tan \phi - c
$$
with
$$
\begin{align}
\tau &= s \cos \phi \\
\sigma &= \sigma_m+s \sin \phi \\
s &= \frac{\sigma_1-\sigma_3}{2} \\
\sigma_m &= \frac{\sigma_1+\sigma_3}{2}
\end{align}
$$
where $\sigma_\alpha$ is the $\alpha$ th principal stress evaluating by
$$
\sigma_\alpha = \sigma_{ij} n_i^{(\alpha)}n_j^{(\alpha)}
$$
and $n_i^{(\alpha)}$'s are the components of direction relating to $\sigma_\alpha$.
In accordance with consistency condition, the [[Return mapping algorithm|elastoplastic modulus]] is attained by
$$
C_{ijkl}^{ep} = C_{ijkl} -
\frac{C_{ijab} \frac{\partial f}{\partial \sigma_{ab}} \frac{\partial f}{\partial \sigma_{cd}} C_{cdkl}}
{\frac{\partial f}{\partial \sigma_{ef}} C_{efgh} \frac{\partial f}{\partial \sigma_{gh}}}
$$
with
$$
C_{ijkl} = \lambda \delta_{ij} \delta_{kl} + \mu (\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk})
$$
$$
\begin{split}
\frac{\partial f}{\partial \sigma_{ij}} &= \frac{\partial \tau}{\partial \sigma_{ij}} + \frac{\partial \sigma}{\partial \sigma_{ij}}\tan\phi \\
&= \frac{\partial s}{\partial \sigma_{ij}} \frac{1}{\cos\phi} + \frac{\partial \sigma_m}{\sigma_{ij}}\tan\phi \\
&= \frac{1}{2}n_i^{(1)}n_j^{(1)}\frac{\sin \phi + 1}{\cos \phi} + \frac{1}{2}n_i^{(3)}n_j^{(3)}\frac{\sin \phi - 1}{\cos \phi}
\end{split}
$$
$$
\begin{split}
\frac{\partial s}{\partial \sigma_{ij}} &= \frac{1}{2}(\frac{\partial \sigma_1}{\partial \sigma_{ij}}-\frac{\partial \sigma_3}{\partial \sigma_{ij}}) \\
&= \frac{1}{2}(n_i^{(1)}n_j^{(1)}-n_i^{(3)}n_j^{(3)}) \\
\end{split}
$$
$$
\begin{split}
\frac{\partial \sigma_m}{\partial \sigma_{ij}} &= \frac{1}{2}(\frac{\partial \sigma_1}{\partial \sigma_{ij}}+\frac{\partial \sigma_3}{\partial \sigma_{ij}}) \\
&= \frac{1}{2}(n_i^{(1)}n_j^{(1)}+n_i^{(3)}n_j^{(3)}) \\
\end{split}
$$
$$
\begin{split}
\frac{\partial f}{\partial \sigma_{ij}} C_{ijkl} \frac{\partial f}{\partial \sigma_{kl}}
&= \frac{1}{4\cos^2\phi}C_{ijkl}n_i^{(1)}n_j^{(1)}n_k^{(1)}n_l^{(1)}(\sin \phi + 1)^2 \\
&+ \frac{1}{4\cos^2\phi}C_{ijkl}n_i^{(3)}n_j^{(3)}n_k^{(3)}n_l^{(3)}(\sin \phi - 1)^2 \\
&+ \frac{1}{4\cos^2\phi}C_{ijkl}(n_i^{(1)}n_j^{(1)}n_k^{(3)}n_l^{(3)}+n_i^{(3)}n_j^{(3)}n_k^{(1)}n_l^{(1)})(\sin^2 \phi - 1) \\
&= \frac{1}{4\cos^2\phi}(\lambda + 2\mu)(\sin^2\phi+2\sin\phi+1) \\
&+ \frac{1}{4\cos^2\phi}(\lambda + 2\mu)(\sin^2\phi-2\sin\phi+1) \\
&- \frac{1}{2}\lambda \\
&= \tan^2\phi\lambda + \frac{1+\sin^2\phi}{\cos^2\phi}\mu
\end{split}
$$

# Yield function 2
$$
f:= \sigma_1 - \sigma_3 + (\sigma_1+\sigma_3) \sin \phi - 2 c \cos \phi
$$
$$
\begin{split}
\frac{\partial f}{\partial \sigma_{ij}} &= (\sin\phi+1)\frac{\partial \sigma_1}{\sigma_{ij}} + (\sin\phi-1)\frac{\partial \sigma_3}{\partial \sigma_{ij}}\\
&= (\sin\phi+1)n_i^{(1)}n_j^{(1)} + (\sin\phi-1)n_i^{(3)}n_j^{(3)}\\
\end{split}
$$
$$
\begin{split}
C_{ijab}\frac{\partial f}{\partial \sigma_{ab}} &= (\lambda \delta_{ij} \delta_{ab} + \mu(\delta_{ia}\delta_{jb}+\delta_{ib}\delta_{ja}))
((\sin\phi+1)n_a^{(1)}n_b^{(1)} + (\sin\phi-1)n_a^{(3)}n_b^{(3)})\\
&= 2 \sin\phi\lambda \delta_{ij} + 2((\sin\phi+1)n_i^{(1)}n_j^{(1)} + (\sin\phi-1)n_i^{(3)}n_j^{(3)})\mu
\end{split}
$$
$$
\begin{split}
C_{ijab}\frac{\partial f}{\partial \sigma_{ab}}\frac{\partial f}{\partial \sigma_{cd}} C_{cdkl}
&= 4 \sin^2\phi\lambda^2 \delta_{ij} \delta_{kl} \\
&+ 4 \sin\phi(\sin\phi+1) \lambda\mu \delta_{ij}n_k^{(1)}n_l^{(1)} \\
&+ 4 \sin\phi(\sin\phi-1) \lambda\mu \delta_{ij}n_k^{(3)}n_l^{(3)} \\
&+ 4 \sin\phi(\sin\phi+1) \lambda\mu n_i^{(1)}n_j^{(1)}\delta_{kl} \\
&+ 4 \sin\phi(\sin\phi-1) \lambda\mu n_i^{(3)}n_j^{(3)}\delta_{kl} \\
&+ 4 (\sin\phi+1)(\sin\phi+1) \mu^2 n_i^{(1)}n_j^{(1)}n_k^{(1)}n_l^{(1)} \\
&+ 4 (\sin\phi-1)(\sin\phi+1) \mu^2 n_i^{(3)}n_j^{(3)}n_k^{(1)}n_l^{(1)} \\
&+ 4 (\sin\phi+1)(\sin\phi-1) \mu^2 n_i^{(1)}n_j^{(1)}n_k^{(3)}n_l^{(3)} \\
&+ 4 (\sin\phi-1)(\sin\phi-1) \mu^2 n_i^{(3)}n_j^{(3)}n_k^{(3)}n_l^{(3)} \\
\end{split}
$$
$$
\begin{split}
\frac{\partial f}{\partial \sigma_{ij}} C_{ijkl} \frac{\partial f}{\partial \sigma_{kl}}
&= C_{ijkl}n_i^{(1)}n_j^{(1)}n_k^{(1)}n_l^{(1)}(\sin \phi + 1)^2 \\
&+ C_{ijkl}n_i^{(3)}n_j^{(3)}n_k^{(3)}n_l^{(3)}(\sin \phi - 1)^2 \\
&+ C_{ijkl}(n_i^{(1)}n_j^{(1)}n_k^{(3)}n_l^{(3)}+n_i^{(3)}n_j^{(3)}n_k^{(1)}n_l^{(1)})(\sin^2 \phi - 1) \\
&= (\lambda + 2\mu)(\sin^2\phi+2\sin\phi+1) \\
&+ (\lambda + 2\mu)(\sin^2\phi-2\sin\phi+1) \\
&+ 2(\sin^2 \phi-1)\lambda \\
&= 4\sin^2\phi\lambda + 4(1+\sin^2\phi)\mu
\end{split}
$$

# Yield function with the terms of invariants
The Mohr-Coulomb criterion can be rephrased in terms of invariants $I_1$, $J_2$ and *Lode angle* $0\le \theta \le \frac{\pi}{3}$ as
$$
f:= \frac{1}{3} I_1 \sin\phi + \sqrt{J_2}(\cos\theta - \frac{1}{\sqrt{3}}\sin\theta \sin\phi)-c\cos\phi
$$
$$
\frac{\partial f}{\partial \sigma_{ij}} = \frac{1}{3}\sin\phi \frac{\partial I_1}{\partial \sigma_{ij}} +
\frac{1}{2\sqrt{J_2}}(\cos\theta-\frac{1}{\sqrt{3}}\sin\theta\sin\phi) \frac{\partial J_2}{\partial \sigma_{ij}} -
\sqrt{J_2}(\sin\theta-\frac{1}{\sqrt{3}}\cos\theta\sin\phi)\frac{\partial \theta}{\partial \sigma_{ij}}
$$
$$
\frac{\partial I_1}{\partial \sigma_{ij}} = \delta_{ij}
$$
