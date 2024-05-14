---
icon: OcInfinity16
---
#Incompressible #Elasticity 

The locking problem in Galerkin formulation is arose due to the mismatch of magnitudes of material parameters. We summarize some conventional locking problem as follows, where the <font color=red>locking variables</font> is colored by red, and the <font color=blue>total variables</font> is blue. 
Furthermore, the tables shows the locking and free degrees of freedoms while the total variables are assumed to be polynomials. The $p$ in tables stands for the order of polynomial, $n_p$ is the number of the $p$-th order independent monomials, $n_q$ is the monomial number of locking variable with $q$-order, and the $n_p$ and $n_q$ can be computed by
$$
n_p = \frac{(p+d)!}{p!d!}, \quad n_q = \frac{(q+d)!}{q!d!}
$$
where $d$ is the number of dimensions.
and then, $n_t$, $n_c$ are the numbers of total DOFs, constraint DOFs respectively and can be evaluated by
$$
n_t = n_p \times \; \text{num. of {\color{blue}total variables}}
$$
$$
n_c = n_q \times \; \text{num. of {\color{red}locking variables}}
$$
- **[[Linear Elasticity#Spectral decomposition of elasticity|Volumetric locking in elasticity problem]]**
$$
{\color{blue} u_i, \; i=1,2,3} \qquad p = K {\color{red} u_{k,k}}
$$
| $p$ | $n_p$| $n_q$ | $n_t$ | $n_c$ |
|:---:|:---:|:---:|:---:|:---:|
|1|4|1|12|1|
|2|10|4|30|4|
|3|20|10|60|10|
|…|…|…|…|…|
|$n$|$\frac{(n+3)!}{n!3!}$|$\frac{(n+2)!}{(n-1)!3!}$|$\frac{(n+3)!}{n!2}$|$\frac{(n+2)!}{(n-1)!3!}$|
$$
$$
- **[[Linear Elasticity#Spectral decomposition of elasticity|Volumetric locking in plane-strain problem]]**
$$
{\color{blue} u_i, \; i=1,2} \qquad p = K {\color{red} u_{k,k}}
$$
| $p$ | $n_p$| $n_q$ | $n_t$ | $n_c$ |
|:---:|:---:|:---:|:---:|:---:|
|1|3|1|6|1|
|2|6|3|12|3|
|3|10|6|20|6|
|…|…|…|…|…|
|$n$|$\frac{(n+2)!}{n!2!}$|$\frac{(n+1)!}{(n-1)!2!}$|$\frac{(n+2)!}{n!}$|$\frac{(n+1)!}{(n-1)!2!}$|
- **[[Bar and beam#Timoshenko-Ehrenfest beam|Shearing locking in Timoshenko beam problem]]**
$$
{\color{blue} w, \varphi} \qquad V = kGA({\color{red}w_{,x}-\varphi})
$$
| $p$ | $n_p$| $n_q$ | $n_t$ | $n_c$ |
|:---:|:---:|:---:|:---:|:---:|
|1|2|2|4|2|
|2|3|3|6|3|
|3|4|4|8|4|
|…|…|…|…|…|
|$n$|$n+1$|$n+1$|$2n+2$|$n+1$|
- [ ] #TODO **Shearing locking in Mindlin plate problem**
- [ ] #TODO **[[Curved beam|Membrane and shearing locking in curved Timoshenko beam problem]]**

$$
{\color{blue} u,w, \varphi} \qquad N = EA({\color{red}u_{,1}-\Gamma_{11}^3 w}),\;V = kGA({\color{red}w_{,1}-\varphi-\Gamma_{13}^1u})
$$
| $p$ | $n_p$| $n_q$ | $n_t$ | $n_c$ |
|:---:|:---:|:---:|:---:|:---:|
|1|2|2|6|2|
|2|3|3|9|3|
|3|4|4|12|4|
|…|…|…|…|…|
|$n$|$n+1$|$n+1$|$3n+3$|$n+1$|
- [ ] #TODO **[[Curved beam|Membrane locking in curved Euler beam problem]]**
$$
{\color{blue} u,w} \qquad N = EA({\color{red}u_{,1}-\Gamma_{11}^3 w})
$$
| $p$ | $n_p$| $n_q$ | $n_t$ | $n_c$ |
|:---:|:---:|:---:|:---:|:---:|
|1|2|2|4|2|
|2|3|3|6|3|
|3|4|4|8|4|
|…|…|…|…|…|
|$n$|$n+1$|$n+1$|$2n+2$|$n+1$|
- [ ] #TODO  **Membrane and shearing locking in Mindlin shell problem**
- [ ] #TODO  **Membrane locking in Kirchhoff shell problem**
- [ ] #TODO  **Membrane and shearing locking in Mindlin shell problem**
- [ ] #TODO  **Membrane locking in Kirchhoff shell problem**
