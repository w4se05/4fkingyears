### 1. Definition and Convergence

> [!Definition] 💡  
> An **infinite series** associated with a sequence $\{a_n\}$ is written as  
> $$
> \sum_{n=1}^{\infty} a_n = a_1 + a_2 + a_3 + \cdots
> $$
> The **n-th partial sum** is  
> $$
> s_n = \sum_{k=1}^{n} a_k.
> $$
> The series **converges** if $\lim_{n \to \infty} s_n = s$ exists and is finite;  
> otherwise, it **diverges**.

---

> [!Example] 🔍 **Geometric Series**  
> $$
> \sum_{n=0}^{\infty} ar^n = a + ar + ar^2 + ar^3 + \cdots
> $$
> Partial sum:
> $$
> s_n = a \frac{1 - r^{n+1}}{1 - r}, \quad r \ne 1.
> $$
> Converges if $|r| < 1$, and  
> $$
> \sum_{n=0}^{\infty} ar^n = \frac{a}{1 - r}.
> $$

> [!Example] 🔍  
> $$
> \sum_{n=1}^{\infty} \frac{1}{2^n} = 1.
> $$

---

### 2. Divergent and Special Series

> [!Example] 🔍 **Harmonic Series**
> $$
> \sum_{n=1}^{\infty} \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \cdots
> $$
> diverges to infinity (partial sums unbounded).

> [!Example] 🔍 **Telescoping Series**
> $$
> \sum_{n=1}^{\infty} \frac{1}{n(n+1)} = \sum_{n=1}^{\infty} \left(\frac{1}{n} - \frac{1}{n+1}\right)
> $$
> Partial sum:
> $$
> s_n = 1 - \frac{1}{n+1} \to 1.
> $$
> Hence, the series converges to 1.

---

### 3. Convergence Tests


>[!Theorem] **p-Series Test**
>*The series*
>$$\displaystyle\sum^\infty_{n=1}\frac{1}{n^P}$$
>- **converges** if $p>1$ 
>- **diverges** if $p\leq{1}$


> [!Theorem] 📘 **(Test for Divergence)**  
> If $\lim_{n \to \infty} a_n \ne 0$ or the limit does not exist,  
> then $\sum a_n$ **diverges**.

---

> [!Theorem] 📘 **(Comparison Test)**  
> Suppose $a_n, b_n > 0$ for all large $n$.
> - If $a_n \le b_n$ and $\sum b_n$ converges, then $\sum a_n$ converges.  
> - If $a_n \ge b_n$ and $\sum b_n$ diverges, then $\sum a_n$ diverges.

> [!Example] 🔍  
> Compare $\displaystyle \sum_{n=1}^{\infty} \frac{1}{n^2 + 1}$ with $\sum \frac{1}{n^2}$:  
> since $\frac{1}{n^2 + 1} < \frac{1}{n^2}$ and $\sum \frac{1}{n^2}$ converges,  
> $\sum \frac{1}{n^2 + 1}$ converges by the Comparison Test.

---

> [!Theorem] 📘 **(Limit Comparison Test)**  
> For $a_n, b_n > 0$, if  
> $$
> \lim_{n \to \infty} \frac{a_n}{b_n} = c, \quad 0 < c < \infty,
> $$
> then $\sum a_n$ and $\sum b_n$ either both converge or both diverge.

> [!Example] 🔍  
> $\sum \frac{n}{n^3 + 1}$ compared with $\sum \frac{1}{n^2}$.  
> $$
> \lim_{n\to\infty}\frac{a_n}{b_n} = \lim_{n\to\infty} \frac{n/(n^3+1)}{1/n^2} = 1.
> $$  
> Hence both converge.

---

> [!Theorem] 📘 **(Ratio Test)**  
> For $\sum a_n$ with $a_n \ne 0$,
> $$
> L = \lim_{n \to \infty} \left| \frac{a_{n+1}}{a_n} \right|.
> $$
> Then:
> - If $L < 1$, series converges absolutely.  
> - If $L > 1$ or $L = \infty$, series diverges.  
> - If $L = 1$, test is inconclusive.

> [!Example] 🔍  
> $\displaystyle \sum_{n=0}^{\infty} \frac{1}{n!}$  
> $$
> \frac{a_{n+1}}{a_n} = \frac{1/(n+1)!}{1/n!} = \frac{1}{n+1} \to 0 < 1.
> $$
> Converges absolutely (sum = $e$).

---

> [!Theorem] 📘 **(Root Test)**  
> Let $L = \lim_{n \to \infty} \sqrt[n]{|a_n|}$.  
> - If $L < 1$, converges absolutely.  
> - If $L > 1$, diverges.  
> - If $L = 1$, inconclusive.

---

### 4. Alternating and Absolute Convergence

> [!Definition] 💡  
> An **alternating series** has terms alternating in sign:  
> $$
> \sum_{n=1}^{\infty} (-1)^{n-1} b_n, \quad b_n > 0.
> $$

> [!Theorem] 📘 **(Leibniz Test)**  
> If $b_n$ decreases monotonically to 0,  
> i.e. $b_{n+1} \le b_n$ and $\lim b_n = 0$,  
> then $\sum (-1)^{n-1} b_n$ **converges**.

> [!Definition] 💡  
> - **Absolutely convergent:** $\sum |a_n|$ converges.  
> - **Conditionally convergent:** $\sum a_n$ converges but $\sum |a_n|$ diverges.

---

### 5. Power Series

> [!Definition] 💡  
> A **power series** centered at $a$ is  
> $$
> \sum_{n=0}^{\infty} c_n (x - a)^n.
> $$
> It converges for $|x - a| < R$ and diverges for $|x - a| > R$,  
> where $R$ is the **radius of convergence**.

> [!Formula] 🧮  
> The radius $R$ is given by  
> $$
> R = \frac{1}{\displaystyle \limsup_{n \to \infty} \sqrt[n]{|c_n|}}.
> $$

---

## 📘 Examples & Applications (Exam Mode)

---

### Example 1 — Telescoping Series
_(Using: Telescoping)_

Evaluate
$$
\sum_{n=1}^{\infty} \frac{1}{n(n+1)}.
$$

**Solution:**
$$
\frac{1}{n(n+1)} = \frac{1}{n} - \frac{1}{n+1}.
$$
Partial sum:
$$
s_n = 1 - \frac{1}{n+1} \to 1.
$$
✅ Series converges to **1**.

---

### Example 2 — Ratio Test
_(Using: Ratio Test)_

Determine convergence of
$$
\sum_{n=1}^{\infty} \frac{3^n}{n!}.
$$

**Solution:**
$$
L = \lim_{n \to \infty} \left|\frac{a_{n+1}}{a_n}\right| = \lim_{n \to \infty} \frac{3^{n+1}/(n+1)!}{3^n/n!} = \lim_{n \to \infty} \frac{3}{n+1} = 0 < 1.
$$
✅ Series converges absolutely.

---

### Example 3 — Alternating Series
_(Using: Leibniz Test)_

$$
\sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n}.
$$
Here $b_n = 1/n$ decreases and $\lim b_n = 0$.  
Hence series converges (conditionally).  
But $\sum |a_n| = \sum 1/n$ diverges → conditional convergence.

---

### Example 4 — Power Series Radius of Convergence
_(Using: Root Test)_

For
$$
\sum_{n=0}^{\infty} \frac{(x-1)^n}{n^2 + 1},
$$
we find
$$
R = \frac{1}{\limsup \sqrt[n]{1/(n^2 + 1)}} = 1.
$$
Hence convergent for $|x - 1| < 1$.

---

## 🔑 Summary (Revision Mode)

- Infinite series: $\sum a_n$ converges if $s_n = \sum_{k=1}^{n} a_k$ approaches a finite limit.  
- Geometric: convergent if $|r| < 1$, sum $= \frac{a}{1 - r}$.  
- Telescoping: collapse to few terms, limit of partial sum gives result.  
- Harmonic: divergent.  
- Divergence Test: if $\lim a_n \ne 0$, diverges.  
- Comparison / Limit Comparison: compare with known p-series $\frac{1}{n^p}$ (convergent if $p > 1$).  
- Ratio Test / Root Test: absolute convergence for $L < 1$.  
- Alternating Series (Leibniz): decreasing to 0 ⇒ convergent.  
- Absolute vs Conditional: absolute ⇒ always convergent.  
- Power series: convergent for $|x - a| < R$, with  
  $$
  R = \frac{1}{\limsup \sqrt[n]{|c_n|}}.
  $$

---

✅ **End of File — Chapter 1: Sequences and Series**
