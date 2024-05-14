---
icon: OcInfinity16
---

#Plasticity

# Bar problem
strong form
$$
\left \{
\begin{array}{l}
\sigma_{,x} + b = 0 & x \; \mathrm{in} \; \Omega \\
\sigma n_x = t & x \; \mathrm{on} \; \Gamma^t \\
u = g & x \; \mathrm{on} \; \Gamma^g \\
\end{array}
\right .
$$
weak form
$$
\int_{\Omega} \delta u_{,x} \sigma d\Omega = \int_{\Gamma^t} \delta u t d\Gamma + \int_{\Omega} \delta u b d\Omega
$$

# Return mapping
yield function
$$
f(\sigma,\alpha) = \vert \sigma \vert - (\sigma_Y + k\alpha) \le 0
$$
$$
\dot \sigma =
\left \{
\begin{array}{l}
E \dot \varepsilon & f<0 \\
\frac{EK}{E+K} \dot \varepsilon & f=0
\end{array}
\right .
$$
In $n+1$ step
$$
\left \{
\begin{array}{l}
\sigma_{n+1}^{tr} = \sigma_n + E\Delta \varepsilon_n \\
\varepsilon_{n+1}^{ptr} = \varepsilon_n^p \\
\alpha_{n+1}^{tr} = \alpha_n \\
f_{n+1}^{tr} = \vert \sigma_{n+1}^{tr} \vert - (\sigma_Y + K \alpha_{n+1}^{tr})
\end{array}
\right .
$$
for $f_{n+1}^{tr}\le0$, update variables
$$
\left \{
\begin{array}{l}
\sigma_{n+1} = \sigma_{n+1}^{tr} \\
\varepsilon_{n+1}^{p} = \varepsilon_n^p \\
\alpha_{n+1} = \alpha_n \\
E_T = E \\
\end{array}
\right .
$$
for $f_{n+1}^{tr}>0$
$$
\left \{
\begin{array}{l}
\Delta \gamma = \frac{f_{n+1}^{tr}}{E+K} \\
\sigma_{n+1} = \sigma_{n+1}^{tr} - \Delta \gamma E \mathrm{sign}(\sigma_{n+1}^{tr}) \\
\varepsilon_{n+1}^{p} = \varepsilon_n^p + \Delta \gamma \mathrm{sign}(\sigma_{n+1}^{tr}) \\
\alpha_{n+1} = \alpha_n + \Delta \gamma \\
E_T = \frac{EK}{E+K} \\
\end{array}
\right .
$$

# Approximation
displacement
$$
u^h = \sum_{I=1}^{n_p} N_I d_I
$$
$$
\Delta \varepsilon_n = \sum_{I=1}^{n_p} N_{I,x} \Delta d_{nI}
$$
equilibrium equation
$$
f^{\mathrm{int}}_I = f^{\mathrm{ext}}_I
$$
$$
f^{\mathrm{int}}_I = \int_{\Omega} N_{I,x} \sigma d\Omega
$$
linearization
$$
f^{\mathrm{int}}_{I,n+1} = f^{\mathrm{ext}}_{I,n+1}
$$
$$
f^{\mathrm{int}}_{I,n+1} = f^{\mathrm{int}}_{I,n} + \Delta f^{\mathrm{int}}_{I,n}
$$
$$
\Delta f^{\mathrm{int}}_{I,n} = \int_{\Omega} N_{I,x} \Delta \sigma d\Omega = \sum_{J=1}^{n_p} \int_{\Omega} N_{I,x} E_T N_{J,x} d\Omega \Delta d_{nJ}
$$
matrix form
$$
\boldsymbol K \Delta \boldsymbol d_{n+1} = f^{\mathrm{ext}}_{n+1} - f^{\mathrm{int}}_{n}
$$
with
$$
K_{IJ} = \int_{\Omega} N_{I,x} E_T N_{J,x} d\Omega
$$
$$
f_{I,n}^{\mathrm{int}} = \int_{\Omega} N_{I,x} \sigma_n d\Omega
$$

# Flowchart
For time step $n$, input: $\sigma_{n}$, $\varepsilon_{n}^p$, $\alpha_n$, $\Delta \varepsilon_{n}$
1. calculate follows:
    - $\sigma_{n+1}^{tr}=\sigma_{n}+E \Delta \varepsilon_n$
    - $\varepsilon_{n+1}^{ptr}=\varepsilon_{n}^p$
    - $\alpha_{n+1}^{tr}=\alpha_{n}$
    - $f_{n+1}^{tr} = \vert \sigma_{n+1}^{tr} \vert - (\sigma_Y + K \alpha_{n+1}^{tr})$
2. Return mapping algorithm:
    1. if $f_{n+1}^{tr}\leq 0$
        - $\sigma_{n+1}=\sigma_{n+1}^{tr}$
        - $\varepsilon_{n+1}^p=\varepsilon_{n}^p$
        - $\alpha_{n+1}=\alpha_n$
        - $E_T = E$
    2. if $f_{n+1}^{tr}>0$
        - $\Delta \gamma = \frac{f_{n+1}^{tr}}{E+K}$
        - $\sigma_{n+1} = \sigma_{n+1}^{tr} - \Delta \gamma E \mathrm{sign}(\sigma_{n+1}^{tr})$
        - $\varepsilon_{n+1}^{p} = \varepsilon_n^p + \Delta \gamma \mathrm{sign}(\sigma_{n+1}^{tr})$
        - $\alpha_{n+1} = \alpha_n + \Delta \gamma$
        - $E_T = \frac{EK}{E+K}$
3. calculate increase displacement
    - $\Delta \boldsymbol d_{n+1} = \boldsymbol K \setminus (\boldsymbol f^{\mathrm{ext}}_{n+1} - \boldsymbol f^{\mathrm{int}}_n)$
    - $\Delta \varepsilon_{n+1} = \sum_{I=1}^{n_p}N_{I,x}\Delta d_{(n+1)I}$
