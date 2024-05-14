---
icon: OcInfinity16
---

#Elasticity #Curvilinear


The principal invariants of a second-order tensor $\boldsymbol A$ are given by
$$
\left \{
\begin{split}
I_1(\boldsymbol A) &= \mathrm{tr}(\boldsymbol A) = A_{ii} \\
I_2(\boldsymbol A) &= \frac{1}{2}(\mathrm{tr}^2(\boldsymbol A)-\mathrm{tr}(\boldsymbol A \cdot \boldsymbol A))
= \frac{1}{2}(A_{ii}A_{jj}-A_{ij}A_{ji}) \\
I_3(\boldsymbol A) &= \det(\boldsymbol A) = \epsilon_{ijk}A_{1i}A_{2j}A_{3k} \\
\end{split}
\right .
$$
The derivatives of the principal invariants of a second-order tensor with respect to the tensor itself are often required in constitutive equations. For reference
$$
\frac{\partial I_1}{\partial A_{ij}} = \frac{\partial A_{kk}}{\partial A_{ij}} = \delta_{ki}\delta_{kj} = \delta_{ij}
$$
$$
\frac{\partial I_1}{\boldsymbol A} = \boldsymbol I
$$
$$
\begin{split}
\frac{\partial I_2}{\partial A_{ij}} &= \frac{\partial (\frac{1}{2}(A_{kk}A_{ll}-A_{kl}A_{lk}))}{\partial A_{ij}} \\
&= \frac{1}{2}(\delta_{ki}\delta_{kj}A_{ll}+\delta_{li}\delta_{lj}A_{kk}-\delta_{ki}\delta_{lj}A_{lk}-\delta_{li}\delta_{kj}A_{kl}) \\
&=A_{kk}\delta_{ij}-A_{ji}
\end{split}
$$
$$
\frac{\partial I_2}{\partial \boldsymbol A} = I_1 \boldsymbol I - \boldsymbol A^T
$$
$$
\begin{split}
\frac{\partial I_3}{\partial A_{ij}} &= \frac{\partial (\epsilon_{klm}A_{1k}A_{2l}A_{3m})}{\partial A_{ij}} \\
&= \epsilon_{klm}(\delta_{1i}\delta_{kj}A_{2l}A_{3m}+\delta_{2i}\delta_{lj}A_{1k}A_{3m}+\delta_{3i}\delta_{mj}A_{1k}A_{2l}) \\
&= \epsilon_{klm}(\delta_{1i}\delta_{kj}A_{2l}A_{3m}+\delta_{2i}\delta_{lj}A_{1k}A_{3m}+\delta_{3i}\delta_{mj}A_{1k}A_{2l}) \\
&= \frac{\partial \left (
\begin{multline}
A_{11}A_{22}A_{33}+A_{12}A_{23}A_{31}+A_{13}A_{21}A_{32} \\
-A_{13}A_{22}A_{31}-A_{12}A_{21}A_{33}-A_{11}A_{23}A_{32}
\end{multline}
\right )}{\partial A_{ij}} \\
&= A_{jk}A_{ki} - I_1 A_{ji} + I_2 \delta_{ji} \\
&= \det(\boldsymbol A) A_{ji}^{-1} \\
\end{split}
$$
$$
\frac{\partial I_3}{\partial \boldsymbol A} = (\boldsymbol A \cdot \boldsymbol A - I_1 \boldsymbol A + I_2 \boldsymbol I)^T = \frac{1}{\det \boldsymbol A} \boldsymbol A^{-T}
$$
where
$$
\boldsymbol A^{-1} = \frac{1}{\det\boldsymbol A}(\boldsymbol A \cdot \boldsymbol A - I_1 \boldsymbol A + I_2 \boldsymbol I)
$$
$$
A_{ij}^{-1} = \frac{1}{\det \boldsymbol A}(A_{ik}A_{kj}-I_1A_{ij}+I_2\delta_{ij})
$$

The derivatives of the inverse matrix can be got by
$$
\begin{gather}
\frac{\partial (\boldsymbol A \cdot \boldsymbol A^{-1})}{\partial \boldsymbol A} = \boldsymbol I \otimes \boldsymbol I \cdot \boldsymbol A^{-1} + \boldsymbol A \cdot \frac{\partial \boldsymbol A^{-1}}{\partial \boldsymbol A} = \frac{\partial \boldsymbol I}{\partial \boldsymbol A} = \boldsymbol 0 \\
\Rightarrow \frac{\partial \boldsymbol A^{-1}}{\partial \boldsymbol A} = - \boldsymbol A^{-1} \otimes \boldsymbol A^{-1}
\end{gather}
$$
$$
\begin{gather}
\begin{split}
\frac{\partial (A_{mn}A_{nl}^{-1})}{\partial A_{ij}} &= \frac{\partial A_{mn}}{\partial A_{ij}}A_{nl}^{-1} + A_{mn}\frac{\partial A_{nl}^{-1}}{\partial A_{ij}} \\
&= \delta_{im}\delta_{jn} A_{nl}^{-1} + A_{mn} \frac{\partial A_{nl}^{-1}}{\partial A_{ij}} \\
&= 0 \\
\end{split} \\
\Rightarrow
\delta_{im}\delta_{jn} A_{km}^{-1}A_{nl}^{-1} + A_{km}^{-1}A_{mn} \frac{\partial A_{nl}^{-1}}{\partial A_{ij}} = A_{ki}^{-1}A_{jl}^{-1} + \delta_{kn} \frac{\partial A_{nl}^{-1}}{\partial A_{ij}} = 0 \\
\Rightarrow
\frac{\partial A_{kl}^{-1}}{\partial A_{ij}} = - A_{ki}^{-1}A_{jl}^{-1}
\end{gather}
$$
