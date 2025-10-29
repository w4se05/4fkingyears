
## 🧭 Conceptual Section (Teach Mode)

### 1. Definition of a Function

> [!Definition] 💡  
> A **function** $f : X \to Y$ is a rule that assigns to each element $x \in X$ **exactly one** element $y \in Y$, denoted $f(x)$.
>
> - $X$: domain (input set)  
> - $Y$: codomain (output set)  
> - $f(x)$: image of $x$ under $f$

---

> [!Example] 🔍  
> Let $f(x) = x^2$.  
> - Domain: $\mathbb{R}$  
> - Range: $[0, \infty)$  
> - $f(-3) = 9$, $f(3) = 9$ (not one-to-one).

---

### 2. Domain and Range

> [!Definition] 💡  
> - **Domain** $D(f) = \{x \in X \mid f(x) \text{ is defined}\}$  
> - **Range** $R(f) = \{f(x) \mid x \in D(f)\}$

> [!Example] 🔍  
> For $f(x) = \frac{1}{x}$:  
> $D(f) = \mathbb{R} \setminus \{0\}$,  
> $R(f) = \mathbb{R} \setminus \{0\}$.

---

### 3. Representations of a Function

> [!Note] 🧩  
> A function can be expressed in four equivalent ways:
> 1. **Algebraically:** $f(x) = 3x + 1$  
> 2. **Numerically:** table of $(x, f(x))$ pairs  
> 3. **Graphically:** plot of $f(x)$  
> 4. **Verbally:** “$f$ triples input and adds one.”

---

### 4. Types of Functions

> [!Property] 🧮  
> - **Linear:** $f(x) = mx + b$  
> - **Quadratic:** $f(x) = ax^2 + bx + c$  
> - **Exponential:** $f(x) = a^x, \; a > 0, a \ne 1$  
> - **Logarithmic:** $f(x) = \log_a x, \; a > 1$  
> - **Trigonometric:** $\sin x, \cos x, \tan x$  
> - **Hyperbolic:** $\frac{1}{x}$  
> - **Piecewise:** defined by different formulas over intervals.

---

### 5. Function Properties

> [!Definition] 💡 **Monotonicity**  
> A function $f$ is:
> - **Increasing** on $I$ if $x_1 < x_2 \Rightarrow f(x_1) \le f(x_2)$  
> - **Decreasing** on $I$ if $x_1 < x_2 \Rightarrow f(x_1) \ge f(x_2)$

> [!Example] 🔍  
> $f(x) = 2x + 1$ is increasing on $\mathbb{R}$;  
> $g(x) = x^2$ is increasing on $(0, \infty)$, decreasing on $(-\infty, 0)$.

---

> [!Definition] 💡 **Symmetry**  
> - Even: $f(-x) = f(x)$ → symmetric about the $y$-axis.  
> - Odd: $f(-x) = -f(x)$ → symmetric about the origin.

> [!Example] 🔍  
> $f(x) = x^2$ is even.  
> $g(x) = x^3$ is odd.

---

> [!Definition] 💡 **Periodicity**  
> $f$ is **periodic** with period $T > 0$ if  
> $$
> f(x + T) = f(x) \quad \forall x.
> $$
> Example: $\sin x, \cos x$ are periodic with $T = 2\pi$.

---

### 6. Operations on Functions

> [!Definition] 💡  
> For functions $f$ and $g$:
> $$
> (f + g)(x) = f(x) + g(x), \quad (f - g)(x) = f(x) - g(x)
> $$
> $$
> (fg)(x) = f(x)g(x), \quad \left(\frac{f}{g}\right)(x) = \frac{f(x)}{g(x)} \text{ if } g(x) \ne 0.
> $$

> [!Example] 🔍  
> $f(x) = x^2 + 1$, $g(x) = x$:  
> $(f/g)(x) = \frac{x^2 + 1}{x}, \; x \ne 0.$

---

### 7. Composition of Functions

> [!Definition] 💡  
> The **composition** $f \circ g$ is  
> $$
> (f \circ g)(x) = f(g(x)).
> $$

> [!Example] 🔍  
> $f(x) = 3x + 2$, $g(x) = x^2$:  
> $(f \circ g)(x) = f(g(x)) = 3x^2 + 2.$

---

### 8. Inverse Function

> [!Definition] 💡  
> $f^{-1}$ is the **inverse** of $f$ if
> $$
> f(f^{-1}(x)) = x, \quad f^{-1}(f(x)) = x.
> $$

> [!Theorem] 📘 **Existence of Inverse**  
> A function $f$ has an inverse **iff** it is **one-to-one** (injective).

> [!Example] 🔍  
> $f(x) = 2x + 3$:  
> $y = 2x + 3 \Rightarrow x = \frac{y - 3}{2} \Rightarrow f^{-1}(x) = \frac{x - 3}{2}.$

---

### 9. Transformations of Functions

> [!Definition] 💡  
> Transformations modify the graph of a base function $f(x)$:
>
> - **Vertical shift:** $f(x) + k$ → up by $k$  
> - **Horizontal shift:** $f(x - h)$ → right by $h$  
> - **Reflection:** $-f(x)$ (x-axis), $f(-x)$ (y-axis)  
> - **Vertical stretch/shrink:** $a f(x)$ (by factor $a$)  
> - **Horizontal stretch/shrink:** $f(bx)$ (by factor $1/b$)

---

> [!Example] 🔍  
> $f(x) = x^2$  
> - $g(x) = (x - 2)^2$ → shift right by 2  
> - $h(x) = -x^2$ → reflection over x-axis  
> - $k(x) = 2x^2$ → vertical stretch by 2  
> - $m(x) = \frac{1}{2}x^2$ → vertical shrink by $\frac{1}{2}$

---

> [!Example] 🔍  
> $f(x) = \sin x$
> - $g(x) = \sin(x - \pi/2)$ → shift right by $\pi/2$  
> - $h(x) = -\sin x$ → reflection over x-axis  
> - $k(x) = 2\sin x$ → vertical stretch by 2  
> - $p(x) = \sin(2x)$ → horizontal compression by $\frac{1}{2}$

---

## 📘 Examples & Applications (Exam Mode)

---

### Example 1 — Find the Domain and Range  
_(Using: Definition of a Function)_

For $f(x) = \sqrt{x - 2}$

**Solution:**  
Require $x - 2 \ge 0 \Rightarrow x \ge 2.$  
Domain: $[2, \infty)$  
Range: $[0, \infty)$

---

### Example 2 — Composition and Domain  
_(Using: Function Composition)_

$f(x) = \sqrt{x + 1}$, $g(x) = 4x - 3$  
Find $(f \circ g)(x)$ and its domain.

**Solution:**  
$$
(f \circ g)(x) = f(g(x)) = \sqrt{4x - 3 + 1} = \sqrt{4x - 2}.
$$
Domain: $4x - 2 \ge 0 \Rightarrow x \ge \frac{1}{2}.$  
Hence $D = [\frac{1}{2}, \infty)$.

---

### Example 3 — Inverse Function  
_(Using: Inverse Definition)_

Given $f(x) = 5x - 4$, find $f^{-1}(x)$.

**Solution:**  
$y = 5x - 4 \Rightarrow x = \frac{y + 4}{5}$  
$\Rightarrow f^{-1}(x) = \frac{x + 4}{5}.$  
Verify:  
$f(f^{-1}(x)) = 5\left(\frac{x + 4}{5}\right) - 4 = x.$ ✅

---

### Example 4 — Transformation  
_(Using: Transformation Rules)_

Base function $f(x) = |x|$.  
Find the graph of $g(x) = -2|x + 3| + 1$.

**Solution:**  
Transformations in order:  
1. Shift **left 3 units** → $|x + 3|$  
2. Reflect **over x-axis** → $-|x + 3|$  
3. Stretch **vertically by 2** → $-2|x + 3|$  
4. Shift **up 1 unit** → $-2|x + 3| + 1$

---

## 🔑 Summary (Revision Mode)

- Function $f : X \to Y$ assigns one $y$ to each $x$.  
- Domain = valid $x$; Range = resulting $f(x)$.  
- Monotonicity: increasing/decreasing behavior.  
- Symmetry:  
  - Even: $f(-x) = f(x)$  
  - Odd: $f(-x) = -f(x)$  
- Composition: $(f \circ g)(x) = f(g(x))$.  
- Inverse exists iff $f$ is one-to-one.  
- Transformations:  
  - Shift, reflection, stretch, compression.  
  - $f(x - h) + k$ → right by $h$, up by $k$.  

---

✅ **End of File — Chapter 2 (Part A): Functions and Transformations**
