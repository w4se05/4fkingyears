## [[Vector Space]] 🧭
Let $\mathbb{K}$ be a field (in our case $\mathbb{R}$).  
A **vector space** over $\mathbb{K}$ is a non-empty set $V$ equipped with:

- an operation of **addition** $+:V\times V\to V$
- an operation of **scalar multiplication** $\cdot:\mathbb{K}\times V\to V$

satisfying the following **axioms**.

---

## [[Axioms of Vector Spaces]] ⚙️
For all $u,v,w\in V$ and all $\alpha,\beta\in\mathbb{K}$:

1. **Commutativity:** $u+v=v+u$
2. **Associativity:** $(u+v)+w=u+(v+w)$
3. **Additive Identity:** $\exists\,0\in V$ s.t. $u+0=u$
4. **Additive Inverse:** $\forall\,u\in V,\,\exists\,(-u)\in V$ s.t. $u+(-u)=0$
5. **Distributivity (Vector):** $\alpha(u+v)=\alpha u+\alpha v$
6. **Distributivity (Scalar):** $(\alpha+\beta)u=\alpha u+\beta u$
7. **Compatibility:** $(\alpha\beta)u=\alpha(\beta u)$
8. **Identity:** $1\cdot u=u$

---

## [[Examples of Vector Spaces]] 📚
1. $\mathbb{R}^n$: all $n$-tuples of real numbers  
2. $M_{m\times n}(\mathbb{R})$: set of real $m\times n$ matrices  
3. $P_n$: set of all real polynomials of degree ≤ n  
4. $\mathbb{R}^m$: column vectors with $m$ components  

Each of these satisfies the above axioms under natural addition and scalar multiplication.

---

## [[Subspace]] 🔹
A non-empty subset $W\subseteq V$ is a **subspace** if:

1. $0\in W$  
2. If $u,v\in W$, then $u+v\in W$  
3. If $\alpha\in\mathbb{R}$ and $u\in W$, then $\alpha u\in W$

---

## [[Linear Combination and Span]] ➕
Given $v_1,\dots,v_k\in V$ and scalars $\alpha_1,\dots,\alpha_k\in\mathbb{R}$,  
a vector $v$ is a **linear combination** if:
$$v=\alpha_1v_1+\alpha_2v_2+\dots+\alpha_kv_k$$

The set of all such combinations is the **span**:
$$\text{Span}\{v_1,\dots,v_k\}=\{\alpha_1v_1+\dots+\alpha_kv_k\mid \alpha_i\in\mathbb{R}\}$$

---

## [[Linear Independence]] ⚖️
The set $\{v_1,\dots,v_k\}$ is **linearly independent** if:
$$\alpha_1v_1+\alpha_2v_2+\dots+\alpha_kv_k=0 \implies \alpha_1=\dots=\alpha_k=0$$

Otherwise, it is **linearly dependent**.

---

## [[Basis and Dimension]] 🧩
A **basis** of $V$ is a linearly independent set that spans $V$.

The **dimension** of $V$ is the number of elements in any of its bases.

Examples:
- $\dim(\mathbb{R}^n)=n$
- $\dim(M_{m\times n})=mn$
- $dim(P_{n}(x))=n+1$
- $dim(l^{\infty})=\infty$

---

## [[Sum and Intersection of Subspaces]] 🔀
Given subspaces $U,W\subseteq V$:
- **Sum:** $U+W=\{u+w\mid u\in U,w\in W\}$
- **Intersection:** $U\cap W=\{v\mid v\in U\text{ and }v\in W\}$

If $U\cap W=\{0\}$, we say the sum is **direct** and write $V=U\oplus W$.

---

## [[Linear Mapping]] 🔁
A mapping $T:V\to W$ is **linear** if:
$$T(u+v)=T(u)+T(v),\quad T(\alpha u)=\alpha T(u)$$
for all $u,v\in V$ and $\alpha\in\mathbb{R}$.

Every linear mapping can be represented by a **matrix** relative to a chosen basis.

---

## [[Connection with Matrices and LES]] 🔗
Let $A\in M_{m\times n}$.  
Then the associated linear map $T_A:\mathbb{R}^n\to\mathbb{R}^m$ is given by:
$$T_A(x)=Ax$$

- **Image of $T_A$** = **Column space** of $A$
- **Kernel of $T_A$** = **Null space** of $A$
- $\operatorname{rank}(A)=\dim(\text{Im}(A))$
- $\operatorname{nullity}(A)=\dim(\text{Ker}(A))$

By **Rank–Nullity Theorem:**
$$\operatorname{rank}(A)+\operatorname{nullity}(A)=n$$

---

**Summary Insight:**  
A vector space abstracts all linear behavior in algebraic form —  
its elements are vectors, its operations are linear,  
and its substructures (span, basis, rank) form the core of linear algebra itself. 🧭
