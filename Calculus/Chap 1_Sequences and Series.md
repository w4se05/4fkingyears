# 2. Infinite Series (Conceptual)

### Definitions

> [!Definition] Infinite Series
> An expression of the sum of a sequence $\{a_n\}$:
> $$\sum_{n=1}^{\infty}a_{n} = a_{1} + a_{2} + a_{3} + \cdot\cdot\cdot$$
> .

> [!Definition] Partial Sums & Convergence
> The **$n$-th partial sum** is $s_{n} = \sum_{k=1}^{n}a_{k}$.
> * If the sequence of partial sums $\{s_n\}$ has a finite limit $s$, the series **converges** to $s$: $\sum_{n=1}^{\infty}a_{n} = s$.
> * If the limit does not exist, the series **diverges**.

### Fundamental Series Types

> [!Tip] Geometric Series
> Form: $\sum_{n=0}^{\infty}ar^{n} = a + ar + ar^2 + ...$ ($a \neq 0$).
> * **Converges** if $|r| < 1$. Sum = $\frac{a}{1-r}$.
> * **Diverges** if $|r| \ge 1$.

> [!Tip] p-Series
> Form: $\sum_{n=1}^{\infty}\frac{1}{n^{p}}$.
> * **Converges** if $p > 1$.
> * **Diverges** if $p \le 1$.
> * **Harmonic Series ($p=1$):** $\sum \frac{1}{n}$ diverges.

> [!Theorem] Test for Divergence ($n$-th Term Test)
> If $\sum a_n$ converges, then $\lim_{n\rightarrow\infty}a_{n} = 0$.
> **Contrapositive (The Test):** If $\lim_{n\rightarrow\infty}a_{n} \neq 0$ (or does not exist), then $\sum a_n$ **diverges**.
> *Warning:* If limit is 0, the test is inconclusive (e.g., Harmonic series limit is 0 but diverges).

---

## 3. Convergence Tests (Teach Mode)

### Comparison Tests
1.  **Direct Comparison Test:** Suppose $0 \le a_n \le b_n$.
    * If $\sum b_n$ (larger) converges $\implies \sum a_n$ converges.
    * If $\sum a_n$ (smaller) diverges $\implies \sum b_n$ diverges .
2.  **Limit Comparison Test (LCT):** If $a_n, b_n > 0$ and $\lim_{n\rightarrow\infty}\frac{a_n}{b_n} = c$ where $0 < c < \infty$:
    * Both series converge OR both series diverge .

### Absolute Convergence Tests
> [!Definition] Absolute vs. Conditional
> * **Absolute Convergence:** $\sum |a_n|$ converges. This implies $\sum a_n$ converges.
> * **Conditional Convergence:** $\sum a_n$ converges, but $\sum |a_n|$ diverges.

1.  **Ratio Test:** Let $L = \lim_{n\rightarrow\infty}|\frac{a_{n+1}}{a_{n}}|$.
    * $L < 1$: Converges absolutely.
    * $L > 1$ or $\infty$: Diverges.
    * $L = 1$: Inconclusive .
2.  **Root Test:** Let $L = \lim_{n\rightarrow\infty}\sqrt[n]{|a_{n}|}$.
    * $L < 1$: Converges absolutely.
    * $L > 1$ or $\infty$: Diverges.
    * $L = 1$: Inconclusive .

### Alternating Series
**Leibniz Criterion:** For $\sum (-1)^{n-1}b_n$ where $b_n \ge 0$:
The series converges if:
1.  $b_{n+1} \le b_n$ (Decreasing), AND
2.  $\lim_{n\rightarrow\infty}b_n = 0$ .

---

## 📘 Examples & Applications (Exam Mode)

### Example 1: Finding the General Term of a Sequence
> [!Example] Problem
> Find the formula for the sequence: $\frac{3}{5}, -\frac{4}{25}, \frac{5}{125}, -\frac{6}{625}, ...$.
> **Analysis:**
> * **Numerator:** $3, 4, 5, 6...$ increases by 1. If $n=1$, numerator is $n+2$.
> * **Denominator:** $5, 25, 125, 625...$ are powers of 5. If $n=1$, denominator is $5^n$.
> * **Signs:** $+ - + -$ indicates an alternating term like $(-1)^{n-1}$ (starts positive).
>
> **Solution:**
> $$a_{n} = (-1)^{n-1}\frac{n+2}{5^{n}}$$
> .

### Example 2: Squeeze Theorem Application
### Example 3: Telescoping Series
> [!Example] Problem
> Calculate the sum $\sum_{n=1}^{\infty}\frac{1}{n(n+1)}$.
> **Using:** Partial Fractions & Definition of Partial Sums.
>
> **Step 1:** Decompose term.
> $$\frac{1}{n(n+1)} = \frac{1}{n} - \frac{1}{n+1}$$
> .
>
> **Step 2:** Write partial sum $s_n$.
> $$s_{n} = \left(1 - \frac{1}{2}\right) + \left(\frac{1}{2} - \frac{1}{3}\right) + ... + \left(\frac{1}{n} - \frac{1}{n+1}\right)$$
> The intermediate terms cancel out.
> $$s_{n} = 1 - \frac{1}{n+1}$$
> .
>
> **Step 3:** Take the limit.
> $$\lim_{n\rightarrow\infty} s_n = 1 - 0 = 1$$
> **Result:** The series converges to 1.

### Example 4: Ratio Test for Convergence
> [!Example] Problem
> Test the series $\sum \frac{n!}{2^n}$ for convergence.
> **Using:** Ratio Test.
>
> **Step 1:** Set up limit $L$.
> $$L = \lim_{n\rightarrow\infty} \left| \frac{a_{n+1}}{a_n} \right| = \lim_{n\rightarrow\infty} \frac{(n+1)!}{2^{n+1}} \cdot \frac{2^n}{n!}$$
>
> **Step 2:** Simplify.
> $$L = \lim_{n\rightarrow\infty} \frac{(n+1)n!}{2 \cdot 2^n} \cdot \frac{2^n}{n!} = \lim_{n\rightarrow\infty} \frac{n+1}{2}$$
>
> **Step 3:** Evaluate.
> $$L = \infty$$
> .
>
> **Conclusion:** Since $L > 1$, the series **diverges**.
---

