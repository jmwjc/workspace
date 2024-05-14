---
icon: OcInfinity16
---

#Math 
$$
\begin{align}
P_0 &= 1\\
P_1 &= x\\
P_2 &= \frac{1}{2}(3x^2-1)\\
P_3 &= \frac{1}{2}(5x^3-3x)\\
P_4 &= \frac{1}{8}(35x^4-30x^2+3)\\
&\dots\\
\end{align}
$$
$$
\begin{align}
P_{0,x} &= 0\\
P_{1,x} &= 1 = P_0\\
P_{2,x} &= 3x = 3P_1\\
P_{3,x} &= \frac{3}{2}(5x^2-1) = 5P_2 + P_0\\
P_{4,x} &= \frac{1}{2}(35x^3-15x) = 7P_3+3P_1\\
P_{2n+1,x} &= \sum_{i=0}^{n}(4i+1)P_{2i} \\
P_{2n,x} &= \sum_{i=1}^{n}(4i-1)P_{2i-1}
&\dots\\
\end{align}
$$
$$
\begin{align}
P_{n+1,x}(x) &= (2n+1)P_n(x) + (2(n-2)+1)P_{n-2} + (2(n-4)+1)P_{n-4}(x)+\dots\\
&= \sum_{i=0,2,4,\dots} (2(n-i)+1)P_{n-i}(x)
\end{align}
$$
$$
u(x,y) = \sum_{i=0} a_{i}(y) P_{i}(x)
$$
$$
u_{,x} = \sum_{i=0} a_{i}(y) P_{i,x}(x) = 
$$
