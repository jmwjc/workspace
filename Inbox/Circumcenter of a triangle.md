---
icon: OcInfinity16
---

#Math/Geometry/Voronoi #Program #Math/Geometry/Triangle #Math/Geometry

1. Calculate the mid-point $\boldsymbol x_m$ of edges.
$$
\left \{
\begin{split}
\boldsymbol x_{m_1} &= 0.5(\boldsymbol x_2 + \boldsymbol x_3) \\
\boldsymbol x_{m_2} &= 0.5(\boldsymbol x_3 + \boldsymbol x_1) \\
\end{split}
\right .
$$

2. Calculate slope of edges.
$$
\left \{
\begin{split}
s_{1} &= \frac{y_3-y_2}{x_3-x_2} \\
s_{2} &= \frac{y_1-y_3}{x_1-x_3} \\
\end{split}
\right .
$$

3. Construct bisector lines of edges.
$$
\begin{split}
y = -\frac{1}{s_i} (x-x_{m_i}) + y_{m_i}
\end{split}
$$

4. Use two bisector lines to find circumcenter.
$$
\left \{
\begin{split}
x &= \frac{s_1 s_2(y_{m_1}-y_{m_2})+(s_2 x_{m_1}-s_1 x_{m_2})}{s_2-s_1} \\
y &= \frac{(s_2 y_{m_2}-s_1 y_{m_1})+(x_{m_2}-x_{m_1})}{s_2-s_1} \\
\end{split}
\right .
$$
or
$$
\left \{
\begin{split}
x &= \frac{s_1 s_2(y_{m_1}-y_{m_2})+(s_2 x_{m_1}-s_1 x_{m_2})}{s_2-s_1} \\
y &= \frac{(s_2 y_{m_2}-s_1 y_{m_1})+(x_{m_2}-x_{m_1})}{s_2-s_1} \\
\end{split}
\right .
$$

