---
icon: OcInfinity16
---

#NonlinearElasticity/Plasticity 

![[Return mapping algorithm]]
# Tresca yield criterion
**Yield function**:
$$
f := \frac{1}{2}(\sigma_1 - \sigma_3) - Y \le 0
$$
where $\sigma_\alpha$ is the principal stress evaluating by
$$
\sigma_\alpha = \sigma_{ij} n_{i}^{(\alpha)} n_{j}^{(\alpha)}
$$
$$
\frac{\partial f}{\partial \sigma_{ij}} = n_{i}^{(1)} n_{j}^{(1)} - n_{i}^{(3)} n_{j}^{(3)}
$$
$$
\begin{split}
C_{ijkl} \frac{\partial f^{tr}}{\partial \sigma_{kl}} &= (\lambda \delta_{ij}\delta_{kl} + \mu(\delta_{ik}\delta_{jl} + \delta_{il}\delta_{jk}))(n_{k}^{(1)} n_{l}^{(1)} - n_{k}^{(3)} n_{l}^{(3)}) \\
&= \mu(n_{i}^{(1)} n_{j}^{(1)} + n_{j}^{(1)} n_{i}^{(1)} - n_{i}^{(3)} n_{j}^{(3)} - n_{j}^{(3)} n_{i}^{(3)}) \\
&= 2\mu(n_{i}^{(1)} n_{j}^{(1)} - n_{i}^{(3)} n_{j}^{(3)})
\end{split}
$$
$$
\begin{split}
\frac{\partial f^{tr}}{\partial \sigma_{ij}} C_{ijkl} \frac{\partial f^{tr}}{\partial \sigma_{kl}} &= (n_{i}^{(1)} n_{j}^{(1)} - n_{i}^{(3)} n_{j}^{(3)}) 2\mu (n_{i}^{(1)} n_{j}^{(1)} - n_{i}^{(3)} n_{j}^{(3)}) \\
&= 2\mu (n_{i}^{(1)} n_{j}^{(1)}n_{i}^{(1)} n_{j}^{(1)} + n_{i}^{(3)} n_{j}^{(3)}n_{i}^{(3)} n_{j}^{(3)} - 2 n_{i}^{(1)} n_{j}^{(1)}n_{i}^{(3)} n_{j}^{(3)}) \\
&= 4\mu
\end{split}
$$
$$
C_{ijab} \frac{\partial f}{\partial \sigma_{ab}} \frac{\partial f}{\partial \sigma_{cd}} C_{cdkl} = 4\mu^2 (n_{i}^{(1)} n_{j}^{(1)} - n_{i}^{(3)} n_{j}^{(3)})(n_{k}^{(1)} n_{l}^{(1)} - n_{k}^{(3)} n_{l}^{(3)})
$$

