---
icon: OcInfinity16
---

#Elasticity #NonlinearElasticity

The potential energy of hyperelasticity material is given by
$$
\begin{split}
\Pi(\boldsymbol u) &= \int_{\Omega} W d\Omega - \int_{\Gamma^t} \boldsymbol u \cdot \boldsymbol t d\Gamma - \int_{\Omega} \boldsymbol u \cdot \boldsymbol b d\Omega \\
&= \int_{\Omega} W d\Omega - W^{ext}
\end{split}
$$
where $W$ is the strain energy density, $W^{ext}$ is external energy. With a variation operation, the Galerkin weak form is attain as
$$
\delta \Pi(\boldsymbol u) = \int_{\Omega} \delta \boldsymbol E : \boldsymbol S d\Omega - \delta W^{ext} = 0
$$
with
$$
\delta W^{ext} = \int_{\Gamma^t} \delta \boldsymbol u \cdot \boldsymbol t d\Gamma + \int_{\Omega} \delta \boldsymbol u \cdot \boldsymbol b d\Omega
$$
Use the approximation to discrete the displacement and its virtual counterpart, yields
$$
\boldsymbol u = \sum_{I=1}^{n_p} N_I \boldsymbol d_I, \quad \delta \boldsymbol u = \sum_{I=1}^{n_p} N_I \delta \boldsymbol d_I
$$
$$
u_i = \sum_{I=1}^{n_p} N_I d_{iI}, \quad \delta u_i = \sum_{I=1}^{n_p} N_I \delta d_{iI}
$$
correspondingly, the deformation gradient can be evaluated by
$$
\delta F_{iI} = \delta u_{i,I}
$$
$$
\begin{split}
\delta E_{IJ} &= \frac{1}{2} \delta C_{IJ} \\
&= \frac{1}{2}(\delta F_{iI} F_{iJ} + F_{iI} \delta F_{iJ}) \\
&= \frac{1}{2}(\delta u_{i,I} (\delta_{iJ}+u_{i,J}) + (\delta_{iI}+u_{i,I}) \delta u_{i,J}) \\
&= \frac{1}{2}(\delta u_{J,I}  + \delta u_{I,J} + \delta u_{i,I} u_{i,J} + u_{i,I}\delta u_{i,J}) \\
&= \frac{1}{2}(\delta u_{i,J}(\delta_{iI}+u_{i,I}) + \delta u_{i,I}(\delta_{iJ}+u_{i,J})) \\
&= \frac{1}{2}(\delta u_{i,J}F_{iI} + \delta u_{i,I}F_{iJ}) \\
\end{split}
$$
**Internal force**
$$
\begin{split}
E_{IJ} &= \frac{1}{2}(F_{iI}F_{iJ}-1) \\
&= \frac{1}{2}(F_{1I}F_{1J}+F_{2I}F_{2J}+F_{3I}F_{3J}-1)
\end{split}
$$
$$
\begin{split}
\int_{\Omega} \delta E_{IJ} S_{IJ} d\Omega &= \int_{\Omega} \frac{1}{2}(\delta u_{i,J}F_{iI}+\delta u_{i,I}F_{iJ}) S_{IJ} d\Omega \\
&= \sum_{K=1}^{n_p} \delta d_{iK} \int_{\Omega} \frac{1}{2}(N_{K,J}F_{iI}+N_{K,I}F_{iJ}) S_{IJ} d\Omega \\
&= \sum_{K=1}^{n_p} \delta d_{iK} f_{iK}^{int} \\
\end{split}
$$
$$
\boldsymbol f_{I}^{int} = \{ f_{1I}^{int},\;  f_{2I}^{int},\; f_{3I}^{int} \}^T
$$
$$
\begin{split}
f_{iA}^{int} &= \int_{\Omega} \frac{1}{2}(N_{A,J}F_{iI} + N_{A,I}F_{iJ})S_{IJ}d\Omega \\
&= \int_{\Omega}
\left (
\begin{split}
&N_{A,1}F_{i1}S_{11} + N_{A,2}F_{i2}S_{22} + N_{A,3}F_{i3}S_{33} \\
&+ (N_{A,1}F_{i2}+N_{A,2}F_{i1})S_{12} \\
&+ (N_{A,1}F_{i3}+N_{A,3}F_{i1})S_{13} \\
&+ (N_{A,2}F_{i3}+N_{A,3}F_{i2})S_{23}
\end{split}
\right ) d\Omega
\end{split}
$$
**Stiffness matrix**
$$
\Delta F_{iI} = \sum_{A=1}^{n_p} \Psi_{A,I} d_{iA}
$$
$$
\begin{split}
\Delta E_{IJ} &= \frac{1}{2}(\Delta u_{i,J}F_{iI}+\Delta u_{i,I}F_{iJ}) \\
&= \sum_{A=1}^{n_p} \frac{1}{2}(N_{A,J}F_{iI}+N_{A,I}F_{iJ})d_{iA}
\end{split}
$$
$$
\begin{split}
\Delta f_{iA}^{int} &= \int_{\Omega} \frac{1}{2}(N_{A,J}\Delta F_{iI}+N_{A,I}\Delta F_{iJ})S_{IJ}+\frac{1}{2}(N_{A,J}F_{iI}+N_{A,I}F_{iJ})\Delta S_{IJ})d\Omega \\
&= \sum_{B=1}^{n_p}\int_{\Omega} \frac{1}{2}(N_{A,J}N_{B,I}+N_{A,I}N_{B,J})S_{IJ}d\Omega d_{iB} \\
&+\sum_{B=1}^{n_p} \int_{\Omega} \frac{1}{2}(N_{A,J}F_{iI}+N_{A,I}F_{iJ})C_{IJKL}\frac{1}{2}(N_{B,L}F_{jK}+N_{B,K}F_{jL})d\Omega d_{jB} \\
&= \sum_{B=1}^{n_p} (K_{AB}^G d_{iB}+K_{ijAB}^M d_{jB}) \\
&= \sum_{B=1}^{n_p} (K_{AB}^G \delta_{ij}+K_{ijAB}^M) d_{jB} \\
\end{split}
$$
$$
\begin{split}
K_{(3A-3+i)(3B-3+j)}^G &= \int_{\Omega} \frac{1}{2}(N_{A,J}N_{B,I}+N_{A,I}N_{B,J})S_{IJ}d\Omega \\
&= \int_{\Omega}
\left (
\begin{split}
&N_{A,1}N_{B,1}S_{11} + N_{A,2}N_{B,2}S_{22} + N_{A,3}N_{B,3}S_{33} \\
&+(N_{A,1}N_{B,2}+N_{A,2}N_{B,1})S_{12} \\
&+(N_{A,1}N_{B,3}+N_{A,3}N_{B,1})S_{13} \\
&+(N_{A,2}N_{B,3}+N_{A,3}N_{B,2})S_{23}
\end{split}
\right )
d\Omega
\end{split}
$$
$$
\begin{split}
K_{(3A-3+i)(3B-3+j)}^M &= \int_{\Omega} \frac{1}{2}(N_{A,J}F_{iI}+N_{A,I}F_{iJ})C_{IJKL}\frac{1}{2}(N_{B,L}F_{jK}+N_{B,K}F_{jL})d\Omega \\
&= \int_{\Omega}
\left (
\begin{split}
&N_{A,1}F_{i1}N_{B,1}F_{j1}C_{1111} \\
&+N_{A,2}F_{i2}N_{B,2}F_{j2}C_{2222} \\
&+N_{A,3}F_{i3}N_{B,3}F_{j3}C_{3333} \\
&+(N_{A,1}F_{i1}N_{B,2}F_{j2}+N_{A,2}F_{i2}N_{B,1}F_{j1})C_{1122} \\
&+(N_{A,1}F_{i1}N_{B,3}F_{j3}+N_{A,3}F_{i3}N_{B,1}F_{j1})C_{1133} \\
&+(N_{A,2}F_{i2}N_{B,3}F_{j3}+N_{A,3}F_{i3}N_{B,2}F_{j2})C_{2233} \\
&+(N_{A,1}F_{i2}+N_{A,2}F_{i1})(N_{B,1}F_{j2}+N_{B,2}F_{j1})C_{1212} \\
&+(N_{A,1}F_{i3}+N_{A,3}F_{i1})(N_{B,1}F_{j3}+N_{B,3}F_{j1})C_{1313} \\
&+(N_{A,2}F_{i3}+N_{A,3}F_{i2})(N_{B,2}F_{j3}+N_{B,3}F_{j2})C_{2323} \\
\end{split}
\right ) d\Omega
\end{split}
$$
