## 🧮 [[1. Determinants & Invertibility]]

### 💡 Core Idea
A square matrix $A \in M_{n\times n}$ is **invertible** iff $\det(A) \neq 0$.

### 🧠 Strategy on Exam Day
1. **Simplify before expanding.** Use row/column ops to create zeros.
2. **Use cofactor expansion wisely.** Expand along a row/column with the most zeros.
3. **Remember:** If a row or column is multiplied by $k$, $\det(A)$ scales by $k$.

---

### 🧩 Example 1 — 3×3 Determinant
Find $\det(A)$ for  
$$
A=\begin{bmatrix}
2&1&3\\
0&4&-2\\
1&-1&1
\end{bmatrix}
$$

#### Step 1: Expand along row 1 (since it’s simple):
$$
\det(A)=2
\begin{vmatrix}
4&-2\\
-1&1
\end{vmatrix}
-1
\begin{vmatrix}
0&-2\\
1&1
\end{vmatrix}
+3
\begin{vmatrix}
0&4\\
1&-1
\end{vmatrix}
$$

#### Step 2: Compute minors
$$
2[(4)(1)-(-2)(-1)]-1[(0)(1)-(-2)(1)]+3[(0)(-1)-(4)(1)]
$$
$$
=2(4-2)-1(0+2)+3(0-4)=4-2-12=\boxed{-10}
$$

✅ **Answer:** $\det(A)=-10 \neq 0 \Rightarrow A$ is invertible.

---

### ⚙️ Example 2 — Cramer’s Rule
Solve the system:
$$
\begin{cases}
x+y+z=6\\
2x+3y+z=10\\
x+2y+3z=13
\end{cases}
$$

#### Step 1: Coefficient Matrix
$$
A=\begin{bmatrix}
1&1&1\\
2&3&1\\
1&2&3
\end{bmatrix},\quad
b=\begin{bmatrix}
6\\10\\13
\end{bmatrix}
$$

Compute $\det(A)=1(3\cdot3-1\cdot2)-1(2\cdot3-1\cdot1)+1(2\cdot2-3\cdot1)=9-5+1=5$

#### Step 2: Replace columns

$A_x=$ replace col 1 with $b$:
$$
\begin{bmatrix}
6&1&1\\
10&3&1\\
13&2&3
\end{bmatrix}
\Rightarrow \det(A_x)=6(3\cdot3-1\cdot2)-1(10\cdot3-1\cdot13)+1(10\cdot2-13\cdot3)=6(7)-1(17)+1(20-39)=42-17-19=6
$$

Similarly,
$$A_y=\begin{bmatrix}
1&6&1\\
2&10&1\\
1&13&3
\end{bmatrix} \Rightarrow \det(A_y)=1(10\cdot3-1\cdot13)-6(2\cdot3-1\cdot1)+1(2\cdot13-10\cdot1)=17-6(5)+16=17-30+16=3$$

and  
$$A_z=\begin{bmatrix}
1&1&6\\
2&3&10\\
1&2&13
\end{bmatrix} \Rightarrow \det(A_z)=1(3\cdot13-10\cdot2)-1(2\cdot13-10\cdot1)+6(2\cdot3-3\cdot1)=1(39-20)-1(26-10)+6(3)=19-16+18=21$$

#### Step 3: Solve
$$
x=\frac{6}{5},\quad y=\frac{3}{5},\quad z=\frac{21}{5}
$$
✅ **Final Answer:** $\boxed{(x,y,z)=(1.2,0.6,4.2)}$

---

## ⚙️ [[2. Gaussian & Gauss–Jordan Elimination (LES)]]

### 💡 Core Idea
Use elimination to convert $(A|b)$ into **row echelon** or **reduced row echelon form**.

### 🧠 Exam Strategy
1. Write clear row operations: $(R_i \leftrightarrow R_j)$, $(R_i+kR_j)$, etc.
2. Simplify step by step.
3. Mark pivots and free variables.

---

### 🧩 Example 3 — Solve via Gaussian Elimination
$$
\begin{cases}
x+2y+z=2\\
2x+3y+z=4\\
x+y+2z=3
\end{cases}
$$

**Augmented Matrix**
$$
\left[\begin{array}{ccc|c}
1&2&1&2\\
2&3&1&4\\
1&1&2&3
\end{array}\right]
$$

**Step 1:** $R_2-2R_1$, $R_3-R_1$
$$
\Rightarrow
\begin{bmatrix}
1&2&1&2\\
0&-1&-1&0\\
0&-1&1&1
\end{bmatrix}
$$

**Step 2:** $R_3-R_2$
$$
\Rightarrow
\begin{bmatrix}
1&2&1&2\\
0&-1&-1&0\\
0&0&2&1
\end{bmatrix}
$$

**Back substitution**
$$
2z=1\Rightarrow z=\frac12\\
-y-z=0\Rightarrow y=-\frac12\\
x+2y+z=2\Rightarrow x+2(-\frac12)+\frac12=2\Rightarrow x=\frac{5}{2}
$$

✅ **Solution:** $\boxed{(x,y,z)=(2.5,-0.5,0.5)}$

---

## 🧮 [[3. Matrix Properties & Inverses]]

### 💡 Key Relations
1. $(AB)^T = B^T A^T$
2. $(AB)^{-1} = B^{-1}A^{-1}$
3. $(A^T)^{-1} = (A^{-1})^T$

---

### 🧩 Example 4 — Inverse via Gaussian–Jordan
$$
A=\begin{bmatrix}1&2&3\\0&1&4\\2&0&1\end{bmatrix}
$$

**Start:**  
$$
(A|I_3)=
\left[\begin{array}{ccc|ccc}
1&2&3&1&0&0\\
0&1&4&0&1&0\\
2&0&1&0&0&1
\end{array}\right]
$$

Perform $R_3-2R_1$:
$$
\Rightarrow
\begin{bmatrix}
1&2&3&1&0&0\\
0&1&4&0&1&0\\
0&-4&-5&-2&0&1
\end{bmatrix}
$$

Then $R_3+4R_2$:
$$
\begin{bmatrix}
1&2&3&1&0&0\\
0&1&4&0&1&0\\
0&0&11&-2&4&1
\end{bmatrix}
$$

Simplify: $R_3/11$
$$
R_3=\begin{bmatrix}0&0&1&-\frac{2}{11}&\frac{4}{11}&\frac{1}{11}\end{bmatrix}
$$
Back substitute to eliminate above pivots.

✅ After full reduction:
$$
A^{-1}=
\boxed{
\begin{bmatrix}
\frac{6}{11}&-\frac{3}{11}&-\frac{5}{11}\\
\frac{8}{11}&-\frac{4}{11}&-\frac{7}{11}\\
-\frac{2}{11}&\frac{4}{11}&\frac{1}{11}
\end{bmatrix}}
$$

> ✅ *Always verify quickly by multiplying $AA^{-1}$.*

---

## 🧭 [[4. Vectors & Orthogonality]]

### 💡 Exam Key
- Orthogonal if $\vec{u}\cdot\vec{v}=0$
- Length $|\vec{u}|=\sqrt{u_1^2+u_2^2+\dots+u_n^2}$
- Projection: $\text{proj}_{\vec{v}}(\vec{u})=\frac{\vec{u}\cdot\vec{v}}{|\vec{v}|^2}\vec{v}$

---

### 🧩 Example 5 — Dot Product & Angle
Let $\vec{u}=(2,1,-1)$ and $\vec{v}=(1,-3,2)$.

Compute:
$$
\vec{u}\cdot\vec{v}=2(1)+1(-3)+(-1)(2)=-3\\
|\vec{u}|=\sqrt{6},\quad |\vec{v}|=\sqrt{14}\\
\cos\theta=\frac{-3}{\sqrt{6}\sqrt{14}}\Rightarrow \boxed{\theta\approx112.9^\circ}
$$
✅ *Obtuse angle → negative dot product.*

---

## 🌌 [[5. Vector Spaces & Subspaces]]

### 💡 Concept Check
A set $W\subseteq\mathbb{R}^n$ is a **subspace** if:
1. $\vec{0}\in W$
2. Closed under addition
3. Closed under scalar multiplication

---

### 🧩 Example 6 — Subspace & Basis
Let $W=\{(x,y,z)\in\mathbb{R}^3\mid x+2y+z=0\}$.

Express $W$ in vector form.

$$
x=-2y-z \Rightarrow 
\begin{bmatrix}
x\\y\\z
\end{bmatrix}
=y\begin{bmatrix}-2\\1\\0\end{bmatrix}
+z\begin{bmatrix}-1\\0\\1\end{bmatrix}
$$
Hence,  
**Basis:** $$\left\{
\begin{bmatrix}-2\\1\\0\end{bmatrix},
\begin{bmatrix}-1\\0\\1\end{bmatrix}
\right\}$$  
**Dimension:** $\boxed{2}$



