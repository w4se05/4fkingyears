>[!Definition]
>Given a Square Matrix $A \in M_{n\times n}$. A is invertible if $\exists \; B\in M_{n\times n}$ so that $AB=BA=I_{n}$. We call B an invert matrix of 
**For God's sake pls remember ONLY SQUARE MATRIX can be INVERTIBLE**

>[!Definition] Also Definition But a Lil More Formal
>Given $A\in M_{n\times n}$
>1. A is invertible if A can be reduced to $I_{n}$ using Gaussian-Jordan Elimination
>2. If $(A|I_{n})\xrightarrow{\text{G.J.E}}(I_{n}|B)$, then $A^{-1}=B$
>3. Given $Ax=b$, $A\in M_{n\times n}$
>   If A is invertible, then $Ax=b$ has one unique solution & precisely, $x=A^{-1}b$

>[!Theorem 1]
>The inverse matrix, if it exists, is unique. That means, given $A \in M_{n\times n}$ if $B_{1},B_{2}$ are inverses of A, then $B_{1}=B_{2}$. Then we denote $A^{-1}$ the inverse matrix of A
>
>**Proof:**
>Assuming $B_{1}$ and $B_{2}$ is the inverse matrix of A, we have:
>$$\left\{ 
>\begin{array}{l} 
AB_{1}=B_{1}A=I_{n} \\
AB_{2}=B_{2}A=I_{n}
\end{array}
\right.$$
Hence, with $AB_{1}=I_{n}$
$\Leftrightarrow B_{2}AB_{1}=B_{2}B_{1}A\Leftrightarrow B_{2}I_{n}=B_{2}$

>[!Theorem 2]
>1. If A is invertible then $A^T$ is invertible. More precisely:
>   $$(A^T)^{-1}=(A^{-1})^T$$
>2. If $A$ is invertible, then $A^{-1}$ is invertible. Moreover, we have $(A^{-1})^{-1}=A$
>3. If A, B are invertible, then $A.B$ is invertible. Moreover, we have $(AB)^{-1}=B^{-1}A^{-1}$
>4.  If A is invertible & $\lambda \neq{0},\,\lambda \in \mathbb{R}$ then, $\lambda A$ is invertible & $(\lambda A)^{-1}=\frac{1}{\lambda}A^{-1}$

.87