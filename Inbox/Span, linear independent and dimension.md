---
icon: OcInfinity16
---

#Math/FunctionalAnalysis

# Span
Let $V$ be a vector space and $\boldsymbol v_1, \dots, \boldsymbol v_n \in V$. The set $\{\boldsymbol v_1, \dots, \boldsymbol v_n\}$ is a spanning set for $V$ if
$$
\mathrm{span}\{\boldsymbol v_1, \dots, \boldsymbol v_n\} = V
$$
We also say that $V$ is **generated** or **spanned** by $\boldsymbol v_1, \dots, \boldsymbol v_n$.

# Linear dependence
A set of vector $\{\boldsymbol v_1, \dots, \boldsymbol v_n\}$ is said to be **linear dependent** if there are scalars $c_1, \dots, c_n$, *not all zero*, such taht
$$
c_1 \boldsymbol v_1 + c_2 \boldsymbol v_2 + \cdots + c_n \boldsymbol v_n = \boldsymbol 0
$$
Such a linear combination is called a **linear dependence relation** or a **linear dependency**. The set of vectors is **linearly independent** if the *only* linear combination producing $\boldsymbol 0$ is the trivial one with $c_1 = \cdots =c_n=0$.

# Basis
A set of vector $\{\boldsymbol v_1, \dots, \boldsymbol v_n\}$ in a vector space $V$ is called a **basis** (plural **bases**) for $V$ if
1. The vectors are linearly independent.
2. They span $V$.

# Dimension
The number of elements in any basis is the **dimension** of the vector space, and denoted by $\dim V$.
