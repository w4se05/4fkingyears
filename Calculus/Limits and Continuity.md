## 🧭 Conceptual Section (Teach Mode)

### 1. Definition of a Limit 

> [!Definition] 💡  
> The **limit** of $f(x)$ as $x$ approaches $a$ is $L$ if  
> $$
> \forall \varepsilon > 0, \exists \delta > 0 \text{ such that } 0 < |x - a| < \delta \Rightarrow |f(x) - L| < \varepsilon.
> $$
> Notation:  
> $$
> \lim_{x \to a} f(x) = L.
> $$

> [!Note] 🧩  
> Intuitively, as $x$ gets arbitrarily close to $a$, $f(x)$ gets arbitrarily close to $L$.

---

### 2. One-Sided Limits

> [!Definition] 💡  
> - **Right-hand limit:** $\displaystyle \lim_{x \to a^+} f(x)$  
> - **Left-hand limit:** $\displaystyle \lim_{x \to a^-} f(x)$  
>
> If both exist and are equal, the two-sided limit exists.

> [!Example] 🔍  
> $$
> f(x) =
> \begin{cases}
> 1, & x > 0, \\
> 0, & x \le 0
> \end{cases}
> $$
> Then $\lim_{x \to 0^-} f(x) = 0$, $\lim_{x \to 0^+} f(x) = 1$ → limit does not exist.

---

### 3. Infinite Limits

> [!Definition] 💡  
> If $f(x)$ increases without bound as $x \to a$,  
> $$
> \lim_{x \to a} f(x) = +\infty.
> $$
> If $f(x)$ decreases without bound,  
> $$
> \lim_{x \to a} f(x) = -\infty.
> $$

> [!Example] 🔍  
> $\displaystyle \lim_{x \to 0^+} \frac{1}{x} = +\infty$.

---

### 4. Limit Laws

> [!Theorem] 📘  
> If $\lim f(x) = L$ and $\lim g(x) = M$, then
> $$
> \begin{aligned}
> \lim (f(x) \pm g(x)) &= L \pm M, \\
> \lim (cf(x)) &= cL, \\
> \lim (f(x)g(x)) &= LM, \\
> \lim \frac{f(x)}{g(x)} &= \frac{L}{M}, \; M \ne 0.
> \end{aligned}
> $$

---

### 5. Important Standard Limits

> [!Property] 🧮  
> $$
> \lim_{x \to 0} \frac{\sin x}{x} = 1, \quad
> \lim_{x \to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2}, \quad
> \lim_{x \to 0} (1 + x)^{1/x} = e.
> $$

---

### 6. The Squeeze (Sandwich) Theorem

> [!Theorem] 📘  
> If $g(x) \le f(x) \le h(x)$ for $x$ near $a$, and  
> $$
> \lim_{x \to a} g(x) = \lim_{x \to a} h(x) = L,
> $$
> then $\lim_{x \to a} f(x) = L$.

> [!Example] 🔍  
> $\displaystyle \lim_{x \to 0} x^2 \sin\frac{1}{x} = 0$  
> since $-x^2 \le x^2 \sin\frac{1}{x} \le x^2$ and both bounding limits $\to 0$.

---

### 7. Continuity

> [!Definition] 💡  
> A function $f$ is **continuous at $x = a$** if:
> $$
> \lim_{x \to a} f(x) = f(a).
> $$
> That is,  
> 1. $f(a)$ is defined,  
> 2. $\lim_{x \to a} f(x)$ exists,  
> 3. Both are equal.

> [!Definition] 💡  
> $f$ is **continuous on interval $I$** if it is continuous at every point of $I$.

---

### 8. Types of Discontinuities

> [!Property] 🧮  
> - **Removable:** $\lim f(x)$ exists, but $\ne f(a)$.  
> - **Jump:** left/right limits exist but are unequal.  
> - **Infinite:** $f(x)$ approaches $\pm\infty$.

> [!Example] 🔍  
> $$
> f(x) =
> \begin{cases}
> x, & x \ne 2 \\
> 3, & x = 2
> \end{cases}
> $$
> $\lim_{x \to 2} f(x) = 2$, but $f(2) = 3$ → removable discontinuity.

---

### 9. Continuity of Composite and Inverse Functions

> [!Theorem] 📘  
> If $f$ and $g$ are continuous at $a$ and $f$ is continuous at $g(a)$,  
> then $f \circ g$ is continuous at $a$.

> [!Theorem] 📘  
> If $f$ is continuous and one-to-one, then $f^{-1}$ is continuous on its domain.

---

### 10. Intermediate Value Theorem (IVT)

> [!Theorem] 📘  
> If $f$ is continuous on $[a, b]$ and $N$ lies between $f(a)$ and $f(b)$,  
> then $\exists c \in (a, b)$ such that $f(c) = N$.

> [!Example] 🔍  
> $f(x) = x^3 - x - 2$  
> $f(1) = -2$, $f(2) = 4$.  
> Since $0$ lies between $f(1)$ and $f(2)$,  
> $\exists c \in (1, 2)$ such that $f(c) = 0$ (by IVT).

---

## 📘 Examples & Applications (Exam Mode)

---

### Example 1 — Evaluating a Limit  
_(Using: Algebraic Simplification)_

$$
\lim_{x \to 2} \frac{x^2 - 4}{x - 2}
$$

**Solution:**  
Factor numerator: $(x - 2)(x + 2)$.  
Simplify:  
$$
\lim_{x \to 2} (x + 2) = 4.
$$
✅ Limit = 4.

---

### Example 2 — Trigonometric Limit  
_(Using: Standard Limit)_

$$
\lim_{x \to 0} \frac{\sin 3x}{x}
$$

**Solution:**  
Multiply and divide by $3$:  
$$
\lim_{x \to 0} 3 \frac{\sin 3x}{3x} = 3(1) = 3.
$$
✅ Limit = 3.

---

### Example 3 — Squeeze Theorem  
_(Using: Squeeze)_

$$
\lim_{x \to 0} x^2 \cos\frac{1}{x}
$$

Since $-x^2 \le x^2 \cos\frac{1}{x} \le x^2$,  
both outer terms $\to 0$.  
✅ Limit = 0.

---

### Example 4 — Continuity Check  
_(Using: Definition of Continuity)_

$$
f(x) =
\begin{cases}
x^2, & x < 1,\\
2x - 1, & x \ge 1
\end{cases}
$$
Check continuity at $x = 1$.

**Solution:**  
Left limit: $\lim_{x \to 1^-} f(x) = 1$  
Right limit: $\lim_{x \to 1^+} f(x) = 1$  
$f(1) = 1$  
✅ Continuous at $x = 1$.

---

### Example 5 — IVT Application  
_(Using: Intermediate Value Theorem)_

Prove existence of a root of $f(x) = x^3 - x - 1$ between $1$ and $2$.

**Solution:**  
$f(1) = -1$, $f(2) = 5$.  
$0$ lies between them ⇒ by IVT,  
∃ $c \in (1, 2)$ with $f(c) = 0$.  
✅ Root exists between 1 and 2.

---

## 🔑 Summary (Revision Mode)

- Limit: $\displaystyle \lim_{x \to a} f(x) = L$  
  if $f(x)$ → $L$ as $x$ → $a$.
- One-sided limits must match for limit to exist.
- Infinite limits → vertical asymptotes.
- Limit laws simplify combinations of limits.
- Standard limits:
  $$
  \lim_{x\to 0} \frac{\sin x}{x} = 1, \;
  \lim_{x\to 0} (1+x)^{1/x} = e.
  $$
- Squeeze Theorem: if $g \le f \le h$ and $\lim g = \lim h = L$, then $\lim f = L$.
- Continuity: $\lim_{x \to a} f(x) = f(a)$.
- Discontinuities: removable, jump, infinite.
- IVT: continuous $f$ on $[a,b]$ takes every value between $f(a)$ and $f(b)$.

---

✅ **End of File — Chapter 2 (Part B): Limits and Continuity**
