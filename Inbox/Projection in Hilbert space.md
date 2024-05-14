---
icon: OcInfinity16
---

#Math #Math/FunctionalAnalysis

## Hilbert space
An inner-product space $(X,(:,:))$ is **Hilbert space** if, as a norm vector space, it is a *Banach space*, i.e., if $X$ is complete with respect to the norm $\Vert \cdot \Vert$ defined by $\Vert x \Vert = \sqrt{(x,x)}, \; \forall x \in X$.

## Linear Operator
- Let $X$ and $Y$ are two vector spaces, a mapping $P: X\rightarrow Y$ is a **linear operator** from $X$ into $Y$, or **linear functional (linear form)** if $Y=\mathbb K$, if
$$
P(x+y) = P(x) + P(y), \quad P(\alpha x) = \alpha P(x), \quad \forall x,\; y \in X,\; \alpha \in \mathbb K
$$
- Let $P: X \rightarrow Y$ be a linear operator. Then the **kernel** of $P$ is the subset of $X$ defined by
$$
\ker P := \{ x \in X \; \vert \; Px = 0 \}
$$
A **direct image** $P(X)$ of $X$ under $P$, also called the **range** of $P$, is also denoted $\textrm{Im}\:P$, defined as follows
$$
\textrm{Im}\: P := P(X) = \{ y \in Y \; \vert \; \exists x \in X,\; y = Px \}
$$
Clearly, $\ker P \subset X$ and $\textrm{Im}\: P \subset Y$.
- $P$ is an **idempotent operator** if and only if $P^2 = P$. 
- **Closed graph theorem**: Let $X$ and $Y$ be two normed vector spaces and let $P:X\rightarrow Y$ be a linear operator. Then the following properties are equivalent:
1. The linear operator $P$ is continuous on $X$.
2. The linear operator $P$ is continuous at the origin of $X$.
3. There exists a constant $C>0$ such that
$$
\Vert Px \Vert \le C \Vert x \Vert, \quad \forall x \in X
$$
4. The direct image under $P$, $\textrm{Im}\; P$ of any bounded subset of $X$ is a bounded subset of $Y$.
- **Hilbert projection theorem**: For every vector $x$ in a Hilbert space $X$ and every nonempty closed convex $C \subseteq X$, there exists a unique vector $m\in C$ for which 
$$
\Vert x - m \Vert = \inf_{c \in C} \Vert x - c \Vert
$$
