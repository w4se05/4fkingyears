## 🔹 Linear Equation
A **linear equation in n variables** $x_{1}, x_{2}, \dots, x_{n}$ is an equation of the form:
$$
a_{1}x_{1} + a_{2}x_{2} + \dots + a_{n}x_{n} = b \quad (1)
$$

where  
$\begin{split}
&a_{1}, a_{2}, \dots, a_{n} \in \mathbb{R} \text{ are the **coefficients** of (1)} \\
&b \in \mathbb{R} \text{ is the **right-hand side** of (1)}
\end{split}$

---

## 🔹 Linear Equation System (LES)
A **system of m linear equations in n variables** is written as:
$$
\begin{cases}
a_{11}x_{1} + a_{12}x_{2} + \dots + a_{1n}x_{n} = b_{1} \\
a_{21}x_{1} + a_{22}x_{2} + \dots + a_{2n}x_{n} = b_{2} \\
\vdots \\
a_{m1}x_{1} + a_{m2}x_{2} + \dots + a_{mn}x_{n} = b_{m}
\end{cases}
\quad (2)
$$

with  
$$
a_{ij} \in \mathbb{R}, \quad 
\begin{cases}
i = 1, 2, \dots, m \\
j = 1, 2, \dots, n
\end{cases}
$$

Here:
- $a_{ij}$ are called **coefficients**
- $b_{1}, b_{2}, \dots, b_{m}$ are the **right-hand sides**

---

## 🔹 Solution Set of a LES
A **solution** to (2) is an assignment of real numbers $s_{1}, s_{2}, \dots, s_{n}$ to variables $x_{1}, x_{2}, \dots, x_{n}$ so that all equations in (2) are satisfied.

Written in **vector form**:
$$
\begin{pmatrix}
x_{1} \\ x_{2} \\ \vdots \\ x_{n}
\end{pmatrix}
=
\begin{pmatrix}
s_{1} \\ s_{2} \\ \vdots \\ s_{n}
\end{pmatrix}
$$

---

## 🔹 Consistency of a LES
- The system (2) is **consistent** if it has *at least one solution*.  
- Otherwise, it is **inconsistent**.

---

## 🔹 Equivalence of Two LESs
Two systems of linear equations are **equivalent** if they have the **same solution set**.

**Elementary operations** that do **not change** the solution set:
1. Multiplying an equation by a nonzero constant  
2. Adding a multiple of one equation to another  
3. Interchanging two equations

---

## 🔹 Coefficient and Augmented Matrices
Given the system (2):

**Coefficient matrix:**
$$
A =
\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

**Augmented matrix:**
$$
(A|b) =
\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} & | & b_{1} \\
a_{21} & a_{22} & \dots & a_{2n} & | & b_{2} \\
\vdots & \vdots & \ddots & \vdots & | & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn} & | & b_{m}
\end{pmatrix}
$$

---

## 🔹 Row Echelon Form (REF) and Gaussian Elimination
The **Row Echelon Form (REF)** of a LES, denoted $(A^* | b^*)$, looks like:
$$
\begin{pmatrix}
a_{11} & a_{12} & a_{13} & \dots & a_{1n} & | & b_{1} \\
0 & a_{22} & a_{23} & \dots & a_{2n} & | & b_{2} \\
0 & 0 & a_{33} & \dots & a_{3n} & | & b_{3} \\
\vdots & \vdots & \vdots & \ddots & \vdots & | & \vdots \\
0 & 0 & 0 & \dots & a_{mn} & | & b_{m}
\end{pmatrix}
$$

Each $a_{ii}$ is a **pivot** (the leading nonzero entry of its row).  
All entries **below each pivot** are zero.

### ✅ A matrix is in REF if:
1. All-zero rows (if any) are at the bottom.  
2. In each nonzero row, the **pivot** is the first nonzero entry, and all entries below it are zero.  
3. Pivots move **rightward** as you move down the rows.  
4. Non-pivot (free) variables can take any value; pivot variables depend on them.

After transforming a system to REF, we solve by **back-substitution**, working upward from the last pivot row.  
This process is called **Gaussian Elimination**.

**Note:**
- $(A|b)$ is inconsistent if the REF has a zero row in $A$ but the corresponding $b_i$ is nonzero.  
- The number of **free variables** equals the **dimension** of the solution space.

---

## 🔹 Gaussian–Jordan Elimination
This method extends Gaussian elimination to produce the **Reduced Row Echelon Form (RREF)**:
$$
(A|b) 
\xrightarrow{\text{GE}} (A^*|b^*) 
\xrightarrow[\text{top-down}]{\text{Elimination}} 
(A^{**}|b^{**})
$$

where:
- All pivots are **1**
- All entries **above and below pivots** are **0**

This simplifies reading off solutions directly.

---

## 🔹 Rank of a Matrix
Given $A$, let $A^{**}$ be its row echelon form.  
Then the **rank** of $A$ is:
$$
r(A) = \text{number of nonzero rows in } A^{**}
$$

**Note:**  
A system is **consistent** if and only if  
$$
r(A) = r(A|b)
$$

---

