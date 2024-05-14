---
icon: OcInfinity16
---

#Example #Elasticity 

Displacement

$$
\begin{Bmatrix}
u \\ v \\ w 
\end{Bmatrix} = 
\begin{Bmatrix}
\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) \\ \sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z)  \\ g(z)
\end{Bmatrix}
$$

$$
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ \varepsilon_{33} \\ 2\varepsilon_{12} \\ 2\varepsilon_{13} \\ 2\varepsilon_{23}
\end{Bmatrix} =
\begin{Bmatrix}
u_{,x} \\ v_{,y} \\ w_{,z} \\ v_{,x} + u_{,y} \\ w_{,x} + u_{,z} \\ w_{,y} + v_{,z}
\end{Bmatrix} =
\begin{Bmatrix}
\frac{\pi x}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) \\
\frac{\pi y}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) \\
g'(z) \\
\frac{\pi (x+y)}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) \\
\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f'(z) \\
\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f'(z) \\
\end{Bmatrix}
$$

$$
\begin{split}
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12} \\ \sigma_{13} \\ \sigma_{23}
\end{Bmatrix} &= 
\frac{E}{(1+\nu)(1-2\nu)}
\begin{Bmatrix}
(1-\nu)\varepsilon_{11} + \nu \varepsilon_{22} + \nu \varepsilon_{33} \\
\nu\varepsilon_{11} + (1-\nu) \varepsilon_{22} + \nu \varepsilon_{33} \\
\nu\varepsilon_{11} + \nu \varepsilon_{22} + (1-\nu) \varepsilon_{33} \\
\frac{(1-2\nu)}{2}2\varepsilon_{12} \\ \frac{(1-2\nu)}{2}2\varepsilon_{13} \\ \frac{(1-2\nu)}{2}2\varepsilon_{23}
\end{Bmatrix} \\
&= \frac{E}{(1+\nu)(1-2\nu)}
\begin{Bmatrix}
\frac{\pi ((1-\nu)x + \nu y)}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) + \nu g'(z) \\
\frac{\pi (\nu x + (1-\nu)y)}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) + \nu g'(z) \\
\frac{\pi \nu (x + y)}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) + (1-\nu) g'(z) \\
\frac{(1-2\nu)}{2}\frac{\pi (x+y)}{(r_{o}-r_{i})r}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f(z) \\
\frac{(1-2\nu)}{2}\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f'(z) \\
\frac{(1-2\nu)}{2}\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f'(z) \\
\end{Bmatrix}
\end{split}
$$

$$
\sigma_{11,1} = \frac{E}{(1+\nu)(1-2\nu)}(\frac{\pi}{r_{o}-r_{i}} \frac{(1-\nu)y^2 - \nu xy}{r^3} \cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}})
- \frac{\pi^2}{(r_{o}-r_{i})^2} \frac{(1-\nu)x^2 + \nu xy}{r^2} \sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}})) f(z)\\
\sigma_{12,2} = \frac{E}{(1+\nu)(1-2\nu)}\frac{(1-2\nu)}{2}(\frac{\pi}{r_{o}-r_{i}} \frac{x^2-xy}{r^3}\cos(\pi \frac{r-r_{i}}{r_{o}-r_{i}})
- \frac{\pi^2}{(r_{o}-r_{i})^2}\frac{xy+y^2}{r^2}\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}})) f(z)\\
\sigma_{13,3} = \frac{E}{(1+\nu)(1-2\nu)}\frac{(1-2\nu)}{2}\sin(\pi \frac{r-r_{i}}{r_{o}-r_{i}}) f''(z)
$$

$$
\begin{Bmatrix}
b_{1} \\ b_{2} \\ b_{3}
\end{Bmatrix} = 
\begin{Bmatrix}
\sigma_{11,1} + \sigma_{12,2} + \sigma_{13,3} \\
\sigma_{21,1} + \sigma_{22,2} + \sigma_{23,3} \\
\sigma_{31,1} + \sigma_{32,2} + \sigma_{33,3}
\end{Bmatrix}
$$
