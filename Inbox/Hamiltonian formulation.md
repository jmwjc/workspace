#Group/王崇志 
## Hamiltonian  formula derivation

在给定初始边界条件 $\delta u(t_1) = 0$ 、$u (t_0) = u_0$ 的前提下，验证哈密顿法则在时间和空间二维下计算动力系统的准确性，以下是哈密顿法则F1算例的推导。
一根长为$L$的杆，在空间上关于0-L的势能积分表达式：
$$
U = \int_{0}^{L} \frac{1}{2} EA u_{,x}^2 dx
$$
在空间上关于0-L的动能积分表达式：
$$
T = \int_{0}^{L} \frac{1}{2} \rho A \dot u^2 dx
$$
其中，$u$为势能，$E$为杨氏模量，$A$为平面面积，$u_{,x}$为应变，$T$为动能，$ρ$为密度，$\dot u$为速度。
拉格朗日函数：
$$
R = T-U
$$
引入时间范畴，在时间上关于$t_0 - t_1$进行积分：
$$
\Phi = \int_{t_0}^{t_1} R dt = \int_{t_0}^{t_1} \int_{0}^{L} (\frac{1}{2} \rho A \dot u^2 - \frac{1}{2} EA u_{,x}^2) dx dt
$$
对上式进行变分，得到弱形式：
$$
\delta \Phi = \int_{t_0}^{t_1} \int_{0}^{L} \delta \dot u \rho A \dot u - \delta u_{,x} EA u_{,x} dx dt = 0
$$
外力功在时间和空间上的表达式：
$$
W = \int_{t_0}^{t_1} \int_{0}^{L}ub dx  +uP \vert_{x=L} dt
$$
其中，b是体力，P是外力。
引入哈密顿法则F1算例：
$$
\delta \int_{t_0}^{t_1} R dt - \left . \frac{\partial R}{\partial \dot u} \delta u \right \vert_{t_0}^{t_1} - \int_{t_0}^{t_1} \delta W dt = 0
$$
对上式进行变分，得到弱形式：
$$
 \int_{t_0}^{t_1} \int_{0}^{L} (\delta \dot u \rho A \dot u - \delta u_{,x} EA u_{,x}) dx dt = (\int_{0}^{L} \rho A \dot udx \delta u)t \vert_{t_0}^{t_1} + \int_{t_0}^{t_1} (\int_{0}^{L} \delta ub dx  + \delta uP \vert_{x=L} )dt
$$
分别对$u, \dot u , u_{,x}$进行近似：
$$
u^h(x,t) = \sum_{I=1}^{n_p} N_I(x,t) d_I
$$
$$
\dot u^h = \sum_{I=1}^{n_p} N_{I,t} d_I
$$
$$
u_{,x}^h = \sum_{I=1}^{n_p} N_{I,x} d_I
$$
得到刚度矩阵$K_{IJ}$为：
$$
K_{IJ} = \int_{t_0}^{t_1} \int_{0}^{L} (N_{I,t} \rho A N_{J,t} - N_{I,x}EAN_{J,x})dxdt
$$
得到力矩阵$f_I$为：
$$
f_{I} = \int_{0}^{L} \rho A N_{I,t} N_I dx \vert_{t_0}^{t_1} + \int_{t_0}^{t_1} (\int_{0}^{L} N_{I} b dx + N_{I} P \vert_{x=L})dt
$$
将初始边界条件$\delta u (t_1) = 0$带入弱形式，引入动量表达式:
$$
C = \rho A \dot u(t_0)
$$
最终得到力矩阵$f_I$为：
$$
f_{I} = - \int_{0}^{L} N_I C dx \vert_{t = t_0}  + \int_{t_0}^{t_1} (\int_{0}^{L} N_{I} b dx + N_{I} P \vert_{x=L})dt
$$
带入控制方程 $Kd = f$ 得到精确解

## Euler iterative formula derivation

Explicit_Euler
$$
\left \{
\begin{split}
\ddot {\boldsymbol d}_n &= \boldsymbol M^{-1} (\boldsymbol f_n - \boldsymbol K \boldsymbol d_n) \\
\dot {\boldsymbol d}_{n+1} &= \dot {\boldsymbol d}_n + \Delta t \ddot {\boldsymbol d}_n \\
\boldsymbol d_{n+1} &= \boldsymbol d_n + \Delta t \dot {\boldsymbol d}_n
\end{split}
\right . 
$$Semi-implicit_Euler
$$
\left \{
\begin{split}
\ddot {\boldsymbol d}_{n+1} &= \boldsymbol M^{-1} (\boldsymbol f_{n+1} - \boldsymbol K \boldsymbol d_n) \\
\dot {\boldsymbol d}_{n+1} &= \dot {\boldsymbol d}_n + \Delta t \ddot {\boldsymbol d}_{n+1} \\
\boldsymbol d_{n+1} &= \boldsymbol d_n + \Delta t \dot {\boldsymbol d}_{n+1}
\end{split}
\right . 
$$
mplicit_Euler
$$
\left \{
\begin{split}
\ddot {\boldsymbol d}_{n+1} &= \boldsymbol M^{-1} (\boldsymbol f_{n+1} - \boldsymbol K \boldsymbol d_n) \\
\dot {\boldsymbol d}_{n+1} &= \dot {\boldsymbol d}_n + \Delta t \ddot {\boldsymbol d}_{n+1} \\
\boldsymbol d_{n+1} &= \frac{\boldsymbol M}{\boldsymbol M + \Delta t^2\boldsymbol K}(\boldsymbol d_n + \Delta t \dot {\boldsymbol d}_n + \frac{\Delta t^2}{\boldsymbol M}\boldsymbol f_{n+1})
\end{split}
\right . 
$$

## Figure out the data

exact_solution
![[exact_solution.png|500]]


hmd_2d_n=10
![[hmd_2d_n10.png|500]]


hmd_2d_n=10_error
![[hmd_2d_n10_error.png|500]]

hmd_2d_n=20
![[hmd_2d_n20.png|500]]


hmd_2d_n=20_error
![[hmd_2d_n20_error 1.png|500]]


semi_implicit_Euler
![[semi_implicit_Euler.png|500]]


Semi-implicit_Euler_error
![[Semi-implicit_Euler_error.png|500]]


non-uniform_10
![[non-uniform_10.png|500]]


non-uniform_20
![[non-uniform_20.png|500]]


Error-convergence-rate
![[Error-convergence-rate.png|500]]