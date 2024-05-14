---
icon: OcInfinity16
---

#Formulation/PhaseField
# Phase field model
Phase field model(PFM) firstly is constructed for tracking the phase transformation of some physical phenomenon, or finding the boundaries for graphs. This ability of PFM will thank to $\Gamma$ convergence performed in PFM. We consider the energy of second order PFM as follow:
$$
\mathcal{D} = \int_\Omega k (\frac{(1-v)^2}{4l} + l \vert \nabla v \vert ^2) d\Omega
$$
and the corresponding profile in 1D is given by:
$$
v = 1 - e^{-\frac{\vert x-x_c \vert}{2l}}
$$
where $x_c$ is a constant, and this will be the location of the crack in PFM fracture model. We can check this result by substituting Eq.$\ref{profile}$ into Eq.$\ref{pfmenergy}$, yields:
$$
\begin{split}
\mathcal{D} &= \int_\Omega k(\frac{e^{-\frac{\vert x-x_c \vert}{l}}}{4l} + l\vert \frac{e^{-\frac{\vert x-x_c \vert}{2l}}}{2l}\vert ^2)d\Omega \\
&= \int_\Omega k(\frac{1}{4l}e^{-\frac{\vert x-x_c \vert}{l}} + \frac{1}{4l}e^{-\frac{\vert x-x_c \vert}{l}})d\Omega \\
&= \int_\Omega k \frac{1}{2l}e^{-\frac{\vert x-x_c \vert}{l}}d\Omega \\
&= k
\end{split}
$$
# PFM modeling fracture
Consider a field $\Omega$ with a crack $\Gamma^c$, the loss of the energy caused by crack, namely surface energy functional of crack $\mathcal{D}$, can be integrated along with the crack:
$$
\mathcal{D} = \int_{\Gamma^c} k d\Gamma = k \Gamma^c
$$
where $k$ is the critical energy release rate. And the crack $\Gamma^c$ can depicted by PFM as:
$$
\Gamma^c = \int_\Omega \gamma d\Omega = \int_\Omega \frac{(1-v)^2}{4l} + l \vert \nabla v \vert ^2 d\Omega
$$
take Eq.$\ref{gamma}$ in to Eq.$\ref{crack}$:
$$
\mathcal{D}(v) = k\int_\Omega \frac{(1-v)^2}{4l} + l \vert \nabla v \vert ^2 d\Omega
$$
so we reconsider the variation functional energy $\Pi$:
$$
\Pi(\boldsymbol{u},v) = \int_\Omega \psi(\boldsymbol{u},v) d\Omega + \mathcal{D}(v) + \mathcal{F}(\boldsymbol{u})
$$
# Tensile-compressive splitting model
$$
\psi(\boldsymbol{\varepsilon},v) = g(v) \psi_{0}^{+}(\boldsymbol{\varepsilon}) + \psi_{0}^{-}(\boldsymbol{\varepsilon})
$$

$$
\psi^{\pm}_{0}(\boldsymbol{\varepsilon}) = \frac{1}{2}\lambda \langle \pm \mathrm{tr}(\boldsymbol{\varepsilon}) \rangle ^{2} + \mu \boldsymbol{\varepsilon}^{\pm}:\boldsymbol{\varepsilon}^{\pm}
$$

where $\langle \cdot \rangle$ is the Macaulay bracket defined as $\langle x \rangle = \frac{\vert x \vert + x}{2}$. The tensile and compressive parts of strain tensor $\boldsymbol{\varepsilon}$, denoted by $\boldsymbol{\varepsilon}^{+}$ and $\boldsymbol{\varepsilon}^{-}$, are given by spectral decomposition of strain tensor:

$$
\boldsymbol{\varepsilon}^{+} = \sum_{\alpha = 1}^{3} \langle \varepsilon_{\alpha} \rangle \boldsymbol{e}_{\alpha} \otimes \boldsymbol{e}_{\alpha}, \quad
\boldsymbol{\varepsilon}^{-} = \sum_{\alpha = 1}^{3} - \langle -\varepsilon_{\alpha} \rangle \boldsymbol{e}_{\alpha} \otimes \boldsymbol{e}_{\alpha}
$$

# Stress decomposition in frictional interfaces
Consider the friction in damaged region, the stress tensor is interpolated by bulk stress, $\boldsymbol{\sigma}_{\text{bulk}}$, and interface stress, $\boldsymbol{\sigma}_{\text{interface}}$:
$$
\boldsymbol{\sigma} = g(v) \boldsymbol{\sigma}_{\text{bulk}} + (1-g(v))\boldsymbol{\sigma_{\text{interface}}}
$$

$$
\dot{\boldsymbol{\sigma}}_{\text{bulk}} = \boldsymbol{C}:\dot{\boldsymbol{\varepsilon}}
$$

We define the contact normal strain, $\varepsilon_{nn}$:
$$
\varepsilon_{nn} = \boldsymbol{\varepsilon}:(\boldsymbol{n}\otimes \boldsymbol{n})
$$
For the strain-softening material, the stress in interface region is evaluated by:
$$
\dot{\boldsymbol{\sigma}}_{\text{interface}} = \boldsymbol{C}:(\dot{\boldsymbol{\varepsilon}} - \dot{\boldsymbol{\varepsilon}}^{p})
$$
Assume that
$$
\dot{\boldsymbol{\varepsilon}}^{p} = \gamma \boldsymbol{r}(\boldsymbol{\sigma})
$$
The yield function is given by:
$$
f(\boldsymbol{\sigma}_{\text{interface}}):= \vert \tau \vert - \tau_{Y} \le 0
$$
where
$$
\tau:= \frac{1}{2}\boldsymbol{\sigma}:\boldsymbol{\alpha}, \quad \boldsymbol{\alpha} = \boldsymbol{m} \otimes \boldsymbol{n} + \boldsymbol{n} \otimes \boldsymbol{m}
$$
$$
\tau_{Y} = - \mu \sigma_{nn}, \quad \sigma_{nn} = \boldsymbol{\sigma}:\boldsymbol{\beta},\quad \boldsymbol{\beta} = \boldsymbol{n}\otimes \boldsymbol{n}
$$
Kuhn-Tucker conditions:
$$
\text{if} f(\boldsymbol{\sigma}) = 0\; \text{and} \; \gamma \ne 0, \quad
\gamma \dot{f} = 0
$$

$$
\begin{align}
    \dot{f} &= \frac{\partial f}{\partial \boldsymbol{\sigma}}: \dot{\boldsymbol{\sigma}} \\
      &= \frac{\partial f}{\partial \boldsymbol{\sigma}}: \boldsymbol{C}:(\dot{\boldsymbol{\varepsilon}} - \dot{\boldsymbol{\varepsilon}}^{p}) \\
      &= \frac{\partial f}{\partial \boldsymbol{\sigma}}: \boldsymbol{C}:(\dot{\boldsymbol{\varepsilon}} - \gamma \boldsymbol{r}) \\
      &= 0
\end{align}
$$
$$
\gamma = \frac{\partial_{\boldsymbol{\sigma}} f:\boldsymbol{C}:\dot{\boldsymbol{\varepsilon}}}{\partial_{\boldsymbol{\sigma}} f:\boldsymbol{C}:\boldsymbol{r}}
$$
$$
\begin{align}
    \partial_{\boldsymbol{\sigma}}f &= \frac{\partial (\vert \tau \vert - \tau_{Y})}{\partial \boldsymbol{\sigma}} \\
           &= \frac{\partial (\vert \frac{1}{2}\boldsymbol{\sigma}:\boldsymbol{\alpha} \vert + \mu \boldsymbol{\sigma}:\boldsymbol{\beta})}{\partial \boldsymbol{\sigma}} \\
           &= \frac{1}{2}\text{sign}(\tau)\boldsymbol{\alpha} + \mu \boldsymbol{\beta}
\end{align}
$$
$$
\begin{align}
    \dot{\boldsymbol{\sigma}} &= \boldsymbol{C}:(\dot{\boldsymbol{\varepsilon}}-\dot{\boldsymbol{\varepsilon}}^{p}) \\
            &= \boldsymbol{C}:(\dot{\boldsymbol{\varepsilon}}-\gamma \boldsymbol{r}) \\
            &= (\boldsymbol{C} - \frac{\boldsymbol{C}:\boldsymbol{r}\otimes\boldsymbol{C}:\partial_{\boldsymbol{\sigma}} f}{\partial_{\boldsymbol{\sigma}} f:\boldsymbol{C}:\boldsymbol{r}}):\dot{\boldsymbol{\varepsilon}}
\end{align}
$$
Tangent elastoplastic moduli tensor
$$
\boldsymbol{C}^{\text{ep}} = \left \{
\begin{array}{l}
    \boldsymbol{C} & \text{if} \; \gamma = 0 \\
    \boldsymbol{C} - \frac{\boldsymbol{C}:\boldsymbol{r}\otimes\boldsymbol{C}:\partial_{\boldsymbol{\sigma}} f}{\partial_{\boldsymbol{\sigma}} f:\boldsymbol{C}:\boldsymbol{r}} & \text{if} \; \gamma > 0
    
\end{array}
\right .
$$
Associative case
$$
\boldsymbol{r} = \partial_{\boldsymbol{\sigma}}f
$$
$$
\boldsymbol{r}:\frac{\boldsymbol{C}:\boldsymbol{r}}{\boldsymbol{r}:\boldsymbol{C}:\boldsymbol{r}},\quad \boldsymbol{r}:\mathrm{sign}(\tau)\boldsymbol{\alpha} = 1 \Rightarrow \frac{\boldsymbol{C}:\boldsymbol{r}}{\boldsymbol{r}:\boldsymbol{C}:\boldsymbol{r}} = \mathrm{sign}(\tau)\boldsymbol{\alpha}
$$
$$
\boldsymbol{C}^{\text{ep}} = \left \{
\begin{array}{l}
    \boldsymbol{C} & \text{if} \; \gamma = 0 \\
    \boldsymbol{C} - \mathrm{sign}(\tau)\boldsymbol{\alpha}\otimes\boldsymbol{C}:\boldsymbol{r} & \text{if} \; \gamma > 0
    
\end{array}
\right .
$$
$$
\dot{\boldsymbol{\sigma}}_{\text{interface}} = \left \{
    \begin{array}{l}
    \boldsymbol{0} & \text{if open}(\varepsilon_{nn}>0) \\
    \dot{\boldsymbol{\sigma}}_{\text{bulk}} & \text{if stick} (\varepsilon_{nn}\le 0,\; f<0)\\
    \dot{\boldsymbol{\sigma}}_{\text{friction}} + \dot{\boldsymbol{\sigma}}_{\text{no-penetration}} & \text{if slip} (\varepsilon_{nn}\le0,\;f=0)
    \end{array}
\right .
$$
$$
\boldsymbol{\sigma} = \left \{
    \begin{array}{l}
    g(v)\boldsymbol{\sigma}_{\text{bulk}} & \text{if open}(\varepsilon_{nn}>0) \\
    \boldsymbol{\sigma}_{\text{bulk}} & \text{if stick} (\varepsilon_{nn}\le 0,\; f<0)\\
    \boldsymbol{\sigma}_{\text{bulk}} - (1-g(v))\tau_{\text{bulk}}\boldsymbol{\alpha} + (1-g(v))\tau_{r}\boldsymbol{\alpha} & \text{if slip} (\varepsilon_{nn}\le0,\;f=0)
    \end{array}
\right .
$$
where
$$
\tau_{\text{bulk}} = \frac{1}{2} \boldsymbol{\sigma}:\boldsymbol{\alpha},\quad \tau_{\text{r}} = - \mathrm{sign}(\tau_{\text{bulk}})\mu \boldsymbol{\sigma}:\boldsymbol{\beta}

$$
# Weak form
$$
\delta \Pi(\boldsymbol{u},v) = \int_{\Omega} g(v)\delta\boldsymbol{\sigma}:\boldsymbol{\varepsilon}d\Omega + \int_{\Omega}\delta v g_{,v}(v)\frac{1}{2}\boldsymbol{\sigma}:\boldsymbol{\varepsilon}d\Omega + k \int_{\Omega} \frac{\delta v(v-1)}{2l} + 2 l \nabla \delta v \cdot \nabla v d\Omega + \delta \mathcal{F}(\boldsymbol{u})
$$

