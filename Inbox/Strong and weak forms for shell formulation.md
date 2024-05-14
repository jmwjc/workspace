---
icon: OcInfinity16
---


#Elasticity/Shell/Thin-shell 


**Constitutive relationship**
$$
\begin{equation}
\begin{split}
\boldsymbol{\sigma} &= \boldsymbol{C}:\boldsymbol{\varepsilon} \\&=
C_{abcd} \varepsilon_{cd} \; \boldsymbol{e}_a \otimes \boldsymbol{e}_b \\&=
C^{ijkl} \varepsilon_{kl} \; \boldsymbol{g}_i \otimes \boldsymbol{g}_j
\end{split}
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\boldsymbol{C} &= C_{abcd} \; \boldsymbol{e}_a \otimes \boldsymbol{e}_b
\otimes \boldsymbol{e}_c \otimes \boldsymbol{e}_d \\&=
C_{abcd} \frac{\partial \xi^i}{\partial x_a}
\frac{\partial \xi^j}{\partial x_b}
\frac{\partial \xi^k}{\partial x_c}
\frac{\partial \xi^l}{\partial x_d}
\; \boldsymbol{g}_i \otimes \boldsymbol{g}_j
\otimes \boldsymbol{g}_k \otimes \boldsymbol{g}_l \\&=
(\lambda \delta_{ab} \delta_{cd} + \mu(\delta_{ac}\delta_{bd}+\delta_{ad}\delta_{bc}))
\frac{\partial \xi^i}{\partial x_a}
\frac{\partial \xi^j}{\partial x_b}
\frac{\partial \xi^k}{\partial x_c}
\frac{\partial \xi^l}{\partial x_d}
\; \boldsymbol{g}_i \otimes \boldsymbol{g}_j
\otimes \boldsymbol{g}_k \otimes \boldsymbol{g}_l \\&=
(\lambda \frac{\partial \xi^i}{\partial x_a} \frac{\partial \xi^j}{\partial x_a}
\frac{\partial \xi^k}{\partial x_c} \frac{\partial \xi^l}{\partial x_c} +
\mu (\frac{\partial \xi^i}{\partial x_a} \frac{\partial \xi^j}{\partial x_b}
\frac{\partial \xi^k}{\partial x_a} \frac{\partial \xi^l}{\partial x_b} +
\frac{\partial \xi^i}{\partial x_a} \frac{\partial \xi^j}{\partial x_b}
\frac{\partial \xi^k}{\partial x_b} \frac{\partial \xi^l}{\partial x_a})
\; \boldsymbol{g}_i \otimes \boldsymbol{g}_j
\otimes \boldsymbol{g}_k \otimes \boldsymbol{g}_l\\&=
(\lambda g^{ij}g^{kl} + \mu(g^{ik}g^{jl} + g^{il}g^{jk}))\; \boldsymbol{g}_i \otimes \boldsymbol{g}_j
\otimes \boldsymbol{g}_k \otimes \boldsymbol{g}_l
\end{split}
\end{equation}
$$
$$
\begin{equation}
C^{ijkl} = \lambda g^{ij}g^{kl} + \mu(g^{ik}g^{jl} + g^{il}g^{jk})
\end{equation}
$$
**Internal force**
$$
\begin{equation}
\begin{split}
\int_{\Omega} \delta \boldsymbol{\varepsilon} : \boldsymbol{\sigma} d\Omega &=
\int_{\Omega} \delta\varepsilon_{\alpha \beta} \sigma^{\alpha \beta} d\Omega \\&=
\int_{\bar{\Omega}}\int_{-t}^{t} (\delta\epsilon_{\alpha \beta}+\xi^3\delta\kappa_{\alpha \beta})
C^{\alpha \beta \gamma \eta} (\epsilon_{\gamma \eta}+\xi^3\kappa_{\gamma \eta}) d\xi^3 d\bar{\Omega} \\&=
\int_{\bar{\Omega}}\int_{-\frac{h}{2}}^{\frac{h}{2}} (\delta\epsilon_{\alpha \beta}+\xi^3\delta\kappa_{\alpha \beta})
C^{\alpha \beta \gamma \eta} (\epsilon_{\gamma \eta}+\xi^3\kappa_{\gamma \eta}) d\xi^3 d\bar{\Omega} \\&=
\int_{\bar{\Omega}}\delta\epsilon_{\alpha \beta} N^{\alpha \beta} d\bar{\Omega} +
\int_{\bar{\Omega}}\delta\kappa_{\alpha \beta}M^{\alpha \beta}d\bar{\Omega}
\end{split}
\end{equation}
$$
$$
\begin{equation}
N^{\alpha \beta} = hC^{\alpha \beta \gamma \eta}\epsilon_{\gamma \eta}, \quad M^{\alpha \beta} = \frac{h^3}{12}C^{\alpha \beta \gamma \eta}\kappa_{\gamma \eta}
\end{equation}
$$

**External force**

Traction:
$$
\begin{equation}
\begin{split}
\boldsymbol{t} &= \boldsymbol{\sigma} \cdot \boldsymbol{n} \\
&= \sigma^{\alpha \beta} \boldsymbol{g}_\alpha
\otimes \boldsymbol{g}_\beta \cdot \boldsymbol{n}
\end{split}
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\int_{\bar{\Gamma}}
\int_{-\frac{h}{2}}^{\frac{h}{2}}
\delta \boldsymbol{u} \cdot \boldsymbol{t}d\xi^3 d\bar{\Gamma}
&= \int_{\bar{\Gamma}}
\int_{-\frac{h}{2}}^{\frac{h}{2}}
(\delta v_{\alpha} + \xi^3 \delta \vartheta_\alpha)
(\sigma^{\alpha \beta} n_\beta) d\xi^3 d\bar{\Gamma} \\
&= \int_{\bar{\Gamma}}
\int_{-\frac{h}{2}}^{\frac{h}{2}}
(\delta v_{\alpha} + \xi^3 \delta \vartheta_\alpha)
(C^{\alpha \beta \gamma \eta}(\epsilon_{\gamma \eta}
+ \xi^3 \kappa_{\gamma \eta}))
n_{\beta} d\xi^3 d\bar{\Gamma} \\
&= \int_{\bar{\Gamma}} \delta v_\alpha
N^{\alpha \beta} n_\beta d\bar{\Gamma} +
\int_{\bar{\Gamma}} \delta \vartheta_\alpha
M^{\alpha \beta} n_{\beta} d\bar{\Gamma}\\
&= \int_{\bar{\Gamma}} \delta \boldsymbol{v} \cdot
\boldsymbol{N} \cdot \boldsymbol{n} d\bar{\Gamma} +
\int_{\bar{\Gamma}} \delta \boldsymbol{\vartheta} \cdot
\boldsymbol{M} \cdot \boldsymbol{n} d\bar{\Gamma}
\end{split}
\end{equation}
$$

Body force:
$$
\begin{equation}
\begin{split}
\boldsymbol{b} &= b^\alpha \boldsymbol{g}_\alpha \\
&= - \boldsymbol{\sigma} \cdot  \nabla\\
&= - (\sigma^{\alpha \beta} \boldsymbol{g}_\alpha \otimes
\boldsymbol{g}_{\beta}) \cdot
\frac{\partial}{\partial \xi^\gamma} \boldsymbol{g}^\gamma\\
&= - (\sigma^{\alpha \beta} \boldsymbol{g}_\alpha)_{,\beta} \\
&= -(\sigma^{\alpha \beta}_{,\beta} +
\sigma^{\beta \gamma} \Gamma_{\beta \gamma}^\alpha) \boldsymbol{g}_\alpha \\
&= - \sigma^{\alpha \beta}|_\beta \boldsymbol{g}_\alpha
\end{split}
\end{equation}
$$
$$
\begin{equation}
\sigma^{\alpha \beta}|_\beta = \sigma^{\alpha \beta}_{,\beta} +
\sigma^{\beta \gamma} \Gamma_{\beta \gamma}^\alpha
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\boldsymbol{\vartheta} &= \frac{1}{J}
(\boldsymbol{\varrho}_{,1} \times
\boldsymbol{v}_{,2} + \boldsymbol{v}_{,1} \times \boldsymbol{\varrho}_{,2}) \cdot
\boldsymbol{g}_{\alpha} \; \boldsymbol{g}^\alpha \\
&= \vartheta_\alpha \boldsymbol{g}^\alpha
\end{split}
\end{equation}
$$
$$
\begin{equation}
\begin{split}
\int_{\bar{\Omega}} \int_{-\frac{h}{2}}^{\frac{h}{2}}
\delta \boldsymbol{u} \cdot \boldsymbol{b} d\xi^3 d\bar{\Omega}
&= \int_{\bar{\Omega}} \int_{-\frac{h}{2}}^{\frac{h}{2}}
\delta u_\alpha \boldsymbol{g}^{\alpha} \cdot
b^\beta \boldsymbol{g}_{\beta}d\xi^3 d\bar{\Omega}\\
&= - \int_{\bar{\Omega}} \int_{-\frac{h}{2}}^{\frac{h}{2}}
(\delta v_\alpha + \xi^3 \delta \vartheta_\alpha)
\sigma^{\alpha \beta}|_\beta d\xi^3 d\bar{\Omega} \\
&= - \int_{\bar{\Omega}} \delta v_\alpha
N^{\alpha \beta}|_\beta d\bar{\Omega} -
\int_{\bar{\Omega}} \delta \vartheta_\alpha
M^{\alpha \beta}|_\beta d\bar{\Omega}
\end{split}
\end{equation}
$$
