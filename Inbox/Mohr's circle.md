---
icon: OcInfinity16
---

#NonlinearElasticity/Plasticity 

main and shear stress's projection to a surface with normal $\boldsymbol n = \{-\sin\alpha,\cos\alpha\}, \boldsymbol s = \{n_2, -n_1\}$
$$
\begin{split}
\sigma &= \boldsymbol n \cdot \boldsymbol \sigma \cdot \boldsymbol n \\
&= \sigma_{11} n_1^2 + \sigma_{22} n_2^2 + 2\sigma_{12} n_1 n_2 \\
&= \sigma_{11} \sin^2\alpha + \sigma_{22} \cos^2\alpha - 2\sigma_{12} \sin\alpha \cos\alpha \\
&= \frac{1}{2}(\sigma_{11}+\sigma_{22}) + \frac{1}{2}(\sigma_{11}-\sigma_{22}) \cos 2\alpha - \sigma_{12} \sin 2\alpha \\
&= \frac{1}{2}(\sigma_{1}+\sigma_{2}) + \frac{1}{2}(\sigma_{1}-\sigma_{2}) \cos 2(\alpha-\alpha^{(1)}) \\
\end{split}
$$
$$
\begin{split}
\tau &= \boldsymbol n \cdot \boldsymbol \sigma \cdot \boldsymbol s \\
&= \sigma_{11} n_1 s_1 + \sigma_{22} n_2 s_2 + \sigma_{12} (n_1 s_2 + n_2 s_1) \\
&= (\sigma_{22}-\sigma_{11}) \sin\alpha \cos\alpha - \sigma_{12}(\cos^2 \alpha - \sin^2 \alpha) \\
&= \frac{1}{2}(\sigma_{22}-\sigma_{11}) \sin 2\alpha - \sigma_{12}\cos 2 \alpha \\
&= \frac{1}{2}(\sigma_{2}-\sigma_{1}) \sin 2(\alpha - \alpha^{(1)})
\end{split}
$$
