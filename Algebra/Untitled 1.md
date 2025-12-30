# VGU - Final Exam: Algebra (Advanced Mock Test) - SOLUTIONS
**Exam Level:** Advanced / Distinction
**Semester:** Simulation 2025

---

## 1. Binary Choice Questions (Conceptual)

1.  **False ($f$)**
    * *Reasoning:* "Zero divisors" exist in matrix algebra. It is possible for $AB = 0$ even if $A \neq 0$ and $B \neq 0$.
    * *Counter-example:* $A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$, $B = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$. Then $AB = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$.

2.  **True ($t$)**
    * *Reasoning:* This follows from the **Rank-Nullity Theorem**: $\dim(\ker(T)) + \dim(\text{Im}(T)) = n$.
    * If $\ker(T) = \{0\}$, then $\dim(\ker) = 0$.
    * Thus, $0 + \dim(\text{Im}(T)) = n$, which implies $\dim(\text{Im}(T)) = n$. Since the image is a subspace of $\mathbb{R}^n$ with dimension $n$, the image *is* $\mathbb{R}^n$, so $T$ is surjective.

3.  **False ($f$)**
    * *Reasoning:* Modular congruence ($a \equiv b \pmod n$) is an **Equivalence Relation** (Reflexive, Symmetric, Transitive), not a Partial Ordering.
    * Partial orderings must be *Anti-symmetric* (if $aRb$ and $bRa$, then $a=b$). In modular arithmetic, $2 \equiv 7$ and $7 \equiv 2 \pmod 5$, but $2 \neq 7$.

4.  **True ($t$)**
    * *Reasoning:* The modular multiplicative inverse $d = e^{-1} \pmod{\phi(n)}$ only exists if $\gcd(e, \phi(n)) = 1$. If they share a factor, the congruence $ed \equiv 1 \pmod{\phi(n)}$ has no solution for $d$.

5.  **False ($f$)**
    * *Reasoning:* Linear dependence means **at least one** vector is a linear combination of the others. It does not imply specifically that $v_3$ depends on $v_1, v_2$.
    * *Counter-example:* Let $v_1 = (1,0)$, $v_2 = (2,0)$, $v_3 = (0,1)$. The set is dependent because $v_2 = 2v_1$. However, $v_3$ cannot be formed by $v_1$ and $v_2$.

---

## 2. Short Answer Questions (Calculations & Logic)

**(a) $k = \frac{1 \pm \sqrt{61}}{6}$**
* *Explanation:* A matrix is not invertible (singular) if $\det(A) = 0$.
    $$
    \det(A) = 1 \begin{vmatrix} 1 & k \\ 1 & 1 \end{vmatrix} - k \begin{vmatrix} 0 & k \\ 3 & 1 \end{vmatrix} + 2 \begin{vmatrix} 0 & 1 \\ 3 & 1 \end{vmatrix}
    $$
    $$= 1(1 - k) - k(0 - 3k) + 2(0 - 3)$$
    $$= 1 - k + 3k^2 - 6$$
    $$= 3k^2 - k - 5 = 0$$
    Using quadratic formula: $k = \frac{1 \pm \sqrt{1 - 4(3)(-5)}}{6} = \frac{1 \pm \sqrt{61}}{6}$.

**(b) $M_{R^*} = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 1 \end{pmatrix}$**
* *Explanation:* The relation represents a cycle: $1 \to 2$, $2 \to 3$, $3 \to 1$.
    * Step 1 ($R$): You can go 1 step ($1 \to 2$, etc).
    * Step 2 ($R^2$): You can go 2 steps ($1 \to 3$, etc).
    * Step 3 ($R^3$): You can go 3 steps ($1 \to 1$, etc - Reflexive).
    Since the graph is a strongly connected cycle involving all nodes, eventually every node can reach every other node.

**(c) 28**
* *Explanation:* Expand the dot product formula $||x||^2 = x \cdot x$.
    $$||2u - v||^2 = (2u - v) \cdot (2u - v)$$
    $$= 4(u \cdot u) - 2(u \cdot v) - 2(v \cdot u) + (v \cdot v)$$
    $$= 4||u||^2 - 4(u \cdot v) + ||v||^2$$
    Calculate $u \cdot v = ||u|| ||v|| \cos(\theta) = 3 \cdot 4 \cdot \cos(60^\circ) = 12 \cdot 0.5 = 6$.
    Substitute: $4(3^2) - 4(6) + 4^2 = 4(9) - 24 + 16 = 36 - 24 + 16 = 28$.

**(d) True**
* *Explanation:* The statement says "For every number $x$, there is a number $y$ such that $x^2 + y = 5$."
    We can construct $y$ explicitly: $y = 5 - x^2$. Since subtraction and squaring are defined for all real numbers, $y$ always exists.

**(e) $d = 17$**
* *Explanation:*
    1.  $n = 143 = 11 \times 13$.
    2.  $\phi(n) = (11-1)(13-1) = 10 \times 12 = 120$.
    3.  We need $d$ such that $113d \equiv 1 \pmod{120}$.
    4.  Notice that $113 \equiv -7 \pmod{120}$. So we solve $-7d \equiv 1 \pmod{120}$, or $7d \equiv -1 \equiv 119 \pmod{120}$.
    5.  $d = 119 / 7 = 17$.

---

## 3. Parametric Linear Systems & Subspaces

**(a) Analysis of $\lambda$**
Use Gaussian Elimination on the augmented matrix:
$$
\begin{pmatrix} 1 & 1 & -1 & 1 \\ 2 & 3 & \lambda & 3 \\ 1 & \lambda & 3 & 2 \end{pmatrix}
$$
$R_2 \leftarrow R_2 - 2R_1$: $\begin{pmatrix} 0 & 1 & \lambda+2 & 1 \end{pmatrix}$
$R_3 \leftarrow R_3 - R_1$: $\begin{pmatrix} 0 & \lambda-1 & 4 & 1 \end{pmatrix}$

Now, eliminate the $y$ term in $R_3$ by $R_3 \leftarrow R_3 - (\lambda-1)R_2$:
* $z$-coeff: $4 - (\lambda-1)(\lambda+2) = 4 - (\lambda^2 + \lambda - 2) = 6 - \lambda - \lambda^2 = -(\lambda+3)(\lambda-2)$.
* RHS: $1 - (\lambda-1)(1) = 1 - \lambda + 1 = 2 - \lambda$.

Final Row 3: $[0, 0, -(\lambda+3)(\lambda-2) \mid 2-\lambda ]$

* **i. Unique Solution:** Pivot is non-zero. $\lambda \neq -3$ and $\lambda \neq 2$.
* **ii. No Solution:** Pivot is zero, but RHS is non-zero.
    If $\lambda = -3$, LHS $= 0$, RHS $= 2 - (-3) = 5$. ($0 = 5$, Contradiction).
    **Answer:** $\lambda = -3$.
* **iii. Infinite Solutions:** Pivot is zero AND RHS is zero.
    If $\lambda = 2$, LHS $= 0$, RHS $= 2 - 2 = 0$. ($0 = 0$, Consistent).
    **Answer:** $\lambda = 2$.

**(b) Basis for Row Space ($W^\perp$) at $\lambda = 2$**
The row space of $A$ (which is orthogonal to the null space $W$) is spanned by the non-zero rows of the echelon form.
At $\lambda = 2$, the matrix reduces to:
$$
\begin{pmatrix} 1 & 1 & -1 \\ 0 & 1 & 4 \\ 0 & 0 & 0 \end{pmatrix}
$$
**Basis:** $\{(1, 1, -1), (0, 1, 4)\}$.

**(c) Proof of Subspace**
The column space is defined as the span of the column vectors of $A$: $\text{span}\{c_1, c_2, c_3\}$.
By definition, the span of any set of vectors in $\mathbb{R}^3$ is a subspace of $\mathbb{R}^3$ because:
1.  It contains the zero vector (weights = 0).
2.  It is closed under addition (sum of linear combos is a linear combo).
3.  It is closed under scalar multiplication.

---

## 4. Abstract Linear Transformations

**(a) Kernel and Injectivity**
Solve $T(x,y,z) = (0,0,0)$.
Matrix $A = \begin{pmatrix} 1 & -2 & 1 \\ 2 & 1 & -1 \\ -1 & -3 & 2 \end{pmatrix}$.
Row Reduce:
1.  $R_2 - 2R_1 \to (0, 5, -3)$
2.  $R_3 + R_1 \to (0, -5, 3)$
3.  $R_3 + R_2 \to (0, 0, 0)$.

System:
1.  $5y - 3z = 0 \implies y = \frac{3}{5}z$.
2.  $x - 2y + z = 0 \implies x - \frac{6}{5}z + \frac{5}{5}z = 0 \implies x = \frac{1}{5}z$.

Let $z = 5t$. Kernel vector: $(t, 3t, 5t)$.
**Kernel Basis:** $\{(1, 3, 5)\}$.
**Dimension:** 1.
**Injective?** No, because $\ker(T) \neq \{0\}$.

**(b) Image and Condition**
Since $\dim(\ker) = 1$, $\dim(\text{Im}) = 3 - 1 = 2$.
The image is spanned by the first two independent columns: $u = (1, 2, -1)$ and $v = (-2, 1, -3)$.
Condition for $w=(a,b,c)$ to be in image:
Looking at the row reduction of the augmented matrix $[A|w]$, we noticed row dependence $R_3 = -(R_1 + R_2)$ in the original matrix? No, let's check:
Original rows: $r_1=(1,-2,1), r_2=(2,1,-1), r_3=(-1,-3,2)$.
Note that $r_2 + r_3 = (1, -2, 1) = r_1$.
This linear dependency on rows means the components of the output $(a, b, c)$ must satisfy the same relationship:
**Condition:** $a = b + c$ (or $a - b - c = 0$).

**(c) Composition Matrix**
$S(v) = 2v \implies [S] = 2I$.
$[S \circ T] = [S][T] = 2I \cdot A = 2A$.
$$
M_{S \circ T} = \begin{pmatrix} 2 & -4 & 2 \\ 4 & 2 & -2 \\ -2 & -6 & 4 \end{pmatrix}
$$

---

## 5. Advanced Propositional Logic

**(a) Proof by Contradiction**
Proposition: $P = [ (p \to q) \wedge (q \to r) \wedge \neg r ] \to \neg p$.
1.  Assume the Proposition is **False**. This happens only if:
    * Premise (Left side) is **True**.
    * Conclusion ($\neg p$) is **False** $\implies p$ is **True**.
2.  Analyze the Premise being True:
    * $(p \to q)$ is True. Since $p$ is True, **$q$ must be True**.
    * $(q \to r)$ is True. Since $q$ is True, **$r$ must be True**.
    * $(\neg r)$ is True. This implies **$r$ is False**.
3.  **Contradiction:** We derived that $r$ is True and $r$ is False.
4.  Therefore, the assumption that the proposition is False is impossible. The proposition is a Tautology.

**(b) Disjunctive Normal Form (DNF)**
Target: $\neg(p \to (q \wedge r))$
1.  Eliminate implication: $\neg(\neg p \vee (q \wedge r))$
2.  De Morgan's Law: $\neg(\neg p) \wedge \neg(q \wedge r)$
3.  Double Negation: $p \wedge \neg(q \wedge r)$
4.  De Morgan's Law: $p \wedge (\neg q \vee \neg r)$
5.  Distributive Law: **$(p \wedge \neg q) \vee (p \wedge \neg r)$**

---

## 6. Relations and Partitions

**(a) Proof of Equivalence**
* **Reflexive:** Is $(x, x) \in R$? $x + x = 2x$, which is always even. **Yes.**
* **Symmetric:** If $(x, y) \in R$, is $(y, x) \in R$? If $x+y$ is even, then $y+x$ is even (commutativity). **Yes.**
* **Transitive:** If $(x, y)$ and $(y, z)$ are in $R$, is $(x, z) \in R$?
    * $x+y = 2k$
    * $y+z = 2j$
    * Add them: $x + 2y + z = 2k + 2j$.
    * $x + z = 2(k + j - y)$. Since the RHS is divisible by 2, $x+z$ is even. **Yes.**

**(b) Equivalence Classes**
* $[1] = \{x \in A \mid 1 + x \text{ is even}\}$.
    For $1+x$ to be even, $x$ must be odd.
    $[1] = \{1, 3, 5\}$.
* $[2] = \{x \in A \mid 2 + x \text{ is even}\}$.
    For $2+x$ to be even, $x$ must be even.
    $[2] = \{2, 4, 6\}$.

**(c) Partition**
The set of equivalence classes: $\{\{1, 3, 5\}, \{2, 4, 6\}\}$.

---

## 7. Modular Arithmetic & RSA Attack

**(a) System of Congruences**
1.  $x \equiv 2 \pmod 3$
2.  $x \equiv 2 \pmod 7$
    * From 1 and 2: Since $x$ has the same remainder (2) for both moduli, $x \equiv 2 \pmod{\text{lcm}(3,7)}$.
    * $x \equiv 2 \pmod{21}$. So $x = 21k + 2$.
3.  Substitute into third equation:
    * $21k + 2 \equiv 3 \pmod 5$
    * $1k + 2 \equiv 3 \pmod 5$ (Since $21 \equiv 1$)
    * $k \equiv 1 \pmod 5$.
    * Let $k = 5j + 1$.
4.  Back substitute:
    * $x = 21(5j + 1) + 2 = 105j + 21 + 2 = 105j + 23$.
5.  Smallest positive integer (j=0): **$x = 23$**.

**(b) Insecure RSA**
If Bob chooses $n = p^2$:
1.  **Factorization is Trivial:** The security of RSA relies on the difficulty of factoring $n$ into $p \times q$. If $n = p^2$, an attacker simply needs to calculate the square root: $p = \sqrt{n}$. Square roots can be computed extremely efficiently.
2.  **Key Calculation:** Once the attacker has $p$, they can calculate $\phi(n) = p^2 - p = p(p-1)$.
3.  **Private Key:** With $\phi(n)$ and the public $e$, they compute $d = e^{-1} \pmod{\phi(n)}$, completely breaking the encryption.

---

## 8. Vector Geometry & Proofs

**(a) Cauchy-Schwarz Implication**
We want to prove $||u + v||^2 \le (||u|| + ||v||)^2$.
1.  Expand LHS: $||u+v||^2 = \langle u+v, u+v \rangle = ||u||^2 + 2\langle u, v \rangle + ||v||^2$.
2.  Apply Cauchy-Schwarz inequality: $\langle u, v \rangle \le |\langle u, v \rangle| \le ||u|| ||v||$.
3.  Substitute this inequality into the expansion:
    $$||u||^2 + 2\langle u, v \rangle + ||v||^2 \le ||u||^2 + 2||u||||v|| + ||v||^2$$
4.  Factor the RHS (Perfect Square):
    $$= (||u|| + ||v||)^2$$
5.  Thus, $||u+v||^2 \le (||u|| + ||v||)^2$. (This proves the Triangle Inequality).

**(b) Orthogonality and Dependence**
* **Part 1: $\{u, v, u+v\}$ is Dependent.**
    Consider the linear combination: $1(u) + 1(v) + (-1)(u+v)$.
    $= u + v - u - v = 0$.
    Since there exist non-zero scalars ($1, 1, -1$) that produce the zero vector, the set is Linearly Dependent.
* **Part 2: $\{u, v\}$ is Independent.**
    Let $c_1 u + c_2 v = 0$.
    Take the dot product of both sides with $u$:
    $\langle u, c_1 u + c_2 v \rangle = \langle u, 0 \rangle$
    $c_1 \langle u, u \rangle + c_2 \langle u, v \rangle = 0$
    Since orthogonal $\langle u, v \rangle = 0$:
    $c_1 ||u||^2 = 0$.
    Since $u \neq 0$, $||u||^2 \neq 0$, so **$c_1 = 0$**.
    Repeat dot product with $v$ to show **$c_2 = 0$**.
    Since only the trivial solution exists, they are Linearly Independent.