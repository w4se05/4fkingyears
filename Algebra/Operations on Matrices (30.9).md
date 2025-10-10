>[!Matrix] 
>Given 2 numbers m and n
A matrix A of size $m \times n$ consists $m.n$ entries so that
> - each row has exactly $n$ entries
> - each col has exactly $m$ entries
> - 
>**Denote:** $M_{m \times n} =$ Set of all Matrices of size $m \times n$
> 
>Eg:
>A matrix of size 2x3: $\begin{pmatrix}
1 &  2 & 3 \\
4& 4& 6 \\
\end{pmatrix}$

> [!Definition] Scalar Multiplication
> $$\lambda \in \mathbb{R},\,A=\begin{pmatrix}
> a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
. \\
. \\
a_{m_{1}} & a_{m_{2}}& \dots &a_{m_{n}} 
>\end{pmatrix}=(a_{ij})_{m \times n}$$
>Where $a_{ij}$ is the entry at row i and col j of A
>$$\lambda.A=(\lambda.a_{ij})_{m \times n}$$
>
>$$\mathbb{R} \times M_{m \times n} \to M_{m \times n}$$
>$$(\lambda,\,A) \to \lambda.A=(\lambda.a_{ij})_{m \times n}$$
>

>[!Addition]
>$$M_{m \times n} + M_{m \times n} \to M_{m \times n}$$
>$$(A,B) \to A+B = (a_{ij}+b_{ij})_{m \times n}$$
>With:
>- A=$(a_{ij})_{m \times n}$
>- B=$(b_{ij})_{m \times n}$

>[!Definition] Transposed Matrix
>$$M_{m \times n} \to M_{n \times m}$$
>$$A\to(b_{ij})_{n \times m}$$
>With:
>- $b_{ij}=a_{ji} \;\forall\; \begin{split}
i=1,2,\dots n\\
j=1,2, \dots m
\end{split}$
>
>Then we denote $A^T$ the transposed matrix of A

>[!Properties]
>Given A, B, C$\in M_{m \times n},\; \alpha,\, \beta \in \mathbb{R}$
>1. $A+B=B+A$ (communicative)
>2. $A+(B+C)=(A+B)+C$ (associative)
>3. $\alpha(A+B)=\lambda A+\lambda B$ (distributive)
>4. $(\alpha+\beta).A=\lambda A+\beta A$
>5. $A+[]=A=[]+A;\;[]=(0)_{m\times n}$
>6. $(A^T)^T=A$
>7. $(\alpha A)^T=\alpha A^T$
>8. $(A+B)^T=A^T+B^T$ (homework)

>[!Definition] Matrix Multiplication
>$$M_{m\times \mathbf{n}} \times M_{\mathbf{n} \times p}\to M_{m\times p}$$
>$$(A,B)\to A.B=(c_{ij})_{m \times p}$$
>With:
>- $A=(a_{ij})_{m\times n}$
>- $B=(b_{ij})_{n\times p}$
>  
>**$c_{ij} = \text{Inner Product of row i of A and col j of B}$**
>
>E.g:
>$$A=\begin{pmatrix}
2 & 0 &-1 \\
4 & -5 & 2 \\
\end{pmatrix} \in M_{2 \times 3}$$
>$$B=\begin{pmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7  & 8\\
9 & 10 & 11 & 12
\end{pmatrix} \in M_{3 \times 4}$$
>$$\begin{aligned}
>A.B&=\begin{pmatrix}
2 & 0 &-1 \\
4 & -5 & 2 \\
\end{pmatrix} \times \begin{pmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7  & 8\\
9 & 10 & 11 & 12
\end{pmatrix} \\ \\
&=\begin{pmatrix}
-7&-6&-5&-4 \\
-3&-2&-1&0
\end{pmatrix} \in M_{2 \times 4}
\end{aligned}$$
>
>**Properties:**
> - $A.B\neq B.A$ in general
> - $A.(B+C)=AB+AC$ (homework)
> - $(A.B)^T=B^T.A^T$ (homework)

>[!Definition] Application of Matrices
>$$\left\{
>\begin{array}{l} 
a_{11}x_{1} +a_{12}x_{2} +\dots+a_{1n}x_{n}=b_{1}  \\
. \\
. \\
. \\
a_{m1}x_{1}  a_{m{2}}x_{2} + \dots +a_{mn}x_{n}=b_{m}
\end{array}
\right. \leftrightarrow (A|B)$$
>$$\Leftrightarrow (a_{11}\quad a_{12} \quad a_{13} \quad \dots \quad a_{1n}) \begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}\\
. \\
. \\
x_{n}
\end{pmatrix}=b_{1}$$
>$$\Leftrightarrow m^{th}\text{ row of A}.\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}\\
. \\
. \\
x_{n}
\end{pmatrix}=b_{m}$$
>Hence, we can represent a LES as
>$$A\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}\\
. \\
. \\
x_{n}
\end{pmatrix}=\begin{pmatrix}
b_{1} \\
b_{2} \\
b_{3}\\
. \\
. \\
b_{m}
\end{pmatrix}\quad \Leftrightarrow\quad Ax=b$$

>[!Definition] Some Popular Matrices
>1. Square Matrix: $M_{n \times n}$ 
>2. Symmetric Matrix: $A \in M_{n\times n}$, $A=A^T$
>3. Identity Matrix: Square Matrix whose diagonal are 1s and others are 0s.
>   Denote $I_{n}$ the identity matrix of size $n\times n$
