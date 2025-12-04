## I. Algebra & Trigonometry

### 1. Bảy Hằng Đẳng Thức (Algebraic Identities)
$$
\begin{aligned}
1. & \quad (A + B)^2 = A^2 + 2AB + B^2 \\
2. & \quad (A - B)^2 = A^2 - 2AB + B^2 \\
3. & \quad A^2 - B^2 = (A - B)(A + B) \\
4. & \quad (A + B)^3 = A^3 + 3A^2B + 3AB^2 + B^3 \\
5. & \quad (A - B)^3 = A^3 - 3A^2B + 3AB^2 - B^3 \\
6. & \quad A^3 + B^3 = (A + B)(A^2 - AB + B^2) \\
7. & \quad A^3 - B^3 = (A - B)(A^2 + AB + B^2)
\end{aligned}
$$

### 2. Trigonometry Definitions & Identities
* **Definitions:**
  $$\tan x = \frac{\sin x}{\cos x}, \quad \cot x = \frac{\cos x}{\sin x}$$
  $$\sec x = \frac{1}{\cos x}, \quad \csc x = \frac{1}{\sin x}$$
* **Pythagorean Identities:**
  1. $\sin^2 x + \cos^2 x = 1$
  2. $1 + \tan^2 x = \sec^2 x$
  3. $1 + \cot^2 x = \csc^2 x$
  4. $\arctan n+ arc\cot n=\frac{\pi}{2}$
* **Double Angle:**
  * $\sin(2x) = 2\sin x \cos x$
  * $\cos(2x) = \cos^2 x - \sin^2 x = 2\cos^2 x - 1 = 1 - 2\sin^2 x$

  ---

## II. Sequences (Dãy số)

* **Limit Definition:** $\lim_{n\to\infty} a_n = L$ (Unique if exists).
* **Standard Limits ($n \to \infty$):**
  * $\lim \frac{1}{n^p} = 0 \quad (p > 0)$
  * $\lim r^n = \begin{cases} 0 & |r| < 1 \\ \infty & r > 1 \end{cases}$
  * $\lim \left(1 + \frac{1}{n}\right)^n = e$
  * $\lim \sqrt[n]{n} = 1$
* **Theorems:**
  * **Weierstrass:** Bounded + Monotone $\Rightarrow$ Convergent.
  * **Squeeze Theorem:** $a_n \le b_n \le c_n$, if $\lim a_n = \lim c_n = L \Rightarrow \lim b_n = L$.
  * **Subsequences:** If $a_n \to L$, then $a_{2k} \to L$ and $a_{2k-1} \to L$. If differ $\to$ Divergent.

---

## III. Infinite Series (Chuỗi số)

> [!WARNING] Divergence Test
> If $\lim_{n\to\infty} a_n \neq 0 \implies \sum a_n$ **Diverges**.

### 1. Common Series Types
| Type          | Form                 | Convergence Condition                                            |
| :------------ | :------------------- | :--------------------------------------------------------------- |
| **Geometric** | $\sum ar^n$          | **Conv:** $r < 1 \quad (S = \frac{a}{1-r})$<br>**Div:** $r\ge 1$ |
| **p-Series**  | $\sum \frac{1}{n^p}$ | **Conv:** $p > 1$<br>**Div:** $p \le 1$                          |
| **Harmonic**  | $\sum \frac{1}{n}$   | **Always Diverges** ($p=1$)                                      |

### 2. Convergence Tests
* **Comparison:** $0 \le a_n \le b_n$. If $\sum b_n$ Conv $\Rightarrow \sum a_n$ Conv.
* **Limit Comparison:** $\lim \frac{a_n}{b_n} = c > 0 \implies$ same behavior.
* **Alternating Series (Leibniz):** $\sum (-1)^{n-1}b_n$ Conv if:
  1. $b_{n+1} \le b_n$ (Decreasing) **AND**
  2. $\lim b_n = 0$.
* **Ratio Test:** $L = \lim |\frac{a_{n+1}}{a_n}|$. $L < 1$ (Conv), $L > 1$ (Div).
* **Root Test:** $L = \lim \sqrt[n]{|a_n|}$. Same rules as Ratio.

### 3. Power Series
* **Radius $R$:** Use Ratio Test ($|x-a| < R$).
* **Interval:** $(a-R, a+R)$. **Check endpoints manually!**

---

## IV. Functions & Limits ($x \to c$)

* **Special Trigonometric Limits ($u \to 0$):**
  1. $\lim_{u \to 0} \frac{\sin u}{u} = 1$
  2. $\lim_{u \to 0} \frac{1 - \cos u}{u} = 0$
  3. $\lim_{u \to 0} \frac{\tan u}{u} = 1$
* **Continuity:** $f$ is continuous at $a$ if $\lim_{x\to a}f(x) = f(a)$.
* **Intermediate Value Theorem (IVT):** If $f$ is continuous on $[a,b]$ and $f(a) \cdot f(b) < 0$, then $\exists c \in (a,b)$ s.t. $f(c) = 0$.
* **Inverse Functions:** Exists if 1-to-1. Symmetric over $y=x$.

---

## V. Differentiation Formulas (Bảng Đạo Hàm)

| Basic ($x$)   | Derivative ($f'$)         | Chain Rule ($u$)           |
| :------------ | :------------------------ | :------------------------- |
| $k$           | $0$                       | —                          |
| $x^n$         | $n x^{n-1}$               | $n u^{n-1} \cdot u'$       |
| $\frac{1}{x}$ | $-\frac{1}{x^2}$          | $-\frac{u'}{u^2}$          |
| $\sqrt{x}$    | $\frac{1}{2\sqrt{x}}$     | $\frac{u'}{2\sqrt{u}}$     |
| $\sin x$      | $\cos x$                  | $\cos u \cdot u'$          |
| $\cos x$      | $-\sin x$                 | $-\sin u \cdot u'$         |
| $\tan x$      | $\sec^2 x$                | $(1+\tan^2 u) u'$          |
| $\cot x$      | $-\csc^2 x$               | $-(1+\cot^2 u) u'$         |
| $e^x$         | $e^x$                     | $e^u \cdot u'$             |
| $a^x$         | $a^x \ln a$               | $a^u \ln a \cdot u'$       |
| $\ln x$       | $\frac{1}{x}$             | $\frac{u'}{u}$             |
| $\log_a x$    | $\frac{1}{x \ln a}$       | $\frac{u'}{u \ln a}$       |
| $\arctan x$   | $\frac{1}{1+x^2}$         | $\frac{u'}{1+u^2}$         |
| $\arcsin x$   | $\frac{1}{\sqrt{1-x^2}}$  | $\frac{u'}{\sqrt{1-u^2}}$  |
| $\arccos x$   | $-\frac{1}{\sqrt{1-x^2}}$ | $-\frac{u'}{\sqrt{1-u^2}}$ |

---

## VI. Derivative Rules

1.  **Product:** $(uv)' = u'v + uv'$
2.  **Quotient:** $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$
3.  **Chain:** $\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$
4.  **Implicit:** Differentiate w.r.t $x$. Add $y'$ to $y$ terms.
5.  **Inverse Func:** $(f^{-1})'(y_0) = \frac{1}{f'(x_0)}$ where $y_0 = f(x_0)$.
6.  **Linear Approx:** $L(x) = f(a) + f'(a)(x-a)$.
7.  **Log Diff:** $\ln y = \dots \implies \frac{y'}{y} = [\dots]'$.