## 🧩 Definition — Matrix
Given two numbers $m$ and $n$,  
a **matrix** $A$ of size $m \times n$ consists of $m \cdot n$ entries such that:

- Each **row** has exactly $n$ entries  
- Each **column** has exactly $m$ entries  

**Denote:** $M_{m \times n}$ — the set of all matrices of size $m \times n$.

**Example:**  
A matrix of size $2 \times 3$  
$$
A = \begin{pmatrix}
1 & 2 & 3 \\
4 & 4 & 6
\end{pmatrix}
$$

---

## ⚙️ Scalar Multiplication
Let $\lambda \in \mathbb{R}$ and  
$$
A = 
\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
= (a_{ij})_{m \times n}
$$

where $a_{ij}$ is the entry at **row i** and **column j** of $A$.

Then,  
$$
\lambda A = (\lambda a_{ij})_{m \times n}
$$

which defines the map:  
$$
\mathbb{R} \times M_{m \times n} \to M_{m \times n}, \quad (\lambda, A) \mapsto \lambda A
$$

---

## ➕ Matrix Addition
$$
M_{m \times n} + M_{m \times n} \to M_{m \times n}
$$

$$(A, B) \mapsto A + B = (a_{ij} + b_{ij})_{m \times n}$$

Where:  
- $A = (a_{ij})_{m \times n}$  
- $B = (b_{ij})_{m \times n}$  

---

## 🔁 Transposed Matrix
The **transpose** of $A \in M_{m \times n}$ is defined as:  
$$
A^T = (b_{ij})_{n \times m}, \quad \text{where } b_{ij} = a_{ji}
$$

for all  
$$
i = 1, 2, \dots, n \\
j = 1, 2, \dots, m
$$

Thus,  
$$
A \in M_{m \times n} \implies A^T \in M_{n \times m}
$$

---

## 🧠 Properties of Matrices
Given $A, B, C \in M_{m \times n}$ and $\alpha, \beta \in \mathbb{R}$:

1. $A + B = B + A$ (Commutative)  
2. $A + (B + C) = (A + B) + C$ (Associative)  
3. $\alpha(A + B) = \alpha A + \alpha B$ (Distributive)  
4. $(\alpha + \beta)A = \alpha A + \beta A$  
5. $A + 0 = 0 + A = A$, where $0 = (0)_{m \times n}$  
6. $(A^T)^T = A$  
7. $(\alpha A)^T = \alpha A^T$  
8. $(A + B)^T = A^T + B^T$ (Homework)

---

## ✖️ Matrix Multiplication
Matrix multiplication is defined by  
$$
M_{m \times \mathbf{n}} \times M_{\mathbf{n} \times p} \to M_{m \times p}
$$

$$(A, B) \mapsto AB = (c_{ij})_{m \times p}$$  

Where:
- $A = (a_{ij})_{m \times n}$  
- $B = (b_{ij})_{n \times p}$  

Each element $c_{ij}$ is the **inner product** of the *i-th row* of $A$ and the *j-th column* of $B$.

---

### 🧮 Example
$$
A = 
\begin{pmatrix}
2 & 0 & -1 \\
4 & -5 & 2
\end{pmatrix} \in M_{2 \times 3}, \quad
B = 
\begin{pmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7 & 8 \\
9 & 10 & 11 & 12
\end{pmatrix} \in M_{3 \times 4}
$$

Then:  
$$
\begin{aligned}
AB &= 
\begin{pmatrix}
2 & 0 & -1 \\
4 & -5 & 2
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7 & 8 \\
9 & 10 & 11 & 12
\end{pmatrix} \\
\\
&=
\begin{pmatrix}
-7 & -6 & -5 & -4 \\
-3 & -2 & -1 & 0
\end{pmatrix} \in M_{2 \times 4}
\end{aligned}
$$

---

### ⚙️ Properties of Matrix Multiplication
- In general, $AB \neq BA$  
- $A(B + C) = AB + AC$ (Homework)  
- $(AB)^T = B^T A^T$ (Homework)

---

## 🧩 Application — Linear Equation Systems
A system of $m$ linear equations in $n$ unknowns:
$$
\begin{cases}
a_{11}x_{1} + a_{12}x_{2} + \dots + a_{1n}x_{n} = b_{1} \\
\vdots \\
a_{m1}x_{1} + a_{m2}x_{2} + \dots + a_{mn}x_{n} = b_{m}
\end{cases}
$$

can be represented as the **augmented matrix** $(A | B)$ or equivalently as:  
$$
A
\begin{pmatrix}
x_{1} \\
x_{2} \\
\vdots \\
x_{n}
\end{pmatrix}
=
\begin{pmatrix}
b_{1} \\
b_{2} \\
\vdots \\
b_{m}
\end{pmatrix}
\quad \Leftrightarrow \quad
Ax = b
$$

---

## 🏷️ Common Types of Matrices
1. **Square Matrix:** $A \in M_{n \times n}$  
2. **Symmetric Matrix:** $A \in M_{n \times n}$ such that $A = A^T$  
3. **Identity Matrix:** Square matrix with diagonal entries = 1, others = 0  
   - Denoted $I_n$ for an identity matrix of size $n \times n$

---
