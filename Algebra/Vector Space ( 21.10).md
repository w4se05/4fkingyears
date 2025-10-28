## [[Definition]] 🧮
A **vector space** (or **linear space**) over $\mathbb{R}$ is a non-empty set $V$ equipped with two operations:

1️⃣ **Vector Addition**:  
$\forall \vec{u}, \vec{v} \in V,\; \vec{u} + \vec{v} \in V$

2️⃣ **Scalar Multiplication**:  
$\forall \alpha \in \mathbb{R},\; \vec{u} \in V \Rightarrow \alpha \vec{u} \in V$

such that the following **8 axioms** hold for all $\vec{u}, \vec{v}, \vec{w} \in V$ and $\alpha,\beta \in \mathbb{R}$:

| # | Property | Expression |
|---|-----------|-------------|
| 1 | Commutativity | $\vec{u}+\vec{v} = \vec{v}+\vec{u}$ |
| 2 | Associativity (add.) | $(\vec{u}+\vec{v})+\vec{w} = \vec{u}+(\vec{v}+\vec{w})$ |
| 3 | Additive identity | $\exists \vec{0}\in V: \vec{u}+\vec{0}=\vec{u}$ |
| 4 | Additive inverse | $\forall \vec{u}\in V,\; \exists (-\vec{u})\in V$ |
| 5 | Distributivity (scalar over vectors) | $\alpha(\vec{u}+\vec{v})=\alpha\vec{u}+\alpha\vec{v}$ |
| 6 | Distributivity (scalars) | $(\alpha+\beta)\vec{u}=\alpha\vec{u}+\beta\vec{u}$ |
| 7 | Associativity (scalar mult.) | $\alpha(\beta\vec{u})=(\alpha\beta)\vec{u}$ |
| 8 | Scalar identity | $1\cdot\vec{u}=\vec{u}$ |

---

## [[Examples of Vector Spaces]] 🧩

| Name | Description | Typical Element |
|------|--------------|------------------|
| $\mathbb{R}^n$ | n-tuples of real numbers | $(x_1, x_2, ..., x_n)$ |
| $M_{m\times n}$ | all $m\times n$ matrices | $(a_{ij})_{m\times n}$ |
| $\mathbb{P}_n$ | polynomials of degree ≤ n | $a_0 + a_1x + \dots + a_nx^n$ |
| $C[a,b]$ | continuous real functions on [a,b] | $f(x)$ |

---

## [[Subspace]] 🧭
A subset $U\subseteq V$ is a **subspace** of $V$ if:

1. $\vec{0}\in U$  
2. $\forall \vec{u},\vec{v}\in U,\; \vec{u}+\vec{v}\in U$  
3. $\forall \alpha\in\mathbb{R},\;\vec{u}\in U\Rightarrow \alpha\vec{u}\in U$

> 💡 Subspaces themselves are vector spaces (under the same operations).

---

### 🧩 Example 1 — Checking Subspace  

Let $V=\mathbb{R}^3$,  
and $U=\{(x,y,z)\in\mathbb{R}^3\;|\;x+y+z=0\}$.

✅ Check:
- $(0,0,0)\in U$  
- Closed under addition:  
  $(x_1+y_1+z_1=0,\;x_2+y_2+z_2=0)\Rightarrow (x_1+x_2)+(y_1+y_2)+(z_1+z_2)=0$  
- Closed under scalar multiplication:  
  $\alpha(x+y+z)=\alpha0=0$

✅ Hence $U$ is a **subspace of $\mathbb{R}^3$**.

---

## [[Linear Combination, Span, and Independence]] 🧩

### Linear Combination  
A vector $\vec{v}$ is a **linear combination** of $\vec{v}_1,\dots,\vec{v}_k$ if  
$$
\vec{v} = c_1\vec{v}_1 + c_2\vec{v}_2 + \dots + c_k\vec{v}_k
$$
for some scalars $c_1,\dots,c_k\in\mathbb{R}$.

---

### Span  
The **span** of $\{\vec{v}_1,\dots,\vec{v}_k\}$ is the set of *all* linear combinations of those vectors:
$$
\text{span}\{\vec{v}_1,\dots,\vec{v}_k\} = \{c_1\vec{v}_1 + \dots + c_k\vec{v}_k \mid c_i\in\mathbb{R}\}
$$

> 💡 The span is always a **subspace** of $V$.

---

### Linear Independence  
$\{\vec{v}_1,\dots,\vec{v}_k\}$ is **linearly independent** if  
$$
c_1\vec{v}_1 + c_2\vec{v}_2 + \dots + c_k\vec{v}_k = \vec{0}
$$
⟹ $c_1=c_2=\dots=c_k=0$

Otherwise, the set is **linearly dependent**.

---

### 🧩 Example 2 — Checking Independence  

Are $\vec{v}_1=(1,2,3)$, $\vec{v}_2=(2,4,6)$, and $\vec{v}_3=(1,0,1)$ independent in $\mathbb{R}^3$?

Set up:
$$
c_1\vec{v}_1 + c_2\vec{v}_2 + c_3\vec{v}_3 = \vec{0}
$$
⟹  
$$
c_1(1,2,3) + c_2(2,4,6) + c_3(1,0,1) = (0,0,0)
$$
⟹$$\begin{cases}
c_1 + 2c_2 + c_3 = 0\\
2c_1 + 4c_2 + 0c_3 = 0\\
3c_1 + 6c_2 + c_3 = 0
\end{cases}
$$
Row-reduce:
$$
\begin{bmatrix}
1 & 2 & 1\\
2 & 4 & 0\\
3 & 6 & 1
\end{bmatrix}
\rightarrow
\begin{bmatrix}
1 & 2 & 1\\
0 & 0 & -2\\
0 & 0 & -2
\end{bmatrix}
$$
⟹ $c_3=0,\;c_1=-2c_2$ ⟹ **dependent** (since $c_2$ free).  
✅ $\boxed{\text{Vectors are linearly dependent.}}$

---

## [[Basis and Dimension]] 🧠

A **basis** of a vector space $V$ is a linearly independent set that **spans** $V$.

The **dimension** of $V$, denoted $\dim(V)$, is the number of vectors in any basis.

> 💡 Every basis of a finite-dimensional vector space has the same number of vectors.

Examples:
- $\dim(\mathbb{R}^n)=n$
- $\dim(M_{m\times n})=mn$
- $dim(P_{n}(x))=n+1$
- $dim(l^{\infty})=\infty$

---

### 🧩 Example 3 — Finding a Basis  

Let $V=\text{span}\{(1,1,0),(2,0,1),(3,1,1)\} \subseteq \mathbb{R}^3$.  
Find a basis.

Build matrix with these as rows:
$$
\begin{bmatrix}
1&1&0\\
2&0&1\\
3&1&1
\end{bmatrix}
\rightarrow
\begin{bmatrix}
1&1&0\\
0&-2&1\\
0&0&1
\end{bmatrix}
$$
→ Rank = 3 → all independent.

✅ Basis = $\{(1,1,0),(2,0,1),(3,1,1)\}$  
✅ $\dim(V)=3$

---

## [[Row, Column, and Null Spaces]] 🧾

For $A\in M_{m\times n}$:

| Space | Definition | Dimension |
|--------|-------------|------------|
| Row Space | span of rows of $A$ | = rank(A) |
| Column Space | span of columns of $A$ | = rank(A) |
| Null Space | $\{\vec{x}\mid A\vec{x}=\vec{0}\}$ | = $n-\text{rank}(A)$ |

---

### 🧩 Example 4 — Null Space  

$$
A=\begin{bmatrix}
1&2&1\\
2&4&2
\end{bmatrix}
$$
$\text{Row 2}=2\times\text{Row 1}$ ⟹ rank = 1.

Solve $A\vec{x}=\vec{0}$:
$$
x_1 + 2x_2 + x_3 = 0 \Rightarrow x_1 = -2x_2 - x_3
$$
Let $x_2=s,\;x_3=t$:
$$
\vec{x} = s(-2,1,0) + t(-1,0,1)
$$
✅ Null space basis = $\{(-2,1,0),(-1,0,1)\}$  
✅ $\dim(\text{Nul}(A)) = 2$

---

## [[Linear Transformation]] 🔄

A mapping $T:V\to W$ between vector spaces is **linear** if:
1. $T(\vec{u}+\vec{v})=T(\vec{u})+T(\vec{v})$
2. $T(c\vec{u})=cT(\vec{u})$

### Matrix Representation  
If $T:\mathbb{R}^n\to\mathbb{R}^m$, then  
$\exists A\in M_{m\times n}$ such that  
$$
T(\vec{x}) = A\vec{x}
$$

> 💡 Every linear transformation corresponds to a matrix, and vice versa.

---

### 🧩 Example 5 — Transformation and Kernel  

Let $T:\mathbb{R}^3\to\mathbb{R}^2$ given by  
$T(x,y,z)=(x+y,2y+z)$.

Matrix form:
$$
A=
\begin{bmatrix}
1&1&0\\
0&2&1
\end{bmatrix}
$$

Find $\ker(T)$ (null space):

Solve $A\vec{x}=\vec{0}$:
$$
\begin{cases}
x+y=0\\
2y+z=0
\end{cases}
\Rightarrow x=-y,\;z=-2y
$$
$$\implies\vec{x}=y(-1,1,-2)$$ 
✅ $\ker(T)=\text{span}\{(-1,1,-2)\}$  
✅ $\dim(\ker T)=1$

---

## [[Rank–Nullity Theorem]] 🧮
For any linear transformation $T:V\to W$:
$$
\dim(V) = \text{rank}(T) + \text{nullity}(T)
$$

> Rank = $\dim(\text{Im }T)$,  
> Nullity = $\dim(\ker T)$.

---

## [[Exam-Style Tip Sheet]] 🎓  

✅ When asked “Is it a subspace?”, always check **three closure rules**.  
✅ Use **row reduction** to test independence or find a basis.  
✅ Keep **null space basis** vectors **parametric** (free-variable = 1).  
✅ Always mention **dimension** in your final answer.  
✅ If $A\in M_{n\times n}$ and $\det(A)\neq0$, its columns form a **basis of $\mathbb{R}^n$**.  
✅ Relate transformations to their matrix representation explicitly.  

