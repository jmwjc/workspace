---
icon: OcInfinity16
---

#Elasticity #Incompressible 

Dilatation part and deviatoric part

$$
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{12} \\ \sigma_{13} \\ \sigma_{23}
\end{Bmatrix} = 
\frac{E}{1-2\nu}
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
0 \\ 0 \\ 0
\end{Bmatrix} + 
\frac{E}{1+\nu}
\begin{Bmatrix}
 \frac{2}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} - \frac{1}{3}\varepsilon_{33} \\
-\frac{1}{3}\varepsilon_{11} + \frac{2}{3}\varepsilon_{22} - \frac{1}{3}\varepsilon_{33} \\
-\frac{1}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} + \frac{2}{3}\varepsilon_{33} \\ 
\varepsilon_{12} \\ \varepsilon_{13} \\ \varepsilon_{23}
\end{Bmatrix}
$$

$$
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
0 \\ 0 \\ 0
\end{Bmatrix} = \sum_{I=1}^{n_{p}}
\begin{bmatrix}
\frac{1}{3}N_{I,x} & \frac{1}{3}N_{I,y} & \frac{1}{3}N_{I,z} \\
\frac{1}{3}N_{I,x} & \frac{1}{3}N_{I,y} & \frac{1}{3}N_{I,z} \\
\frac{1}{3}N_{I,x} & \frac{1}{3}N_{I,y} & \frac{1}{3}N_{I,z} \\
0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 
\end{bmatrix}
\begin{Bmatrix}
d_{xI} \\ d_{yI} \\ d_{zI}
\end{Bmatrix}
$$

$$
\begin{Bmatrix}
 \frac{2}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} - \frac{1}{3}\varepsilon_{33} \\
-\frac{1}{3}\varepsilon_{11} + \frac{2}{3}\varepsilon_{22} - \frac{1}{3}\varepsilon_{33} \\
-\frac{1}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} + \frac{2}{3}\varepsilon_{33} \\ 
\varepsilon_{12} \\ \varepsilon_{13} \\ \varepsilon_{23}
\end{Bmatrix} = \sum_{I=1}^{n_{p}}
\begin{bmatrix}
 \frac{2}{3}N_{I,x} & -\frac{1}{3}N_{I,y} & -\frac{1}{3}N_{I,z} \\
-\frac{1}{3}N_{I,x} &  \frac{2}{3}N_{I,y} & -\frac{1}{3}N_{I,z} \\
-\frac{1}{3}N_{I,x} & -\frac{1}{3}N_{I,y} &  \frac{2}{3}N_{I,z} \\
 \frac{1}{2}N_{I,y} &  \frac{1}{2}N_{I,x} & 0 \\
 \frac{1}{2}N_{I,z} & 0 & \frac{1}{2}N_{I,x} \\
 0 & \frac{1}{2}N_{I,z} & \frac{1}{2}N_{I,y} 
\end{bmatrix}
\begin{Bmatrix}
d_{xI} \\ d_{yI} \\ d_{zI}
\end{Bmatrix}
$$

Plane strain

$$
\varepsilon_{13} = \varepsilon_{23} = \varepsilon_{33} = 0
$$

$$
\begin{split}
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{12} \\ \sigma_{33}
\end{Bmatrix} &= \frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu &   \nu & 0 \\
  \nu & 1-\nu & 0 \\
    0 &     0 & \frac{(1-2\nu)}{2} \\
  \nu &   \nu & 0 \\
\end{bmatrix}
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix} \\ 
&= 
\frac{E}{1-2\nu}
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
0 \\
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
\end{Bmatrix} + 
\frac{E}{1+\nu}
\begin{Bmatrix}
 \frac{2}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} \\
-\frac{1}{3}\varepsilon_{11} + \frac{2}{3}\varepsilon_{22} \\
\varepsilon_{12} \\
-\frac{1}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} \\ 
\end{Bmatrix}
\end{split}
$$

$$
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
0 \\
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
\end{Bmatrix} = \sum_{I=1}^{n_{p}}
\begin{bmatrix}
\frac{1}{3}N_{I,x} & \frac{1}{3}N_{I,y} \\
\frac{1}{3}N_{I,x} & \frac{1}{3}N_{I,y} \\
0 & 0 \\
\frac{1}{3}N_{I,x} & \frac{1}{3}N_{I,y} \\
\end{bmatrix}
\begin{Bmatrix}
d_{xI} \\ d_{yI} 
\end{Bmatrix}
$$


$$
\begin{Bmatrix}
 \frac{2}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} \\
-\frac{1}{3}\varepsilon_{11} + \frac{2}{3}\varepsilon_{22} \\
\varepsilon_{12} \\
-\frac{1}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} \\ 
\end{Bmatrix} = \sum_{I=1}^{n_{p}}
\begin{bmatrix}
 \frac{2}{3}N_{I,x} & -\frac{1}{3}N_{I,y} \\
-\frac{1}{3}N_{I,x} &  \frac{2}{3}N_{I,y} \\
 \frac{1}{2}N_{I,y} &  \frac{1}{2}N_{I,x} \\
-\frac{1}{3}N_{I,x} & -\frac{1}{3}N_{I,y} \\
\end{bmatrix}
\begin{Bmatrix}
d_{xI} \\ d_{yI}
\end{Bmatrix}
$$

Plane stress

$$
\sigma_{13} = \sigma_{23} = \sigma_{33} = 0, \quad 
\varepsilon_{33} = -\frac{\nu}{1-\nu}(\varepsilon_{11} + \varepsilon_{22})
$$

$$
\begin{split}
\begin{Bmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{12}
\end{Bmatrix} &= \frac{E}{(1+\nu)(1-2\nu)}
\begin{bmatrix}
1-\nu &   \nu & 0 & \nu \\
  \nu & 1-\nu & 0 & \nu \\
    0 &     0 & \frac{(1-2\nu)}{2} & 0\\
\end{bmatrix} 
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12} \\ \varepsilon_{33}
\end{Bmatrix} \\ &= \frac{E}{1-\nu^{2}}
\begin{bmatrix}
  1 & \nu & 0\\
\nu &   1 & 0\\
  0 &   0 & \frac{1-\nu}{2}\\
\end{bmatrix} 
\begin{Bmatrix}
\varepsilon_{11} \\ \varepsilon_{22} \\ 2\varepsilon_{12}
\end{Bmatrix} \\ &=
\frac{E}{1-2\nu}
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33}) \\ 
0
\end{Bmatrix} + 
\frac{E}{1+\nu}
\begin{Bmatrix}
 \frac{2}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22} - \frac{1}{3}\varepsilon_{33} \\
-\frac{1}{3}\varepsilon_{11} + \frac{2}{3}\varepsilon_{22} - \frac{1}{3}\varepsilon_{33} \\
\varepsilon_{12}
\end{Bmatrix} \\ &=
\frac{E}{1-\nu}
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
0
\end{Bmatrix} + 
\frac{E}{1-\nu^{2}}
\begin{Bmatrix}
 \frac{2-\nu}{3}\varepsilon_{11} - \frac{1-2\nu}{3}\varepsilon_{22}\\
-\frac{1-2\nu}{3}\varepsilon_{11} + \frac{2-\nu}{3}\varepsilon_{22}\\
(1-\nu)\varepsilon_{12}
\end{Bmatrix} \\ &= \frac{E}{1-\nu^{2}}
\begin{bmatrix}
  1 & \nu & 0\\
\nu &   1 & 0\\
  0 &   0 & \frac{1-\nu}{2}\\
\end{bmatrix} 
\left (
\begin{Bmatrix}
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}) \\ 
0
\end{Bmatrix} + 
\begin{Bmatrix}
 \frac{2}{3}\varepsilon_{11} - \frac{1}{3}\varepsilon_{22}\\
-\frac{1}{3}\varepsilon_{11} + \frac{2}{3}\varepsilon_{22}\\
2\varepsilon_{12}
\end{Bmatrix}
\right )
\end{split}
$$
# Incompressible
$$
\varepsilon_{ij} = \frac{1}{2}(u_{i,j}+u_{j,i}) = \frac{1}{2}\sum_{I=1}^{n_p}(N_{I,j}d_{iI}+N_{I,i}d_{jI})
$$
$$
\left \{
\begin{split}
\varepsilon_{11} &= \sum_{I=1}^{n_p}N_{I,1}d_{1I} \\
\varepsilon_{22} &= \sum_{I=1}^{n_p}N_{I,2}d_{2I} \\
\varepsilon_{33} &= \sum_{I=1}^{n_p}N_{I,3}d_{3I} \\
2\varepsilon_{12} &= \sum_{I=1}^{n_p}(N_{I,2}d_{1I}+N_{I,1}d_{2I}) \\
2\varepsilon_{13} &= \sum_{I=1}^{n_p}(N_{I,3}d_{1I}+N_{I,1}d_{3I}) \\
2\varepsilon_{23} &= \sum_{I=1}^{n_p}(N_{I,3}d_{2I}+N_{I,2}d_{3I})
\end{split}
\right .
$$
$$
\sigma_{ij} = \frac{E}{1-2\nu} \frac{1}{3} \varepsilon_{kk} \delta_{ij} + \frac{E}{1+\nu}(\varepsilon_{ij}-\frac{1}{3}\varepsilon_{kk} \delta_{ij}) = \sigma_{ij}^v + \sigma_{ij}^d
$$
$$
\sigma_{ij}n_j = \frac{E}{1-2\nu} \frac{1}{3}\varepsilon_{kk} n_i + \frac{E}{1+\nu}(\varepsilon_{ij}n_j-\frac{1}{3}\varepsilon_{kk}n_i)
$$
$$
\begin{split}
\sigma_{ij}^v n_j &= \frac{E}{1-2\nu}\frac{1}{3}\varepsilon_{kk}n_i \\
&= \frac{E}{1-2\nu}\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33})n_i \\
\end{split}
$$
$$
\begin{split}
\sigma_{ij}^d n_j &= \frac{E}{1+\nu}(\varepsilon_{ij}n_j-\frac{1}{3}\varepsilon_{kk}n_i) \\
&= \frac{E}{1+\nu}(\varepsilon_{i1}n_1+\varepsilon_{i2}n_2+\varepsilon_{i3}n_3-\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33})n_i) \\
\end{split}
$$
$$
\begin{split}
\sigma_{11}^dn_1+\sigma_{12}^dn_2+\sigma_{13}^dn_3
&= \frac{E}{1+\nu}(\varepsilon_{11}n_1+\varepsilon_{12}n_2+\varepsilon_{13}n_3-\frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33})n_1) \\
&= \frac{E}{1+\nu}((\frac{2}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{33})n_1+\varepsilon_{12}n_2+\varepsilon_{13}n_3) \\
\end{split}
$$
$$
\int_{\Gamma^g} \delta u_i \sigma_{ij}^v n_j d\Gamma = \int_{\Gamma^g} \frac{E}{1-2\nu}(\delta u_1 n_1+\delta u_2 n_2+\delta u_3 n_3) \frac{1}{3}(\varepsilon_{11}+\varepsilon_{22}+\varepsilon_{33})d\Gamma
$$
$$
\boldsymbol K_{IJ}^v = \int_{\Gamma^g} \frac{E}{1-2\nu}\frac{1}{3}
\begin{bmatrix}
    N_IN_{J,1}n_1 & N_IN_{J,2}n_1 & N_IN_{J,3}n_1 \\
    N_IN_{J,1}n_2 & N_IN_{J,2}n_2 & N_IN_{J,3}n_2 \\
    N_IN_{J,1}n_3 & N_IN_{J,2}n_3 & N_IN_{J,3}n_3
\end{bmatrix}
d\Gamma
$$
$$
\int_{\Gamma^g} \delta u_i \sigma_{ij}^d n_j d\Gamma = \int_{\Gamma^g} \frac{E}{1+\nu}
\left (
\begin{array}{l}
\delta u_1((\frac{2}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{33})n_1+\varepsilon_{12}n_2+\varepsilon_{13}n_3) \\
\delta u_2(\varepsilon_{21}n_1+(\frac{2}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{33})n_2+\varepsilon_{23}n_3) \\
\delta u_3(\varepsilon_{31}n_1+\varepsilon_{32}n_2+(\frac{2}{3}\varepsilon_{33}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22})n_3) \\
\end{array}
\right )
d\Gamma
$$
$$
\boldsymbol K_{IJ}^d = \int_{\Gamma^g} \frac{E}{1+\nu}
\begin{bmatrix}
    N_I(\frac{2}{3}n_1N_{J,1}+\frac{1}{2}n_2N_{J,2}+\frac{1}{2}n_3N_{J,3}) &
    N_I(\frac{1}{2}n_2N_{J,1}-\frac{1}{3}n_1N_{J,2}) &
    N_I(\frac{1}{2}n_3N_{J,1}-\frac{1}{3}n_1N_{J,3}) \\
    N_I(\frac{1}{2}n_1N_{J,2}-\frac{1}{3}n_2N_{J,1}) &
    N_I(\frac{1}{2}n_1N_{J,1}+\frac{2}{3}n_2N_{J,2}+\frac{1}{2}n_3N_{J,3}) &
    N_I(\frac{1}{2}n_3N_{J,2}-\frac{1}{3}n_2N_{J,3}) \\
    N_I(\frac{1}{2}n_1N_{J,3}-\frac{1}{3}n_3N_{J,1}) &
    N_I(\frac{1}{2}n_2N_{J,3}-\frac{1}{3}n_3N_{J,2}) &
    N_I(\frac{1}{2}n_1N_{J,1}+\frac{1}{2}n_2N_{J,2}+\frac{2}{3}n_3N_{J,3}) \\
\end{bmatrix}
d\Gamma
$$
$$
\int_{\Gamma^g} \delta u_i n_{ij} \sigma_{jk}^d n_k d\Gamma = \int_{\Gamma^g} \frac{E}{1+\nu}
\left (
\begin{array}{l}
\delta u_1n_{11}((\frac{2}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{33})n_1+\varepsilon_{12}n_2+\varepsilon_{13}n_3) \\
\delta u_1n_{12}(\varepsilon_{21}n_1+(\frac{2}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{33})n_2+\varepsilon_{23}n_3) \\
\delta u_1n_{13}(\varepsilon_{31}n_1+\varepsilon_{32}n_2+(\frac{2}{3}\varepsilon_{33}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22})n_3) \\
\delta u_2n_{21}((\frac{2}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{33})n_1+\varepsilon_{12}n_2+\varepsilon_{13}n_3) \\
\delta u_2n_{22}(\varepsilon_{21}n_1+(\frac{2}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{33})n_2+\varepsilon_{23}n_3) \\
\delta u_2n_{23}(\varepsilon_{31}n_1+\varepsilon_{32}n_2+(\frac{2}{3}\varepsilon_{33}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22})n_3) \\
\delta u_3n_{31}((\frac{2}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{33})n_1+\varepsilon_{12}n_2+\varepsilon_{13}n_3) \\
\delta u_3n_{32}(\varepsilon_{21}n_1+(\frac{2}{3}\varepsilon_{22}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{33})n_2+\varepsilon_{23}n_3) \\
\delta u_3n_{33}(\varepsilon_{31}n_1+\varepsilon_{32}n_2+(\frac{2}{3}\varepsilon_{33}-\frac{1}{3}\varepsilon_{11}-\frac{1}{3}\varepsilon_{22})n_3) \\
\end{array}
\right )
d\Gamma
$$
