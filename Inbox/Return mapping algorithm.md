---
icon: OcInfinity16
---

#Plasticity 

# Perfect plasticity
Consider an associative material following a specific yield function $f$, its plastic strain is given by
$$
\dot \varepsilon^p_{ij} = \dot \gamma \frac{\partial f}{\partial \sigma_{ij}}
$$
where $\frac{\partial f}{\partial \sigma_{ij}}$ is the direction of plastic strain, and $\dot \gamma$ is the counterpart magnitude can be computed from consistency condition
$$
\dot f = \frac{\partial f}{\partial \sigma_{ij}} \dot \sigma_{ij} = 0
$$
the increased stress is stated as
$$
\dot \sigma_{ij} = C_{ijkl} (\dot \varepsilon_{kl} - \dot \varepsilon_{kl}^p) = C_{ijkl}^{ep} \dot \varepsilon_{kl}
$$
substituting it into consistency condition yields
$$
\dot f = \frac{\partial f}{\sigma_{ij}} C_{ijkl}(\dot \varepsilon_{kl} - \dot \gamma \frac{\partial f}{\sigma_{kl}}) = 0
$$
$$
\dot \gamma = \frac{\frac{\partial f}{\sigma_{ij}}C_{ijkl}}{\frac{\partial f}{\partial \sigma_{mn}}C_{mnpq}\frac{\partial f}{\sigma_{pq}}} \dot \varepsilon_{kl}
$$
Consequently, the elastoplastic tangential modulus can be attained by
$$
\begin{split}
\dot \sigma_{ij} &= C_{ijkl}(\dot \varepsilon_{kl} - \dot \varepsilon_{kl}^p) \\
&= C_{ijkl}(\dot \varepsilon_{kl} - \dot \gamma \frac{\partial f}{\partial \sigma_{kl}}) \\
&= C_{ijkl}(\dot \varepsilon_{kl} - 
\frac{\frac{\partial f}{\partial \sigma_{ab}} C_{abcd} \dot \varepsilon_{cd}}
{\frac{\partial f}{\partial \sigma_{efgh}} C_{efgh} \frac{\partial f}{\partial \sigma_{gh}}}
\frac{\partial f}{\partial \sigma_{kl}}) \\
&= C_{ijkl}(\delta_{ck}\delta_{dl} - 
\frac{\frac{\partial f}{\partial \sigma_{ab}} C_{abcd}}
{\frac{\partial f}{\partial \sigma_{efgh}} C_{efgh} \frac{\partial f}{\partial \sigma_{gh}}}
\frac{\partial f}{\partial \sigma_{kl}}) \dot \varepsilon_{cd} \\
&= (C_{ijcd} - 
\frac{\frac{\partial f}{\partial \sigma_{ab}} C_{abcd} C_{ijkl} \frac{\partial f}{\partial \sigma_{kl}}}
{\frac{\partial f}{\partial \sigma_{efgh}} C_{efgh} \frac{\partial f}{\partial \sigma_{gh}}}) \dot \varepsilon_{cd} \\
&= (C_{ijkl} - 
\frac{C_{ijab} \frac{\partial f}{\partial \sigma_{ab}} \frac{\partial f}{\partial \sigma_{cd}} C_{cdkl}}
{\frac{\partial f}{\partial \sigma_{efgh}} C_{efgh} \frac{\partial f}{\partial \sigma_{gh}}}) \dot \varepsilon_{kl} \\
&= C_{ijkl}^{ep} \dot \varepsilon_{kl}
\end{split}
$$
$$
C_{ijkl}^{ep} = C_{ijkl} -
\frac{C_{ijab} \frac{\partial f}{\partial \sigma_{ab}} \frac{\partial f}{\partial \sigma_{cd}} C_{cdkl}}
{\frac{\partial f}{\partial \sigma_{ef}} C_{efgh} \frac{\partial f}{\partial \sigma_{gh}}}
$$

# Discrete form
$$
\boldsymbol \varepsilon^{p(n+1)} = \boldsymbol \varepsilon^{p(n)} + \Delta \gamma \frac{\partial f}{\partial \boldsymbol \sigma}
$$
$$
\begin{split}
\boldsymbol \sigma^{(n+1)} &= \boldsymbol C : (\boldsymbol \varepsilon^{(n+1)} - \boldsymbol \varepsilon^{p(n+1)}) \\
&= \boldsymbol C : (\boldsymbol \varepsilon^{(n+1)} - \boldsymbol \varepsilon^{p(n)}) -
\boldsymbol C : (\boldsymbol \varepsilon^{p(n+1)} - \boldsymbol \varepsilon^{p(n)}) \\
&= \boldsymbol \sigma^{tr} - \boldsymbol C : \Delta \boldsymbol \varepsilon^{p} \\
&= \boldsymbol \sigma^{tr} - \Delta \gamma \boldsymbol C : \frac{\partial f}{\partial \boldsymbol \sigma}(\boldsymbol \sigma^{(n+1)}) \\
&= \boldsymbol \sigma^{tr} - \Delta \gamma \boldsymbol C : \frac{\partial f}{\partial \boldsymbol \sigma}(\boldsymbol \sigma^{tr}) \\
&= \boldsymbol \sigma^{tr} - \Delta \gamma \boldsymbol C : \frac{\partial f^{tr}}{\partial \boldsymbol \sigma} \\
\end{split}
$$
#FIXME  $\frac{\partial f}{\partial \boldsymbol \sigma}(\boldsymbol \sigma^{(n+1)}) = \frac{\partial f^{tr}}{\partial \boldsymbol \sigma}$
**consistency condition**, the yield function at time step $n+1$ can be deduced as
$$
\begin{split}
f^{(n+1)} &= f(\boldsymbol \sigma^{(n+1)}) \\
&= f(\boldsymbol \sigma^{tr})+(\boldsymbol \sigma^{(n+1)} - \boldsymbol \sigma^{tr}):\frac{\partial f^{tr}}{\partial \boldsymbol \sigma} \\
&= f^{tr}-\Delta \gamma \frac{\partial f^{tr}}{\partial \boldsymbol \sigma} : \boldsymbol C : \frac{\partial f^{tr}}{\partial \boldsymbol \sigma} \\
&=0
\end{split}
$$
$$
\Delta \gamma = \frac{f^{tr}}{\frac{\partial f^{tr}}{\partial \boldsymbol \sigma} : \boldsymbol C : \frac{\partial f^{tr}}{\partial \boldsymbol \sigma}}
$$

# Flowchart
For time step $n$, input: $\boldsymbol \sigma^{(n)}$, $\boldsymbol \varepsilon^{p(n)}$, $\Delta \boldsymbol d_I^{(n)}$
1. calculate follows:
    - $\Delta \boldsymbol \varepsilon^{(n)}$:
        $$
        \Delta \varepsilon_{ij}^{(n)} = \sum_{I=1}^{n_p} \frac{1}{2}(\Psi_{I,j}d_{iI}^{(n)}+\Psi_{I,i}d_{jI}^{(n)})
        $$
    - $\boldsymbol \sigma^{tr}$:
        $$
        \sigma_{ij}^{tr} = \sigma_{ij}^{(n)} + C_{ijkl} \Delta \varepsilon_{kl}^{(n)}
        $$
    - $f^{tr}$:
        $$
        f^{tr} = f(\boldsymbol \sigma^{tr})
        $$
2. return mapping algorithm:
    1. if $f^{tr}\le0$
        - $\boldsymbol \sigma^{(n+1)} = \boldsymbol \sigma^{tr}$
        - $\boldsymbol \varepsilon^{p(n+1)} = \boldsymbol \varepsilon^{p(n)}$
        - $\boldsymbol C^T = \boldsymbol C$
    2. else
        - $\Delta \gamma$:
            $$
            \Delta \gamma = \frac{f^{tr}}{\frac{\partial f^{tr}}{\partial \boldsymbol \sigma} : \boldsymbol C : \frac{\partial f^{tr}}{\partial \boldsymbol \sigma}}
            $$
        - $\boldsymbol \sigma^{(n+1)}$:
            $$
            \sigma_{ij}^{(n+1)} = \sigma_{ij}^{tr} - \Delta \gamma C_{ijkl} \frac{\partial f^{tr}}{\partial \sigma_{kl}}
            $$
        - $\boldsymbol \varepsilon^{p(n+1)}$:
            $$
            \varepsilon_{ij}^{p(n+1)} = \varepsilon_{ij}^{p(n)} + \Delta \gamma \frac{\partial f^{tr}}{\partial \sigma_{ij}}
            $$
        - $\boldsymbol C^T = \boldsymbol C^{ep}$
3. calculate increased displacement
    - $\Delta \boldsymbol d^{(n+1)}=\boldsymbol K\setminus(\boldsymbol f^{ext(n+1)}-\boldsymbol f^{int(n)})$
