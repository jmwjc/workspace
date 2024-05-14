---
icon: OcInfinity16
---
#Formulation/Galerkin 

The numerical approaches for solving partial differential equations mostly are designated by fulfillment of variational consistency
$$
\int_{\Omega} v_{,i} u d\Omega = \int_{\Gamma} v u n_i d\Gamma - \int_{\Omega} v u_{,i} d\Omega, \quad \forall v\in V,\; \forall u\in U
$$
where $u$ is a variable in $\Omega$ and can be easily expanded by Taylor's series, yields
$$
\int_{\Omega} v_{,i} \boldsymbol q d\Omega = \int_{\Gamma} v \boldsymbol q n_i d\Gamma - \int_{\Omega} v\boldsymbol q_{,i} d\Omega, \quad \forall v\in V
$$
and $\boldsymbol q$ is a monomials vector with an order of $p-1$. The above relationship between $v_{,i}$ and $v$ is namely **orthogonal condition** and it implies that if a exact integration is used herein, the gradient $v_{,i}$ can be evaluated straightforwardly by the direct derivative of $v$. However, for some numerical approachs, the approximants of $v$ do not have the explicit expression, which leads to a approximate integration. At this point, for the variational consistency, the gradient $v_{,i}$ can be determined by this orthogonal condition.
In the above orthogonal condition, the integrations in domain $\Omega$ and on its boundary $\Gamma$ play important roles in the accuracy of these methods. 

In order to meet orthogonal condition, the gradient $v_{,i}$ always is assumed to be a polynomial with identical order with $\boldsymbol q$
$$
v_{,i}(\boldsymbol x) = \boldsymbol q^T(\boldsymbol x) \boldsymbol a_i
$$
where $\boldsymbol a_i$ is a coefficient vector and can be solved by orthogonal condition.
