---
icon: OcInfinity16
---
#Formulation/Galerkin

The Galerkin methods can be expressed as following problem:
$$
a(v,u) = f(v),\quad \forall v \in V
$$
where $a$ and $f$ are bilinear form and linear functional. The result $u$ are are company with the smallest energy error, yields:
$$
H^{Energy} = \frac{1}{2} a(u-u^h,u-u^h)
$$
such that the interpolation error with respect of energy must less than the error caused by Galerkin methods:
$$
H^{Energy} \le \frac{1}{2} a(u-u^i,u-u^i)
$$
in which $u^i$ is the interpolation of $u$. With the above inequation, we can check whether a new Galerkin mehtods we proposed is correct or not.


