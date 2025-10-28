## [[Inverse Matrix]] 🧮
Given a **square matrix** $A \in M_{n\times n}$, we say $A$ is **invertible** if there exists $B \in M_{n\times n}$ such that:
$$AB = BA = I_{n}$$  
We call $B$ the **inverse matrix** of $A$ and denote it by $A^{-1}$.

👉 **Only square matrices** can be invertible.

---

## [[Definition via Gaussian–Jordan Elimination]] ⚙️
Given $A \in M_{n\times n}$:

1. $A$ is invertible **iff** it can be reduced to $I_{n}$ using Gaussian–Jordan Elimination.  
2. If  
   $$(A|I_{n}) \xrightarrow{\text{G.J.E.}} (I_{n}|B)$$  
   then  
   $$A^{-1} = B$$  
3. For $Ax = b$, where $A \in M_{n\times n}$:  
   If $A$ is invertible, then the system has **one unique solution**  
   $$x = A^{-1}b$$

---

## [[Theorem 1 — Uniqueness of the Inverse]] 🔒
If the inverse matrix exists, it is **unique**.

**Proof:**  
Suppose $A \in M_{n\times n}$, and both $B_{1}$ and $B_{2}$ are inverses of $A$. Then:
$$
\begin{cases}
AB_{1} = B_{1}A = I_{n} \\
AB_{2} = B_{2}A = I_{n}
\end{cases}
$$
From $AB_{1} = I_{n}$:
$$B_{2}AB_{1} = B_{2}I_{n} \Rightarrow (B_{2}A)B_{1} = B_{2} \Rightarrow I_{n}B_{1} = B_{2} \Rightarrow B_{1}=B_{2}$$

Hence, the inverse is **unique**. ✅

---

## [[Theorem 2 — Properties of Inverse Matrices]] 🧠
Let $A, B \in M_{n\times n}$ be invertible matrices, and let $\lambda \in \mathbb{R}$, $\lambda \neq 0$.

1. If $A$ is invertible, then $A^{T}$ is invertible and  
   $$(A^{T})^{-1} = (A^{-1})^{T}$$  
2. If $A$ is invertible, then $A^{-1}$ is invertible and  
   $$(A^{-1})^{-1} = A$$  
3. If $A, B$ are invertible, then $AB$ is invertible and  
   $$(AB)^{-1} = B^{-1}A^{-1}$$  
4. If $A$ is invertible and $\lambda \neq 0$, then $\lambda A$ is invertible and  
   $$(\lambda A)^{-1} = \frac{1}{\lambda}A^{-1}$$  

---

🧩 **Summary Insight:**  
Invertibility links algebraic structure to geometric intuition — every invertible matrix corresponds to a **reversible linear transformation** (no information loss).

---

