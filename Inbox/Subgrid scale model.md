---
icon: OcInfinity16
---

#Formulation/Galerkin 

Consider the following variational problem that

$$
\textrm{find} \; u \in V,\quad a(v,u) = f(v), \quad \forall v \in V
$$

leading a decomposition to variables $v,u$, such that

$$
v = \bar v + v', \quad u = \bar u + u'
$$

At this circumstance, the variational problem split into two problems as

$$
\textrm{find} \; u \in V, \quad a(\bar v, \bar u) + a(\bar v, u') = f(\bar v), \quad \forall \bar v \in V
$$
$$
\textrm{find} \; u \in V, \quad a(v', \bar u) + a(v', u') = f(v'), \quad \forall v' \in V
$$
