## [[Determinant]] 🧮
Let $A \in M_{n\times n}$ be a **square matrix** over $\mathbb{R}$.  
We define a function
$$
\det: M_{n\times n} \to \mathbb{R}
$$
that assigns to each square matrix a real number satisfying the following algebraic properties.

---

## [[Axiomatic Definition]] ⚙️
The determinant is the **unique** function $\det(A)$ satisfying:

1. **Linearity in each row:**  
   $\det(A)$ is linear with respect to every row when others are fixed.

2. **Alternation:**  
   If two rows of $A$ are equal, $\det(A)=0$.

3. **Normalization:**  
   $\det(I_n)=1$

From these axioms, all determinant properties are derived.

---

## [[Determinant of Order 2 and 3]] 🧩
For $A=\begin{pmatrix} a & b \\ c & d \end{pmatrix}$,  
$$\det(A)=ad-bc$$

For $$A=\begin{pmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}
\end{pmatrix}$$
$$\det(A)=a_{11}(a_{22}a_{33}-a_{23}a_{32})
-a_{12}(a_{21}a_{33}-a_{23}a_{31})
+a_{13}(a_{21}a_{32}-a_{22}a_{31})
$$

---

## [[Laplace Expansion (General Formula)]] 🧠
Given $A=(a_{ij})_{n\times n}$, the determinant may be computed recursively as:
$$
\det(A)=\sum_{j=1}^{n}(-1)^{1+j}a_{1j}\det(A_{1j})
$$
where $A_{1j}$ is the **minor** obtained by deleting the 1st row and $j$th column of $A$.

This expansion can be done along **any row or column**.

---

## [[Elementary Properties of Determinants]] 📜
For $A,B\in M_{n\times n}$ and $\lambda\in\mathbb{R}$:

1. $\det(I_n)=1$
2. $\det(A^T)=\det(A)$
3. If $A$ has a zero row (or column), then $\det(A)=0$
4. Interchanging two rows (or columns) multiplies $\det(A)$ by $-1$
5. Multiplying one row (or column) by $\lambda$ multiplies $\det(A)$ by $\lambda$
6. If two rows (or columns) are linearly dependent, $\det(A)=0$
7. $\det(AB)=\det(A)\det(B)$
8. If $A$ is invertible, then $\det(A^{-1})=\frac{1}{\det(A)}$

---

## [[Triangular Matrices]] 🔺
If $A$ is upper or lower triangular,  
$$
\det(A)=a_{11}\cdot a_{22}\cdot\dots\cdot a_{nn}
$$
—the product of the diagonal entries.

---

## [[Invertibility Criterion]] 🔒
A matrix $A\in M_{n\times n}$ is **invertible**  
⇔ $\det(A)\neq0$

If $\det(A)=0$, then $A$ is **singular** and has no inverse.

---

## [[Determinant and Linear Systems]] 🔗
Given $Ax=b$, if $\det(A)\neq0$, then $A$ is invertible, and the system admits a **unique solution**:
$$x=A^{-1}b$$

---

## [[Cramer’s Rule]] 🧭
If $\det(A)\neq0$, then each component $x_i$ of the solution is given by:
$$x_i=\frac{\det(A_i)}{\det(A)}$$
where $A_i$ is obtained by replacing the $i$-th column of $A$ with the column vector $b$.

---

## [[Determinant and Rank]] 📏
A matrix $A$ satisfies:
- $\det(A)\neq0 \iff \operatorname{rank}(A)=n$
- $\det(A)=0 \iff \operatorname{rank}(A)<n$

Thus, determinant measures the **degree of linear dependence** among rows (or columns).

---

**Summary Insight:**  
Determinant is the algebraic scalar that encodes the structural behavior of a matrix —  
it reveals dependence, invertibility, and the strength of linear transformations in $\mathbb{R}^n$.
