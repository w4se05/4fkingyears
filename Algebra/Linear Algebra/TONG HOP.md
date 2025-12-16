# Linear Algebra: Exercise Tips & Tricks

## 🧠 Part 1: Linear Systems & Matrices
**Focus:** Solving systems quickly and handling determinants.

### 1. The "Pivot Counting" Shortcut
When asked about the number of solutions for $[A|b]$:
* **No Solution:** Is there a pivot in the last column (the $b$ column)?
    * Example: $[0 \ 0 \ 0 \ | \ 5]$ means $0 = 5$ (Impossible).
* **Unique Solution:** Does every variable column have a pivot? ($r = n$)
* **Infinite Solutions:** Are there variable columns without pivots? (Free variables).

### 2. Inverse Matrix Tricks
* **$2 \times 2$ Shortcut:**
    $$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \implies A^{-1} = \frac{1}{ad-bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$
    * Swap diagonal, negate off-diagonal, divide by determinant.
* **Check Invertibility quickly:** A matrix is singular (non-invertible) if:
    * Determinant is 0.
    * One row is a multiple of another.
    * It has a row or column of zeros.

### 3. Determinant Computation Strategies
Don't blindly use cofactor expansion.
* **Row Reduce first:** Use row operations to get a zero in a column before expanding.
    * *Tip:* Adding a multiple of a row to another **does not change** the determinant.
* **Triangular Matrix:** If you can easily get to Upper Triangular form, just multiply the diagonal entries.
* **Block Matrices:** $\det \begin{pmatrix} A & B \\ 0 & D \end{pmatrix} = \det(A)\det(D)$.

---

## 🔗 Part 2: Vector Spaces
**Focus:** Identifying subspaces and finding bases.

### 1. The "Subspace Check" Cheat
When checking if $W$ is a subspace:
* **Visual Check:** Does it look like a line/plane through the origin? $\to$ Yes.
* **Equation Check:**
    * Homogeneous linear equations ($3x - y + 2z = 0$)? $\to$ **YES**.
    * Constants ($x + y = 1$)? $\to$ **NO** (fails Zero vector check).
    * Inequalities ($x \ge 0$)? $\to$ **NO** (fails scalar mult by negative).
    * Quadratic/nonlinear ($x^2 + y = 0$)? $\to$ **NO**.

### 2. Independence vs. Dependence
* **The Determinant Test:** If you have $n$ vectors in $\mathbb{R}^n$, put them in a matrix. $\det \neq 0 \implies$ Independent.
* **The "Too Many Vectors" Rule:** If you have $k$ vectors in $\mathbb{R}^n$ and $k > n$, they are **automatically dependent**.
* **The "Multiple" Rule:** Two vectors are dependent iff one is a scalar multiple of the other.

### 3. Finding Bases (The Algorithm)
* **Basis for Span(S):** Put vectors as **columns** in a matrix $A$. Row reduce. Pick the columns of the **original matrix A** that correspond to the pivot positions.
* **Basis for Null Space (Solution Space):**
    1.  Solve $Ax=0$ to find the general solution (e.g., $x = s\vec{u} + t\vec{v}$).
    2.  The vectors $\vec{u}$ and $\vec{v}$ form the basis.
    3.  Dimension = number of free variables.

---

## 🔢 Part 3: Linear Maps
**Focus:** Matrix representations and Kernel/Image.

### 1. Matrix Representation Shortcut
To find the matrix $A$ for transformation $T$:
* **Column 1:** Calculate $T(1, 0, \dots)$.
* **Column 2:** Calculate $T(0, 1, \dots)$.
* ...and so on.
* *Example:* $T(x,y) = (2x, x+y)$.
    * $T(1,0) = (2, 1)$. Col 1 is $\begin{pmatrix} 2 \\ 1 \end{pmatrix}$.
    * $T(0,1) = (0, 1)$. Col 2 is $\begin{pmatrix} 0 \\ 1 \end{pmatrix}$.
    * $A = \begin{pmatrix} 2 & 0 \\ 1 & 1 \end{pmatrix}$.

### 2. Kernel and Image
* **Kernel:** Just solve the homogeneous system $[A | 0]$.
    * If the only solution is zero, $T$ is one-to-one (injective).
* **Image (Range):** It's just the Column Space of $A$.
    * If Rank = Rows, $T$ is onto (surjective).

### 3. Linearity Check
To disprove linearity, you only need one counter-example.
* **Zero Test:** Calculate $T(0)$. If $T(0) \neq 0$, it is **NOT** linear. (e.g., $T(x) = 2x + 1$).
* **Square/Root Test:** If you see $x^2$, $\sqrt{x}$, $\sin(x)$, etc., it is usually **NOT** linear.