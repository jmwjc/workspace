---
icon: OcInfinity16
---
#Math 

# Legendre Series
The Legendre polynomials $P_{l}(x)$ are established on the interval $(-1,1)$:
$$
\int_{-1}^1 P_{l}(x)P_{k}(x) = \frac{2}{2l+1} \delta_{lk}
$$
where $l = 0,1,2,\dots$, then a variable $f$ can be approximated by the Legendre series as:
$$
f(x) = \sum_{l=0}^\infty c_l P_l(x)
$$
and
$$
c_l = \frac{1}{2}(2l+1) \int_{-1}^{1} f(x) P_l (x) dx
$$
The gradient of $f$ is given by:
$$
f'(x) = \sum_{l=0}^\infty c_l P'_l(x)
$$

$$
\begin{align}
    \int_{-1}^{1} P_{0}(x) f'(x) dx &= \sum_{l=0}^\infty c_l \int_{-1}^{1} P_{0}(x) P'_l(x) dx
\end{align}
$$
$$
\begin{align}
    P'_0(x) &= 0 \\
    P'_1(x) &= P_0(x) = 1 \\
    P'_2(x) &= 3P_1(x) + P'_0 = 3x \\
    P'_3(x) &= 5P_2(x) + P'_1(x) = 5P_2(x) + P_0(x) \\
    P'_4(x) &= 7P_3(x) + P'_2(x) = 7P_3(x) + 3P_1(x) \\
    P'_5(x) &= 9P_4(x) + P'_3(x) = 9P_4(x) + 5P_2(x) + P_0(x) \\
    & \dots \\
    P'_{2l+1}(x) &= \sum_{k=0}^{2l}(4k+1)P_{2k}(x) \\
    P'_{2l+2}(x) &= \sum_{k=0}^{2l+1}(4k+3)P_{2k+1}(x) \\
\end{align}
$$
$$
\begin{align}
    \sum_{l=0}^\infty c_l \int_{-1}^{1} P_{0}(x) P'_l(x) dx &= \sum_{l=0}^{\infty} (c_{2l+1} \int_{-1}^{1} P_0(x) P'_{2l+1}(x) dx + c_{2l+2} \int_{-1}^{1} P_0(x) P'_{2l+2}(x) dx) \\
    &= \sum_{l=0}^{\infty} (c_{2l+1} \int_{-1}^{1} P_0(x) \sum_{k=0}^{2l}(4k+1)P_{2k}(x) dx + c_{2l+2} \int_{-1}^{1} P_0(x) \sum_{k=0}^{2l+1}(4k+3)P_{2k+1}(x) dx) \\
    &= \sum_{l=0}^{\infty} c_{2l+1} \int_{-1}^{1} P_0(x) P_{0}(x) dx \\
\end{align}
$$
$$
\begin{align}
    \int_{-1}^{1} P_{1}(x) f'(x) dx &= \sum_{l=0}^\infty c_l \int_{-1}^{1} P_{1}(x) P'_l(x) dx \\
    &= \sum_{l=0}^{\infty} (c_{2l+1} \int_{-1}^{1} P_1(x) \sum_{k=0}^{2l}(4k+1)P_{2k}(x) dx + c_{2l+2} \int_{-1}^{1} P_1(x) \sum_{k=0}^{2l+1}(4k+3)P_{2k+1}(x) dx) \\
    &= \sum_{l=0}^{\infty} 3c_{2l+2} \int_{-1}^{1} P_1(x) P_{1}(x) dx \\
\end{align}
$$

