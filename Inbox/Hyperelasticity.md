---
icon: OcInfinity16
---

#Elasticity #Incompressible #Hyperelasticity 

# Saint Venant-Kirchhoff model
$$
W(\boldsymbol E)=\frac{\lambda}{2}\mathrm{tr}^2(\boldsymbol E) + 2\mu \boldsymbol E : \boldsymbol E = \frac{\lambda}{2} (E_{KK})^2 + \mu E_{IJ} E_{JI}
$$
$$
\begin{split}
S_{IJ} &= \frac{\partial W}{\partial E_{IJ}} \\
&= \lambda E_{KK} \delta_{IJ} + 2\mu E_{IJ} \\
&= (\lambda+\frac{2}{3}\mu) E_{KK} \delta_{IJ} + 2\mu (E_{IJ}-\frac{1}{3}E_{KK}\delta_{IJ}) \\
\end{split}
$$
where $\boldsymbol E$ is [[Nonlinear Elasticity#Strain measures|right Green-Lagrangian strain]].

# Neo-hookean model
## Compressible neo-hookean model 1
One of the widely used energy density of neo-hookean material in 3D is given by
$$
W = \frac{1}{2}\mu(I_1-3) - \mu \ln J + \frac{1}{2}\lambda \Theta(J)^2
$$
where $\lambda$ and $\mu$ are Lamé constants. $I_1 = \mathrm{tr} (\boldsymbol C)$ is the first invariant of right Cauchy-Green tensor, and $J=\det \boldsymbol F = \sqrt{I_3} = \sqrt{\det \boldsymbol C}$ is the determine of deformation gradient. $\Theta$ is a smooth function and should have the following property
1. $\Theta(J)=0$ if and only if $J=1$.
2. $\Theta'(1)\ne0$.

such as $\Theta(J) = J-1$, $\Theta(J) = \ln(J)$.

The PK2 stress can be attained by
$$
\begin{split}
S_{IJ} &= 2 \frac{\partial W}{\partial C_{IJ}} \\
&= 2 (\frac{\partial W}{\partial I_1}\frac{\partial I_1}{\partial C_{IJ}}+\frac{\partial W}{\partial J}\frac{\partial J}{\partial C_{IJ}}) \\
&= \mu\delta_{IJ}+2(\lambda\Theta\Theta'-\mu\frac{1}{J})\frac{1}{2}JC_{IJ}^{-1} \\
&= \mu\delta_{IJ}+(\lambda J\Theta\Theta'-\mu)C_{IJ}^{-1} \\
\end{split}
$$

For $\Theta(J) = J-1$, the energy density functional has the form that
$$
W(\boldsymbol E) = \frac{1}{2}\mu(I_1-3) - \mu \ln J + \frac{1}{2}\lambda (J-1)^2
$$
the corresponding PK2 stress can be evaluated by
$$
\begin{split}
S_{IJ} &= 2\frac{\partial W}{\partial C_{IJ}} \\
&= 2(\frac{\partial W}{\partial I_1}\frac{\partial I_1}{\partial C_{IJ}} + \frac{\partial W}{\partial J }\frac{\partial J}{\partial C_{IJ}}) \\
&= \mu\delta_{IJ} + 2(\lambda(J-1)-\mu \frac{1}{J}) \frac{1}{2}JC_{IJ}^{-1} \\
&= \lambda J(J-1) C_{IJ}^{-1} + \mu (\delta_{IJ}-C_{IJ}^{-1}) \\
\end{split}
$$

In numerical formulation, the linearization of PK2 stress should be carried out in iteration procedure
$$
\Delta \boldsymbol S = \boldsymbol C^{SE} : \Delta \boldsymbol E, \quad C_{IJKL}^{SE} = \frac{\partial^2 W}{\partial E_{IJ}\partial E_{KL}} = 4\frac{\partial^2 W}{\partial C_{IJ}\partial C_{KL}} = 2 \frac{\partial S_{IJ}}{\partial C_{Kl}}
$$
where $\boldsymbol C^{SE}$ is the fourth order elasticity tensor. To get the explicit form of $\boldsymbol C^{SE}$, the derivatives of inverse right Cauchy-Green tensor should firstly be derived as
$$
\begin{gather}
\begin{split}
\frac{\partial(C_{IM}^{-1}C_{MN})}{\partial C_{KL}} &= \frac{\partial (C_{IM}^{-1}\frac{1}{2}(C_{MN}+C_{NM}))}{\partial C_{KL}} \\
&= \frac{1}{2}(\frac{\partial C_{IM}^{-1}}{\partial C_{KL}}C_{MN} + C_{IM}^{-1}\delta_{KM}\delta_{LN}+\frac{\partial C_{IM}^{-1}}{\partial C_{KL}}C_{NM} + C_{IM}^{-1}\delta_{KN}\delta_{LM}) \\
&= \frac{\partial C_{IM}^{-1}}{\partial C_{KL}}C_{MN} + C_{IM}^{-1}\frac{1}{2}(\delta_{KM}\delta_{LN} + \delta_{KN}\delta_{LM}) \\
&= 0 \\
\end{split} \\
\Rightarrow
\frac{\partial C_{IM}^{-1}}{\partial C_{KL}}C_{MN}C_{NJ}^{-1} + C_{NJ}^{-1}C_{IM}^{-1}\frac{1}{2}(\delta_{KM}\delta_{LN} + \delta_{KN}\delta_{LM}) = \\
\frac{\partial C_{IJ}^{-1}}{\partial C_{KL}} + \frac{1}{2}(C_{LJ}^{-1}C_{IK}^{-1}+C_{KJ}^{-1}C_{IL}^{-1}) = 0\\
\Rightarrow
\frac{\partial C_{IJ}^{-1}}{\partial C_{KL}} = -\frac{1}{2}(C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
\end{gather}
$$
Consequently, the fourth order elasticity tensor can be got by
$$
\begin{split}
C_{IJKL} &= 2\frac{\partial S_{IJ}}{\partial C_{KL}} \\
&= 2\frac{\partial (\lambda J(J-1) C_{IJ}^{-1} + \mu (\delta_{IJ}-C_{IJ}^{-1}))}{\partial C_{KL}} \\
&= 2\lambda((2J-1)\frac{1}{2}JC_{KL}^{-1}\;C_{IJ}^{-1} - J(J-1)\frac{1}{2}(C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1})) \\
&+ \mu (C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
&= \lambda J(2J-1) C_{IJ}^{-1}C_{KL}^{-1} + (\mu-\lambda J(J-1)) (C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
\end{split}
$$

For $\Theta(J) = J-1$, the energy density functional has the form that
$$
W(\boldsymbol E) = \frac{1}{2}\mu(I_1-3) - \mu \ln J + \frac{1}{2}\lambda (\ln J)^2
$$
the corresponding PK2 stress can be evaluated by
$$
\begin{split}
S_{IJ} &= 2\frac{\partial W}{\partial C_{IJ}} \\
&= 2(\frac{\partial W}{\partial I_1}\frac{\partial I_1}{\partial C_{IJ}} + \frac{\partial W}{\partial J }\frac{\partial J}{\partial C_{IJ}}) \\
&= \mu\delta_{IJ} + 2(\lambda \ln J -\mu)\frac{1}{J} \frac{1}{2}JC_{IJ}^{-1} \\
&= \lambda \ln J C_{IJ}^{-1} + \mu (\delta_{IJ}-C_{IJ}^{-1}) \\
\end{split}
$$
and the fourth order elasticity tensor has the following form
$$
\begin{split}
C_{IJKL} &= 2\frac{\partial S_{IJ}}{\partial C_{KL}} \\
&= 2\frac{\partial (\lambda \ln J C_{IJ}^{-1} + \mu (\delta_{IJ}-C_{IJ}^{-1}))}{\partial C_{KL}} \\
&= 2\lambda(\frac{1}{J}\frac{1}{2}JC_{KL}^{-1}\;C_{IJ}^{-1} - \ln J \frac{1}{2}(C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1})) \\
&+ \mu (C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
&= \lambda C_{IJ}^{-1}C_{KL}^{-1} + (\mu-\lambda \ln J) (C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
\end{split}
$$

## Incompressible neo-hookean model 1
Introducing the pressure $p=\lambda \Theta(J)$, the energy density functional can be rewritten as
$$
W(\boldsymbol E,p) = \frac{1}{2}\mu(I_1-3) - \mu \ln J + p\Theta(J)-\frac{1}{2\lambda} p^2
$$
for an incompressible material, $\lambda \rightarrow \infty$ will leads to $J\rightarrow 1$. The PK2 stress can be computed as
$$
\begin{split}
\bar S_{IJ} &= 2\frac{\partial W}{\partial C_{IJ}} \\
&= \mu\delta_{IJ}+(\lambda J\Theta\Theta'-\mu)C_{IJ}^{-1} \\
&= \mu(\delta_{IJ}-C_{IJ}^{-1})+JC_{IJ}^{-1}\Theta'p \\
\end{split}
$$

## Compressible neo-hookean model 2
**potential energy density**
$$
W = \frac{1}{2}\mu(J^{-\frac{2}{3}}I_1-3) + \frac{1}{2}K(\frac{1}{2}(J^2-1)-\ln J)
$$
**PK2 stress**
$$
\begin{split}
S_{IJ} &= 2 \frac{\partial W}{\partial C_{IJ}} \\
&= 2(\frac{\partial W}{\partial (J^{-\frac{2}{3}}I_1)}\frac{\partial (J^{-\frac{2}{3}}I_1)}{\partial C_{IJ}}+\frac{\partial W}{\partial J}\frac{\partial J}{\partial C_{IJ}}) \\
&= \mu J^{-\frac{2}{3}}(\delta_{IJ}-\frac{1}{3}I_1C_{JI}^{-1}) + K (J - \frac{1}{J}) \frac{1}{2} J C_{JI}^{-1} \\
&= \mu J^{-\frac{2}{3}}(\delta_{IJ}-\frac{1}{3}I_1C_{JI}^{-1}) + \frac{1}{2} K (J^2 - 1) C_{JI}^{-1} \\
\end{split}
$$
$$
\frac{\partial J}{\partial C_{IJ}} = \frac{\partial \sqrt{\det \boldsymbol C}}{\partial C_{IJ}} = \frac{1}{2\sqrt{\det{\boldsymbol C}}} \frac{\partial \det \boldsymbol C}{\partial C_{IJ}} = \frac{1}{2}J C_{JI}^{-1}
$$
$$
\begin{split}
\frac{\partial (J^{-\frac{2}{3}}I_1)}{\partial C_{IJ}} &= -\frac{2}{3}J^{-\frac{5}{3}} I_1 \frac{\partial J}{\partial C_{IJ}} + J^{-\frac{2}{3}} \frac{\partial I_1}{\partial C_{IJ}} \\
&= -\frac{1}{3} J^{-\frac{2}{3}} I_1 C_{JI}^{-1} + J^{-\frac{2}{3}} \delta_{IJ} \\
&= J^{-\frac{2}{3}}(\delta_{IJ}-\frac{1}{3}I_1C_{JI}^{-1})
\end{split}
$$
**elasticity tensor**
$$
\begin{split}
C_{IJKL} &= 2\frac{\partial S_{IJ}}{\partial C_{KL}} \\
&= 2(\frac{\partial S_{IJ}}{\partial J} \frac{\partial J}{\partial C_{KL}} + \frac{\partial S_{IJ}}{\partial (J^{-\frac{2}{3}}I_1)}\frac{\partial (J^{-\frac{2}{3}}I_1)}{\partial C_{KL}} + \frac{\partial S_{IJ}}{\partial C_{MN}^{-1}}\frac{\partial C_{MN}^{-1}}{\partial C_{KL}}) \\
&= (-\frac{2}{3}\mu J^{-\frac{5}{3}}\delta_{IJ} + KJC_{JI}^{-1})JC_{LK}^{-1} \\
&- \frac{2}{3}\mu C_{JI}^{-1} J^{-\frac{2}{3}}(\delta_{KL}-\frac{1}{3}I_1 C_{LK}^{-1}) \\
&- (-\frac{1}{3}\mu J^{-\frac{2}{3}} I_1 + \frac{1}{2}K(J^2-1)) (C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
&= (-\frac{2}{3} \delta_{IJ}C_{KL}^{-1} - \frac{1}{3} C_{IJ}^{-1}\delta_{KL}) J^{-\frac{2}{3}} \mu \\
&+ (J^2K-\frac{1}{9}J^{-\frac{2}{3}}I_1 \mu) C_{IJ}^{-1}C_{KL}^{-1} \\
&+ (\frac{1}{3}\mu J^{-\frac{2}{3}} I_1 - \frac{1}{2}K(J^2-1)) (C_{IK}^{-1}C_{JL}^{-1}+C_{IL}^{-1}C_{JK}^{-1}) \\
\end{split}
$$
