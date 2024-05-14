---
icon: OcInfinity16
---
#Math/Geometry

Length:

$$
\begin{equation}
L = \left \{ 
\begin{array}{l}
x_2 - x_1 \\
\sqrt{(x_2 - x_1)^2 + (y_2-y_1)^2} \\
\sqrt{(x_2 - x_1)^2 + (y_2-y_1)^2 + (z_2-z_1)^2}
\end{array}
\right . =
\Vert \boldsymbol{x}_2 - \boldsymbol{x}_1 \Vert
= \left \vert
\begin{array}{c}
\boldsymbol{e}_1 & \boldsymbol{e}_2 & \boldsymbol{e}_3 \\
x_2-x_1 & y_2-y_1 & z_2-z_1 
\end{array}
\right \vert
\end{equation}
$$

Area:

$$
\begin{equation}
A = 0.5(x_1 y_2 + x_2 y_3 + x_3 y_1 - x_2 y_1 - x_3 y_2 + x_1 y_3) 
= \frac{1}{2} \left \vert
\begin{array}{c}
\boldsymbol{e}_1 & \boldsymbol{e}_2 & \boldsymbol{e}_3 \\
x_2-x_1 & y_2-y_1 & z_2-z_1 \\
x_3-x_1 & y_3-y_1 & z_3-z_1
\end{array}
\right \vert
\end{equation} =
\frac{1}{2} \Vert (\boldsymbol{x}_2 - \boldsymbol{x}_1)\times(\boldsymbol{x}_3 - \boldsymbol{x}_1) \Vert
$$

Volume:

$$
\begin{equation}
V = \frac{1}{6} \Vert (\boldsymbol{x}_2 - \boldsymbol{x}_1)\times(\boldsymbol{x}_3 - \boldsymbol{x}_1) \cdot (\boldsymbol{x}_4 - \boldsymbol{x}_1) \Vert
\end{equation}
$$

## Inverse of Jacobi
Jacobi for segment

$$
\begin{equation}
\begin{split}
\boldsymbol{x} &= \frac{1-\xi}{2}\boldsymbol{x}_1 + \frac{1+\xi}{2}\boldsymbol{x}_2 \\
\boldsymbol{J} &= \frac{d\boldsymbol{x}}{d\xi} = \frac{\boldsymbol{x}_2 - \boldsymbol{x}_1}{2}
\end{split}
\end{equation}
$$

$$
\begin{equation}
\begin{split}
\frac{dN(\boldsymbol{x})}{ds} &= \frac{dN(\boldsymbol{x})}{dx}\frac{dx}{ds}+
                                 \frac{dN(\boldsymbol{x})}{dy}\frac{dy}{ds}+
                                 \frac{dN(\boldsymbol{x})}{dz}\frac{dz}{ds} \\
s(\boldsymbol{x}) &= \sqrt{(x-x_1)^2 + (y-y_1)^2 + (z-z_1)^2} \\
&= \frac{1+\xi}{2}L\\
\frac{ds}{dx} &= \frac{x-x_1}{s} = \frac{x_2 - x_1}{L}
\end{split}
\end{equation}
$$

$$
\begin{equation}
\begin{split}
\begin{Bmatrix}
N_{,x} \\ N_{,y} \\ N_{,z}
\end{Bmatrix} &= 
\begin{Bmatrix}
N_{,\xi} \frac{d\xi}{dx} \\ N_{,\xi} \frac{d\xi}{dy} \\ N_{,\xi} \frac{d\xi}{dz}
\end{Bmatrix} \\
\frac{d\xi}{dx} = \frac{2}{x_2 - x_1}
\end{split}
\end{equation}
$$

$$
\begin{equation}
\begin{split}
\begin{Bmatrix}
N_{1,s} \\ N_{2,s}
\end{Bmatrix} &= 
\begin{Bmatrix}
N_{1,\xi} \\ N_{2,\xi}
\end{Bmatrix}
\begin{Bmatrix}
\frac{d\xi}{dx} & \frac{d\xi}{dy} & \frac{d\xi}{dz}
\end{Bmatrix}
\begin{Bmatrix}
\frac{x-x_1}{s} \\ \frac{y-y_1}{s} \\ \frac{z-z_1}{s}
\end{Bmatrix} \\
&= \begin{Bmatrix}
N_{1,\xi} \\ N_{2,\xi}
\end{Bmatrix}

\end{split}
\end{equation}
$$
