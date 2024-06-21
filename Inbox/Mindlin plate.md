#Elasticity/Plate/Thick-plate 

# MIndlin 板的几何方程
考虑厚度 $h$ 的厚板 $\bar \Omega$，其位移 $\bar u_i, i=1,2,3$ 可以简化为关于 $x_3$ 的线性函数。可以用中性面位移 $u_\alpha$ 和转角 $\varphi_\alpha$, $\alpha=1,2$ 表示:
$$
\left \{
\begin{array}{l}
\bar{u}_{\alpha}(\boldsymbol{x}) = u_{\alpha}(x_1,x_2) - x_3 \varphi_{\alpha}(x_1,x_2) \\
\bar{u}_{3}(\boldsymbol{x}) = w(x_1,x_2)
\end{array}
\right .
,\quad \alpha = 1,2
$$
将该位移带入 [[❖ Elasticity#^605c91|kinematics relation]]，得到相应的应变:
$$
\left \{
\begin{split}
\epsilon_{\alpha \beta} &=\varepsilon_{\alpha\beta} + \kappa_{\alpha\beta} x_3 = \frac{1}{2}\left(u_{\alpha, \beta}+u_{\beta, \alpha}\right)-\frac{x_{3}}{2}\left(\varphi_{\alpha, \beta}+\varphi_{\beta, \alpha}\right) \\
\epsilon_{\alpha 3} &=\frac{1}{2}k\gamma_{\alpha} = \frac{1}{2}\left(w_{, \alpha}-\varphi_{\alpha}\right) \\
\epsilon_{33} &=0
\end{split}
\right .
$$
其中
$$
\varepsilon_{\alpha\beta} =\frac{1}{2}(u_{\alpha,\beta} + u_{\beta,\alpha})
$$
$$
\kappa_{\alpha\beta} = -\frac{1}{2}(\varphi_{\alpha,\beta} + \varphi_{\beta,\alpha})
$$
$$
\gamma_\alpha = w_{,\alpha} - \varphi_\alpha
$$
式中，$\kappa$ 为剪切修正系数，用于修正内能。$\varepsilon_{\alpha\beta}$, $\kappa_{\alpha\beta}$ 和 $\gamma_\alpha$ 分别为板的应变、曲率和剪切应变。与 [[❖ Kirchhoff-Love Plate|Kirchhoff-Love假设]] 不同， Uflyand-Mindlin 假设下的板剪切应变不可忽略，即 $\gamma_\alpha \ne 0$, $\varphi_\alpha \ne w_{,\alpha}$ 。
# 伽辽金弱形式
 [[❖ Elasticity#Galerkin formulation|弹性弱形式]] 的内力可以用厚板中性面的应力应变来重新表示:
$$
\begin{split}
\int_{\bar \Omega} \delta \epsilon_{ij} \sigma_{ij} d\Omega &=
\int_{\Omega}\int_{-\frac{h}{2}}^{\frac{h}{2}} \delta \epsilon_{\alpha\beta} \sigma_{\alpha\beta} + 2\delta \epsilon_{3 \alpha} \sigma_{3\alpha} dx_3 d\Omega \\
&=\int_{\Omega}\int_{-\frac{h}{2}}^{\frac{h}{2}} (\delta \varepsilon_{\alpha\beta} + \delta \kappa_{\alpha\beta} x_3) \sigma_{\alpha\beta} dx_3 d\Omega + \int_\Omega\int_{-\frac{h}{2}}^{\frac{h}{2}} k\delta \gamma_\alpha \sigma_{3\alpha} dx_3 d\Omega \\
&=\int_{\Omega}(\delta \varepsilon_{\alpha\beta}\underbrace{\int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{\alpha\beta} dx_3}_{N_{\alpha\beta}}
+ \delta \kappa_{\alpha\beta} \underbrace{\int_{-\frac{h}{2}}^{\frac{h}{2}} x_3 \sigma_{\alpha\beta} dx_3}_{M_{\alpha\beta}}) d\Omega 
+ \int_\Omega\delta \gamma_\alpha \underbrace{k\int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{3\alpha} dx_3}_{Q_\alpha} d\Omega\\
&= \int_\Omega \delta \varepsilon_{\alpha\beta} N_{\alpha\beta} + \delta \kappa_{\alpha\beta} M_{\alpha\beta} + \delta \gamma_\alpha Q_\alpha d\Omega
\end{split}
$$
式中 $N_{\alpha\beta}$, $M_{\alpha\beta}$ and $Q_\alpha$ 分别是平面内应力、力矩和剪切的结果。对于各向同性弹性材料，假设应力分量 $\sigma_{33}=0$:
$$
\left \{
\begin{split}
\sigma_{\alpha\beta} &= \frac{E}{1-\nu^2} (\nu\delta_{\alpha\beta} \epsilon_{\gamma\gamma} + (1-\nu) \epsilon_{\alpha\beta}) = D_{\alpha\beta\gamma\eta} \epsilon_{\alpha\beta} \\
\sigma_{\alpha 3} &=\frac{E}{2(1+\nu)} \gamma_\alpha
\end{split}
\right .
$$
式中 $D_{\alpha\beta\gamma\eta}$ 为四阶弹性张量的分量，并具有以下形式:
$$
D_{\alpha\beta\gamma\eta} = \frac{E}{1-\nu^2}(\nu \delta_{\alpha\beta}\delta_{\gamma\eta} +\frac{1}{2}(1-\nu)(\delta_{\alpha\gamma}\delta_{\beta\eta} + \delta_{\alpha\eta}\delta_{\beta\gamma}))
$$
应力结果可以使用平面内应变、曲率和剪切应变进一步表示为:
$$
N_{\alpha\beta} = \int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{\alpha\beta} dx_3 = h D_{\alpha\beta\gamma\eta} \varepsilon_{\gamma\eta}
$$
$$
M_{\alpha\beta} = \int_{-\frac{h}{2}}^{\frac{h}{2}} x_3 \sigma_{\alpha\beta} dx_3 = \frac{h^3}{12}D_{\alpha\beta\gamma\eta} \kappa_{\gamma\eta}
$$
$$
Q_\alpha = k\int_{-\frac{h}{2}}^{\frac{h}{2}} \sigma_{3\alpha} dx_3 = k\frac{Eh}{2(1+\nu)} \gamma_\alpha = kGh \gamma_\alpha
$$

此时，厚板的弱形式可以用分部积分法进行化简:
$$
\begin{split}
&\int_\Omega \delta \varepsilon_{\alpha\beta} N_{\alpha\beta} + \delta \kappa_{\alpha\beta} M_{\alpha\beta} + \delta \gamma_\alpha Q_\alpha d\Omega \\
=& \int_{\Gamma_N} \delta u_\alpha \bar T_\alpha d\Gamma - \int_{\Gamma_M} \delta \varphi_\alpha \bar M_{\alpha} d\Gamma + \int_{\Gamma_Q} \delta w \bar Q d\Gamma - \int_\Omega \delta w \bar q d\Omega \\
\Rightarrow& \int_{\Gamma_N} \delta u_\alpha (N_{\alpha\beta} n_\beta - \bar T_\alpha) d\Gamma
- \int_\Omega \delta u_\alpha (N_{\alpha\beta,\beta} + \bar b_\alpha) d\Omega \\
-& \int_{\Gamma_M} \delta \varphi_\alpha(M_{\alpha\beta} n_\beta - \bar M_\alpha) d\Gamma 
+ \int_\Omega \delta \varphi_\alpha(M_{\alpha\beta,\beta} - Q_\alpha)d\Omega \\
+& \int_{\Gamma_Q} \delta w (Q_\alpha n_\alpha - \bar Q) d\Gamma
- \int_\Omega \delta w (Q_{\alpha,\alpha} + \bar q_\alpha) d\Omega = 0
\end{split}
$$
从上述方程可以看出，强形式中关于平面内水平位移的部分与 [[❖ Elasticity#Plane strain and plane stress|平面应力问题]]的相同。所以，考虑挠度与转角部分的强形式如下: 
$$
\begin{cases}
M_{\alpha\beta,\beta} - Q_\alpha = 0 & \textrm{in}\; \Omega \\
Q_{\alpha,\alpha} + \bar q = 0 & \textrm{in}\; \Omega \\
Q_\alpha n_\alpha = \bar Q & \textrm{on}\; \Gamma_Q \\
M_{\alpha\beta} n_\beta = \bar M_\alpha & \textrm{on}\; \Gamma_M \\
\varphi_\alpha = \bar \varphi_\alpha & \textrm{on}\; \Gamma_\varphi \\
w = \bar w & \textrm{on}\; \Gamma_w \\
\end{cases}
$$

# 数值模拟
在数值模拟中，位移和转角可以用形函数和节点系数来近似:
$$
w^h(\boldsymbol x) = \sum_{I=1}^{n_p} N_I(\boldsymbol x) w_I, \quad
\varphi^h_\alpha(\boldsymbol x) = \sum_{I=1}^{n_p} N_I(\boldsymbol x) \varphi_{\alpha I}
$$
相应的近似应变可以重新表示为:
$$
\boldsymbol \kappa^h = 
\begin{Bmatrix}
\kappa^h_{11} \\ \kappa^h_{22} \\ 2\kappa^h_{12} 
\end{Bmatrix} = -\sum_{I=1}^{n_p}
\begin{bmatrix}
0 & N_{I,1} & 0 \\ 0 & 0 & N_{I,2} \\ 0 & N_{I,2} & N_{I,1}
\end{bmatrix}
\begin{Bmatrix}
w_I \\ \varphi_{1I} \\ \varphi_{2I}
\end{Bmatrix} = - \sum_{I=1}^{n_p} \boldsymbol B^b_I \boldsymbol d_I
$$
$$
\boldsymbol \gamma^h = 
\begin{Bmatrix}
\gamma^h_1 \\ \gamma^h_2
\end{Bmatrix} = \sum_{I=1}^{n_p}
\begin{bmatrix}
N_{I,1} & N_I & 0 \\
N_{I,2} & 0 & N_I
\end{bmatrix}
\begin{Bmatrix}
w_I \\ \varphi_{1I} \\ \varphi_{2I}
\end{Bmatrix} = \sum_{I=1}^{n_p} \boldsymbol B^s_I \boldsymbol d_I
$$
将离散应变代入弱形式，得到以下离散平衡方程:
$$
(\boldsymbol K^b + \boldsymbol K^s) \boldsymbol d = \boldsymbol f
$$
其中 $\boldsymbol K^b$ 和 $\boldsymbol K^s$ 为刚度矩阵并具有以下分量:
$$
\boldsymbol K^b_{IJ} = h \int_\Omega \boldsymbol B^{bT}_I \boldsymbol D \boldsymbol B^b_J d\Omega
$$
$$
\boldsymbol K^s_{IJ} = \frac{h^3}{12} \int_\Omega \boldsymbol B^{sT}_I \boldsymbol D \boldsymbol B^s_J d\Omega
$$
式中 $\boldsymbol D$ 为 [[❖ Elasticity#^91dd38|平面应力弹性矩阵]].
$\boldsymbol f$ 为力矢量，它的分量表达式如下: 
$$
\boldsymbol f_I = \int_{\Gamma_Q} N_I \bar{\boldsymbol Q} d\Gamma - \int_{\Gamma_M} N_I \bar{\boldsymbol M} d\Gamma + \int_\Omega N_I \bar{\boldsymbol q} d\Omega
$$
其中:
$$
\bar{\boldsymbol Q} = 
\begin{Bmatrix}
\bar Q \\ 0 \\ 0
\end{Bmatrix}, \quad
\bar{\boldsymbol M} =
\begin{Bmatrix}
0 \\ \bar M_1 \\ \bar M_2
\end{Bmatrix}, \quad
\bar{\boldsymbol q} =
\begin{Bmatrix}
\bar q \\ 0 \\ 0
\end{Bmatrix}
$$
# 混合离散方程
为了缓解由于板厚度减少引起的剪切自锁，引入对剪切合力 $Q_\alpha$ 的近似，近似值与位移和转角无关:
$$
Q^h_\alpha(\boldsymbol x) = \sum_{K=1}^{n_q} \Psi_K(\boldsymbol x) q_{\alpha K}
$$
相应的弱形式和离散平衡方程公式如下:
$$
\begin{align}
\int_\Omega \delta \kappa_{\alpha\beta} M_{\alpha\beta} d\Omega + \int_\Omega \delta \gamma_\alpha Q_\alpha d\Omega
&= \int_{\Gamma_N} \delta u_\alpha \bar T_\alpha d\Gamma - \int_{\Gamma_M} \delta \varphi_\alpha \bar M_{\alpha} d\Gamma + \int_{\Gamma_Q} \delta w \bar Q d\Gamma - \int_\Omega \delta w \bar q d\Omega \\
\int_\Omega \delta Q_\alpha \gamma_\alpha d\Omega -\frac{1}{kGh} \int_\Omega \delta Q_\alpha Q_\alpha d\Omega &= 0
\end{align}
$$
$$
\begin{bmatrix}
\boldsymbol K^b & \boldsymbol K^{wq} \\
\boldsymbol K^{wqT} & \boldsymbol K^{qq}
\end{bmatrix}
\begin{Bmatrix}
\boldsymbol d \\ \boldsymbol q
\end{Bmatrix}= 
\begin{Bmatrix}
\boldsymbol f \\ \boldsymbol 0
\end{Bmatrix}
$$
式中 $\boldsymbol K^{wq}$ 和 $\boldsymbol K^{qq}$ 的分量为:
$$
\boldsymbol K^{wq}_{IK} = \int_\Omega \boldsymbol B^{sT}_I \Psi_K d\Omega
$$
$$
\boldsymbol K^{qq}_{KL} = -\frac{1}{kGh} \int_\Omega \Psi_K \Psi_L \boldsymbol 1 d\Omega
$$
其中 $\boldsymbol 1$ 是二阶恒等张量。
# 自锁约束自由度

| $w$ 阶数 $p$ | $n_{dof}$ | $n_b$ | $n_s$ |
| ------- | ----- |----- | ----- |
| 1    | 9     |  7 | 2     |
| 2    | 18    | 12 | 6     |
| 3    | 30    | 18 | 12    |
| 4    | 45    | 25  | 20 |
| n    |  $\frac{3(p+1)(p+2)}{2}$|$\frac{(p+1)(p+6)}{2}$|  $p(p+1)$     |
# 数值算例
## 1.分片实验

  刚度矩阵必须通过分片实验，才能保证得出正确的结果。采用挠度为一次，转角为常数的厚板分片实验验证弯曲部分刚度矩阵 $\boldsymbol K^b$ 的正确性; 采用挠度为二次，转角为一次的厚板分片实验验证剪切部分刚度矩阵 $\boldsymbol K^s$ 和 $\boldsymbol K^{wq}$ 的正确性。分片实验考虑求解域为 $\Omega=(0,1)\otimes(0,1)$ 的正方形板，求解域的四边采用罚函数法施加边界条件。分片实验的精确解如下：
  $$
\left \{
\begin{array}{l} w(x,y)=x+y\\\varphi_1(x,y)=1\\\varphi_2(x,y)=1
\end{array}
\right .
\quad,\quad\left \{
\begin{array}{l} w(x,y)=x+y+\frac{x^2}{2}+xy+\frac{y^2}{2}\\\varphi_1(x,y)=x+y+1\\\varphi_2(x,y)=x+y+1
\end{array}
\right .$$ 
 分片实验由 64 个节点进行离散。   
![[SquarePlate_8_msh.png|400]]  
采用位移误差 $L_2-\text{Error}$ 进行分析:
$$
L_2-\text{Error}=\frac{\sqrt{\int_\Omega(w-w^h)^2d\Omega}}{\sqrt{\int_\Omega w^2d\Omega}}
$$
分片实验结果

|                |   |      $w$        |  $\varphi_1$       |    $\varphi_2$    |
|----------------|---|-----------------|------------------|------------------|
|$L_2-\text{Error}$|fem|$3.72\times10^{-16}$|$3.30\times10^{-15}$| $2.64\times10^{-15}$|
|$L_2-\text{Error}$|mix|$2.22\times10^{-16}$|$3.20\times10^{-15}$| $2.99\times10^{-15}$|
从表中结果可以看出，本方法通过了分片实验。
## 2. 简支方板问题
如图所示，简支方板中性面区域为 $\Omega=(0,1000)\otimes(0,1000)$, 此时 $\Omega$ 边长 $L=1000$ ，厚度$h=50、100、150、200、250$，材料系数分别为杨氏模量 $E=10.92$、泊松比 $\nu=0.3$ 板面分布纵向荷载 $F_z=1$，根据对称性截取左下角 $\frac{1}{4}$ 的方板进行分析，中心处位移的参考解如下表所示:  

| $h$   | 50   | 100   | 150   | 200   | 250   |
| ----- | ---- | ----- | ----- | ----- | ----- |
| $w_c$ | 4.11 | 4.268 | 4.532 | 4.902 | 5.377 |

![[Pasted image 20240618205658.png#pic_center]]   
如图采用均布的 $8\times8、16\times16、32\times32、64\times64$ 的四个疏密不同的节点进行离散。
![[Pasted image 20240618212456.png|315]] ![[Pasted image 20240618212742.png|310]]
![[Pasted image 20240618213216.png|310]] ![[Pasted image 20240618213341.png|310]]      图为简支方板问题分别在四个不同节点下得出的位移与参考解的关系。从图中可以明显看出，由于自锁现象随着厚度的减小传统有限元方法得出的位移精度明显减少，节点数增加位移精度有所提高。而采用有限元无网格混合离散方法得出的位移精度保持不变，可以消除自锁现象。  
![[Pasted image 20240619144610.png|318]] ![[Pasted image 20240619144727.png|317]]
![[Pasted image 20240619144838.png|318]] ![[Pasted image 20240619144910.png|317]]
## 3 .简支急性斜板问题
如图所示简支急性斜板，其中边长 $L=1000$ 厚度 $h=0.1、1.0、10$，材料系数分别为杨氏模量 $E=10.92$、泊松比 $\nu=0.3$ 板面分布纵向荷载 $F_z=1$，中心处位移的参考解如下表所示:  

| $h$   | 0.1    | 1.0    | 10     |
| ----- | ------ | ------ | ------ |
| $w_c$ | 0.4134 | 0.4248 | 0.5177 |
 ![[Pasted image 20240619175438.png]]
如图简支急性斜板求解域采用的 $52、190、701、2560$ 的四个疏密不同的节点进行离散。  
![[Pasted image 20240619164905.png|318]] ![[Pasted image 20240619165138.png|317]]
![[Pasted image 20240619165416.png|318]] ![[Pasted image 20240619165651.png|317]]
图为简支急性斜板问题分别在四个不同节点下得出的位移与参考解的关系。从图中可以明显看出，由于自锁现象随着厚度的减小传统有限元方法得出的位移精度明显减少，节点数增加位移精度有所提高。而采用有限元无网格混合离散方法得出的位移精度保持不变，可以消除自锁现象。  
![[Pasted image 20240619171423.png|316]] ![[Pasted image 20240619174059.png|319]]
![[Pasted image 20240619174742.png|318]] ![[Pasted image 20240619174815.png|317]]
## 4 .四边固支方板问题
如图所示，简固支方板中性面区域为 $\Omega=(0,1)\otimes(0,1)$, 此时 $\Omega$ 边长 $L=1$ ，厚度 $h=0.1、0.01、0.001、0.0001、0.00001$，材料系数分别为杨氏模量 $E=10.92\times10^6$、泊松比 $\nu=0.3$ 板面分布如图所示纵向荷载及精确解：
$$
\begin{split}
F(x,y)=&\frac{Eh^3}{12(1-\nu^2)}[12y(y-1)(5x^2-5x+1)(2y^2(y-1)^2+x(x-1)(5y^2-5y+1))\\&+12x(x-1)(5y^2-5y+1)(2x^2(x-1)^2+y(y-1)(5x^2-5x+1))]
\end{split}
$$
$$
\begin{split}
w(x,y)=&\frac{1}{3}x^3(x-3)^3y^3(y-1)^3-\frac{2h^2}{5(1-\nu)}
(y^3(y-1)^3x(x-1)(5x^2-5x+1)
\\&+x^3(x-1)^3y(y-1))(5y^2-5y+1)
\end{split}
$$ 
![[Pasted image 20240619175220.png]]
如图固支方板求解域采用均布的 $8\times8、16\times16、32\times32、64\times64$ 的四个疏密不同的节点进行离散。  
![[Pasted image 20240618212456.png|315]] ![[Pasted image 20240618212742.png|310]]
![[Pasted image 20240618213216.png|310]] ![[Pasted image 20240618213341.png|310]]      
如图为固支方板问题，在厚度不断减少时得有限元方法和有限元无网格混合离散方法得位移误差对比图，以厚度 $h=1$ 时有限元方法得位移误差表示无自锁时的位移误差。从图中可以明显看出，当厚度减小时，有限元方法位移误差很大，混合离散方法 $(1:1)$ 在厚度很薄时位移误差也逐渐增大。  
![[Pasted image 20240620170343.png|500]]  
如图使用有限元无网格混合离散方法，在厚度为 $h=0.00001$ 通过改变节点的数量来改变弯曲和剪切的比值 $(n_b:n_p)$ 寻找最优的约束比例。分别取 $n_b=400、1600、3600$，改变 $n^s$ 的节点数量求出位移误差。  
![[Pasted image 20240620155045.png|310]] ![[Pasted image 20240620155248.png|325]]
![[Pasted image 20240620155330.png|310]]
## 5. 简支圆板问题
如图所示简支圆板，其中半径 $R=5$ 厚度 $h=0.1、1.0、5$，材料系数分别为杨氏模量 $E=10.92$、泊松比 $\nu=0.3$ 板面分布纵向荷载 $F_z=1$，根据对称性截取 $\frac{1}{4}$ 圆板进行分析，中心处位移的精确解解如下表所示:  

| $h$   | 0.1    | 1.0    | 2.5     |
| ----- | ------ | ------ | ------ |
| $w_e$ | 39831 | 49.299 | 3.262 |
![[Pasted image 20240620161950.png]]
如图简支圆板求解域采用的 $37、169、721、2977$ 的四个疏密不同的节点进行离散。  
![[Pasted image 20240620164637.png|310]] ![[Pasted image 20240620164549.png|310]]
![[Pasted image 20240620164715.png|310]] ![[Pasted image 20240620164749.png|310]]
如图为简支圆板问题，在厚度不同时得有限元方法和有限元无网格混合离散方法得位移误差对比图，从图中可以看出，混合离散方法位移误差始终优于有限元法，且在厚度 $h=0.1$ 时无自锁现象。  
![[Pasted image 20240620171426.png|310]] ![[Pasted image 20240620171552.png|320]]
![[Pasted image 20240620171731.png|310]]  
如图使用有限元无网格混合离散方法，在厚度为 $h=0.1$ 通过改变节点的数量来改变弯曲和剪切的比值 $(n_b:n_p)$ 寻找最优的约束比例。分别取 $n_b=217、1141、2611$，改变 $n^s$ 的节点数量求出位移误差。  
![[Mindlin plate-2024-06-21.png|310]] ![[Pasted image 20240621094920.png|310]]
![[Pasted image 20240621094940.png|310]]