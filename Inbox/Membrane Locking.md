---
icon: OcInfinity16
---

#Elasticity/Shell/Thin-shell 
$$
\begin{Bmatrix}
    \varepsilon_{11} \\ \varepsilon_{22} \\ \varepsilon_{12}
\end{Bmatrix} = 
\begin{Bmatrix}
    \boldsymbol{a}_{1} \cdot \boldsymbol{v}_{,1} \\ \boldsymbol{a}_{2} \cdot \boldsymbol{v}_{,2} \\ \boldsymbol{a}_{1} \cdot \boldsymbol{v}_{,2} + \boldsymbol{a}_{2} \cdot \boldsymbol{v}_{,1}
\end{Bmatrix}
$$
$$
\boldsymbol{v} = \begin{Bmatrix}
    v_{1} \\ v_{2} \\ v_{3}
\end{Bmatrix} = 
\begin{bmatrix}
    1 &  &  & x &  &  & y &   &   & \dots \\
     & 1 &  &  & x &  &   & y &   & \dots \\
     &  & 1 &  &  & x &   &   & y & \dots
\end{bmatrix}
$$
$$
\boldsymbol{v} = \begin{Bmatrix}
    c_{11}x + c_{21}y \\ c_{12}x + c_{22}y \\ c_{13}x + c_{23}y
\end{Bmatrix}
$$
$$
\boldsymbol{\varepsilon} = \begin{Bmatrix}
    a_{11}c_{11}+a_{12}c_{12}+a_{13}c_{13} \\
    a_{21}c_{21}+a_{22}c_{22}+a_{23}c_{23} \\
    a_{11}c_{21}+a_{12}c_{22}+a_{13}c_{23} + a_{21}c_{11}+a_{22}c_{12}+a_{23}c_{13}
\end{Bmatrix}
$$
| p     | $n_p$                   | $n_c$      | $n$                      |
| ----- | ----------------------- | ---------- | ------------------------ |
| 0     | 3                       | 0          | 3                        |
| 1     | 9                       | 3          | 6                        |
| 2     | 18                      | 9          | 9                        |
| ...   | ...                     | ...        | ...                      |
| $p>0$ | $\frac{3(p+1)(p+2)}{2}$ | $p^2+3p-1$ | $\frac{(p+1)(p+2)}{2}+3$ |
$$
n_{c}^{opt} = \frac{2n_{dof}}{3} - 3 = 2n_p - 3
$$
