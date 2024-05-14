---
icon: OcInfinity16
---
#Approximation/VEM


Consider the following potential problem
$$
\left \{
\begin{array}{l}
    b = -u_{,ii} & \text{in} \; \Omega \\
    t = u_{,i}n_i & \text{on} \; \Gamma^t \\
    g = u & \text{on} \; \Gamma^g
\end{array}
\right .
$$
The corresponding weak form is given by
$$
\int_{\Omega} v_{,i} u_{,i} d\Omega = \int_{\Gamma} v t d\Gamma + \int_{\Omega} v b d\Omega
$$
# Projection operator
A projector is defined on each cell $\Omega_C, \cup \Omega_C=\Omega$, based upon **orthogonality condition** as follow
$$
\int_{\Omega_C}(\Pi v_{,i} - v_{,i}) \boldsymbol q d\Omega = 0
$$
these projector and the orthogonality can be regarded as the **smoothed gradient** and **integration constraint** as
$$
\int_{\Omega_C} \tilde v_{,i} \boldsymbol q d\Omega = \int_{\partial \Omega} v \boldsymbol q n_i d\partial \Omega - \int_{\Omega_C} v \boldsymbol q_{,i} d\Omega
$$
where $\tilde v_{,i}$ is the smoothed gradient constructed based upon assumed strain, $\Gamma_C$ is the boundary of $\Omega_C$.

The projector of gradient or said smoothed gradient is defined by a polynomial, yields
$$
\Pi v_{,i}(\boldsymbol x) = \tilde v_{,i}(\boldsymbol x) = \boldsymbol a^T \boldsymbol q(\boldsymbol x)
$$
substituting it into orthogonality condition leads to
$$
\boldsymbol a = \boldsymbol G^{-1} \boldsymbol g
$$
where
$$
\boldsymbol G = \int_{\Omega_C} \boldsymbol q \boldsymbol q^T d\Omega
$$
$$
\boldsymbol g = \int_{\partial \Omega} v \boldsymbol q n_i d\partial \Omega - \int_{\Omega_C} v \boldsymbol q_{,i} d\Omega
$$

# Degrees of freedom
The dofs for VEM are selected based upon two rules. For the boundary, the dofs are defined by integration points. For the interior, the dofs are defined by Taylor's series.
