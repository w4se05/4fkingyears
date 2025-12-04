	## 🧭 Conceptual Section (Teach Mode)

### 1. Sequences

> [!Definition] 💡  
> A **sequence** is an ordered list of numbers written as  
> $$a_1, a_2, a_3, \ldots, a_n, \ldots$$  
> or in set form $$\{a_n\}.$$  
> - Finite sequence: has finitely many terms.  
> - Infinite sequence: continues indefinitely.

---

> [!Definition] 💡  
> **Limit of a Sequence**  
> A sequence $\{a_n\}$ has a limit $L$ if  
> $$\forall \varepsilon > 0, \exists N \in \mathbb{N}: |a_n - L| < \varepsilon, \ \forall n > N.$$  
> We write $$\lim_{n \to \infty} a_n = L \quad \text{or simply } a_n \to L.$$

> [!Property] 🧮  
> - The limit, if it exists, is unique.  
> - A constant sequence $a_n = C$ satisfies $\lim a_n = C$.  
> - If $|r| < 1$, then $\lim_{n \to \infty} r^n = 0$.

---

> [!Example] 🔍  
> $$a_n = \frac{n}{n + 1} \to 1 \quad \text{as } n \to \infty.$$  
> Proof:  
> $$|a_n - 1| = \left| \frac{n}{n+1} - 1 \right| = \frac{1}{n+1} \to 0.$$

---

### 2. Convergence and Divergence

> [!Definition] 💡  
> - $\{a_n\}$ is **convergent** if $\lim_{n \to \infty} a_n = L \in \mathbb{R}$.  
> - It **diverges** to $\infty$ if $\lim a_n = +\infty$.  
> - Otherwise, $\{a_n\}$ is **divergent**.

> [!Example] 🔍  
> $$a_n = \frac{1}{n} \to 0 \quad (\text{Convergent})$$  
> $$a_n = n \to +\infty \quad (\text{Divergent})$$  
> $$a_n = (-1)^n \text{ oscillates} \quad (\text{Divergent})$$

---

### 3. Limit Laws for Sequences

> [!Theorem] 📘 **(Limit Laws)**  
> If $\lim a_n = A$ and $\lim b_n = B$, then  
> $$
> \begin{aligned}
> &\lim (a_n \pm b_n) = A \pm B, \\
> &\lim (c a_n) = cA, \quad c \in \mathbb{R}, \\
> &\lim (a_n b_n) = AB, \\
> &\lim \frac{a_n}{b_n} = \frac{A}{B}, \quad \text{if } B \neq 0.
> \end{aligned}
> $$

> [!Property] 🧮  
> If $a_n < b_n$ for all $n$ large enough, then $\lim a_n \leq \lim b_n$.

---

### 4. Boundedness and Monotonicity

> [!Definition] 💡  
> A sequence $\{a_n\}$ is **bounded** if $\exists M > 0$ such that $|a_n| \le M$ for all $n$.

> [!Definition] 💡  
> A sequence $\{a_n\}$ is **monotone** if it is either increasing ($a_{n+1} \ge a_n$) or decreasing ($a_{n+1} \le a_n$).

> [!Theorem] 📘 **(Weierstrass Monotone Convergence Theorem)**  
> Every **bounded monotone** sequence is **convergent**.

---

### 5. Important Theorems

> [!Theorem] 📘 **(Squeeze Theorem)**  
> If $a_n \le b_n \le c_n$ for all $n$ large enough and  
> $$\lim a_n = \lim c_n = L,$$  
> then $$\lim b_n = L.$$

> [!Theorem] 📘 **(Subsequence Convergence)**  
> If both even and odd subsequences converge to the same limit $L$, then  
> $$\lim a_n = L.$$

> [!Theorem] 📘 **(Convergence of Absolute Value)**  
> If $\lim |a_n| = 0$, then $\lim a_n = 0$.

---

### 6. Special Sequences

> [!Definition] 💡  
> **Arithmetic Sequence:**  
> $$a, a + d, a + 2d, a + 3d, \ldots$$  
> General term: $$a_n = a + (n - 1)d.$$

> [!Definition] 💡  
> **Geometric Sequence:**  
> $$a, ar, ar^2, ar^3, \ldots$$  
> General term: $$a_n = a r^{n-1}.$$

> [!Definition] 💡  
> **Number \( e \):**  
> $$e = \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n.$$

---

## 📘 Examples & Applications (Exam Mode)

---

### Example 1 — Convergence of a Rational Sequence  
_(Using: Limit Definition)_

Find $\lim_{n \to \infty} \frac{n}{n + 1}$.

**Solution:**  
$$
\lim_{n \to \infty} \frac{n}{n + 1}
= \lim_{n \to \infty} \frac{1}{1 + \frac{1}{n}} = 1.
$$
Hence, the sequence converges to 1.

---

### Example 2 — Applying the Squeeze Theorem  
_(Using: Squeeze Theorem)_

Find $\lim_{n \to \infty} \frac{\sin n}{n}$.

**Solution:**  
Since $-1 \le \sin n \le 1$, we have  
$$-\frac{1}{n} \le \frac{\sin n}{n} \le \frac{1}{n}.$$
By the Squeeze Theorem,  
$$\lim_{n \to \infty} \frac{\sin n}{n} = 0.$$

---

### Example 3 — Monotone and Bounded Sequence  
_(Using: Weierstrass Theorem)_

Show that $a_n = 1 - \frac{1}{n}$ converges.

**Solution:**  
$a_{n+1} - a_n = \frac{1}{n} - \frac{1}{n+1} > 0$ ⇒ increasing.  
Bounded above by 1.  
By Weierstrass Theorem, $\lim a_n = 1$.

---

### Example 4 — Divergence of an Oscillating Sequence  
_(Using: Subsequence Test)_

Let $a_n = (-1)^n \frac{n}{n+1}$.  
Even subsequence: $a_{2k} = \frac{2k}{2k+1} \to 1$.  
Odd subsequence: $a_{2k-1} = -\frac{2k-1}{2k} \to -1$.  
Since limits differ, $\{a_n\}$ diverges.

---

### Example 5 — Geometric Series and \( e \)  
_(Using: Definition of \( e \))_

Prove $\left(1 + \frac{1}{n}\right)^n$ converges to \( e \).

**Solution Sketch:**  
The sequence is increasing and bounded above by 3.  
Hence by Weierstrass,  
$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e.$$

---

## 🔑 Summary (Revision Mode)

- Sequence: $\{a_n\}$ = ordered list of real numbers.  
- Convergence: $\lim_{n \to \infty} a_n = L$ if $|a_n - L| < \varepsilon$ for large $n$.  
- Divergent ⇒ no finite limit.  
- If $|r| < 1$, then $r^n \to 0$.  
- Bounded + Monotone ⇒ Convergent (Weierstrass).  
- Squeeze Theorem: if $a_n \le b_n \le c_n$ and $\lim a_n = \lim c_n$, then $\lim b_n$ exists.  
- Arithmetic seq.: $a_n = a + (n-1)d$.  
- Geometric seq.: $a_n = ar^{n-1}$.  
- Definition of \( e \): $\displaystyle e = \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n.$

---
$$-1 \le \sin n \le 1$$
$$-1 \le \cos n \le 1$$
$$\lim_{n \to \infty} \cot^{-1} n = 0$$
$$\lim_{x \to \infty} \arctan x = \frac{\pi}{2}$$$$\lim_{x \to -\infty} \arctan x = -\frac{\pi}{2}$$
$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$$(Common variation: $(1 + \frac{a}{n})^n \to e^a$)
