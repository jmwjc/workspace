---
icon: OcInfinity16
---

#Math #Program/Coding  
$$
\boldsymbol{A}^{-1} = \begin{bmatrix}
    a_{11} & a_{12} & a_{13} \\
    a_{12} & a_{22} & a_{23} \\
    a_{13} & a_{23} & a_{33}
\end{bmatrix}
$$
$$
\boldsymbol{A}_{,x} = \begin{bmatrix}
    b_{11} & b_{12} & b_{13} \\
    b_{12} & b_{22} & b_{23} \\
    b_{13} & b_{23} & b_{33}
\end{bmatrix}
$$
$$
\boldsymbol{A}^{-1}\boldsymbol{A}_{,x} = \begin{bmatrix}
    a_{1i}b_{1i} & a_{1i}b_{2i} & a_{1i}b_{3i} \\
    a_{2i}b_{1i} & a_{2i}b_{2i} & a_{2i}b_{3i} \\
    a_{3i}b_{1i} & a_{3i}b_{2i} & a_{3i}b_{3i}
\end{bmatrix}
$$
$$
\boldsymbol{A}^{-1}\boldsymbol{A}_{,x}\boldsymbol{A}^{-1} = \begin{bmatrix}
    a_{1i}b_{ij}a_{j1} & a_{1i}b_{ij}a_{j2} & a_{1i}b_{ij}a_{j3} \\
    a_{2i}b_{ij}a_{j1} & a_{2i}b_{ij}a_{j2} & a_{2i}b_{ij}a_{j3} \\
    a_{3i}b_{ij}a_{j1} & a_{3i}b_{ij}a_{j2} & a_{3i}b_{ij}a_{j3}
\end{bmatrix}
$$
$$
\boldsymbol{A} = \boldsymbol{L}\boldsymbol{L}^{T} = \boldsymbol{U}^{T}\boldsymbol{U}
$$
$$
\boldsymbol{A}^{-1} = \boldsymbol{L}^{-T}\boldsymbol{L}^{-1} = \boldsymbol{U}^{-1}\boldsymbol{U}^{-T}
$$
$$
\boldsymbol{A}^{-1}\boldsymbol{A}_{,x}\boldsymbol{A}^{-1} = \boldsymbol{U}^{-1}\boldsymbol{U}^{-T}\boldsymbol{A}_{,x}\boldsymbol{U}^{-1}\boldsymbol{U}^{-T}
$$
$$
\boldsymbol{U}^{-1} = \begin{bmatrix}
    c_{11} & c_{12} & c_{13} \\
     & c_{22} & c_{23} \\
     &  & c_{33}
\end{bmatrix}
$$
$$
\boldsymbol{U}^{-T}\boldsymbol{A}_{,x} = \begin{bmatrix}
    c_{11}b_{11} & c_{11}b_{12} & c_{11}b_{13} \\
    c_{k2}b_{k1} & c_{k2}b_{k2} & c_{k2}b_{k3} \\
    c_{3i}b_{i1} & c_{3i}b_{i2} & c_{3i}b_{i3}
\end{bmatrix}
$$
$$
\boldsymbol{U}^{-T}\boldsymbol{A}_{,x}\boldsymbol{U}^{-1} = \begin{bmatrix}
    c_{11}b_{11}c_{11} & c_{11}b_{11}c_{12} + c_{11}b_{12}c_{22}  & c_{11}b_{11}c_{13} + c_{11}b_{12}c_{23} + c_{11}b_{13}c_{33} \\
    c_{12}b_{11}c_{11} + c_{22}b_{21}c_{11} & c_{12}b_{11}c_{12} + c_{22}b_{21}c_{12} + c_{12}b_{12}c_{22} + c_{22}b_{22}c_{22} & c_{12}b_{11}c_{13} + c_{22}b_{21}c_{13} + c_{12}b_{22}c_{23} + c_{22}b_{22}c_{23} + c_{12}b_{13}c_{33} + c_{22}c_{23}c_{33} \\
    c_{3i}b_{i1} & c_{3i}b_{i2} & c_{3i}b_{i3}
\end{bmatrix}
$$
$$
\boldsymbol{A}^{-1} = \boldsymbol{U}^{-1}\boldsymbol{U}^{-T} = \begin{bmatrix}
    c_{11}c_{11} + c_{12}c_{12} + c_{13}c_{13} & c_{12}c_{22} + c_{13}c_{23} & c_{13}c_{33} \\
     & c_{22}c_{22} + c_{23}c_{23} & c_{23}c_{33} \\
     &  & c_{33}c_{33}
\end{bmatrix}
$$
$$
\boldsymbol{U}^{-T}\boldsymbol{U}^{-1} = \begin{bmatrix}
    c_{11}c_{11} & c_{11}c_{12} & c_{11}c_{13} \\
     & c_{12}c_{12} + c_{22}c_{22} & c_{12}c_{13} + c_{22}c_{23} \\
     &  & c_{13}c_{13} + c_{23}c_{23} + c_{33}c_{33}
\end{bmatrix}
$$
