f## 🧭 Conceptual Section (Teach Mode)

### 1. Definition of Derivative

> [!Definition] 💡  
> The **derivative** of a function $f$ at $x = a$ is  
> $$
> f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h},
> $$
> if the limit exists.  
> It represents the **instantaneous rate of change** of $f$ with respect to $x$ at $x = a$.

> [!Notation] 🧮  
> $$
> f'(x), \quad \frac{df}{dx}, \quad \frac{dy}{dx}, \quad Df(x)
> $$

> [!Geometric Interpretation] 📘  
> $f'(a)$ = slope of the tangent to the curve $y = f(x)$ at point $(a, f(a))$.

---

### 2. Differentiability and Continuity

> [!Theorem] 📘  
> If $f$ is **differentiable** at $x = a$, then it is **continuous** at $x = a$.  
> The converse is **not necessarily true**.

> [!Example] 🔍  
> $f(x) = |x|$ is continuous at $x = 0$ but not differentiable there.

---

### 3. Derivative Formulas

> [!Property] 🧮 **Basic Rules**  
> $$
> \frac{d}{dx}(c) = 0, \quad
> \frac{d}{dx}(x) = 1, \quad
> \frac{d}{dx}(x^n) = nx^{n-1}, \ n \in \mathbb{R}.
> $$

> [!Property] 🧮 **Sum and Difference**  
> $$
> \frac{d}{dx}[f(x) \pm g(x)] = f'(x) \pm g'(x).
> $$

> [!Property] 🧮 **Product Rule**  
> $$
> \frac{d}{dx}[f(x)g(x)] = f'(x)g(x) + f(x)g'(x).
> $$

> [!Property] 🧮 **Quotient Rule**  
> $$
> \frac{d}{dx}\left[\frac{f(x)}{g(x)}\right] = 
> \frac{f'(x)g(x) - f(x)g'(x)}{[g(x)]^2}.
> $$

> [!Property] 🧮 **Chain Rule**  
> $$
> \frac{d}{dx}f(g(x)) = f'(g(x)) \cdot g'(x)
> $$

---

### 4. Derivatives of Standard Functions

> [!Property] 🧮  
> $$
> \begin{aligned}
> \frac{d}{dx}(\sin x) &= \cos x, & \frac{d}{dx}(\cos x) &= -\sin x,\\
> \frac{d}{dx}(\tan x) &= \sec^2 x=\frac{1}{\cos^2x}, & \frac{d}{dx}(\cot x) &= -\csc^2 x=\frac{-1}{\sin^2x},\\
> \frac{d}{dx}(\sec x) &= \sec x \tan x, & \frac{d}{dx}(\csc x) &= -\csc x \cot x.
> \end{aligned}
> $$

> [!Property] 🧮  
> $$
> \frac{d}{dx}(e^x) = e^x, \quad
> \frac{d}{dx}(\ln x) = \frac{1}{x}, \; x > 0.
> $$

> [!Property] 🧮  
> $$
> \frac{d}{dx}(a^x) = a^x \ln a, \quad
> \frac{d}{dx}(\log_a x) = \frac{1}{x \ln a}.
> $$

---

### 5. Higher Order Derivatives

> [!Definition] 💡  
> - **Second derivative:** $f''(x) = \frac{d}{dx}(f'(x))$  
> - **n-th derivative:** $f^{(n)}(x) = \frac{d^n f}{dx^n}$

---

### 6. Implicit Differentiation

> [!Definition] 💡  
> If $y$ is defined implicitly by an equation involving $x$ and $y$, differentiate both sides with respect to $x$, applying the Chain Rule to terms containing $y$.

> [!Example] 🔍  
> For $x^2 + y^2 = 25$:  
> Differentiate: $2x + 2y \frac{dy}{dx} = 0$  
> Hence, $\displaystyle \frac{dy}{dx} = -\frac{x}{y}$.

---

### 7. Logarithmic Differentiation

> [!Definition] 💡  
> Used when $y = f(x)$ involves powers or products:  
> Take $\ln$ on both sides, then differentiate.

> [!Example] 🔍  
> $y = x^x$  
> $\ln y = x \ln x$  
> Differentiate: $\frac{1}{y}\frac{dy}{dx} = \ln x + 1$  
> Hence $\frac{dy}{dx} = x^x(\ln x + 1)$.

---

### 8. Derivatives of Inverse Functions

> [!Theorem] 📘  
> If $f$ has an inverse and is differentiable, then  
> $$
> (f^{-1})'(x) = \frac{1}{f'(f^{-1}(x))}.
> $$

> [!Example] 🔍  
> For $f(x) = \sin x$ on $[-\pi/2, \pi/2]$:  
> $$
> (\sin^{-1}x)' = \frac{1}{\cos(\sin^{-1}x)} = \frac{1}{\sqrt{1 - x^2}}.
> $$

---

### 9. Derivatives of Inverse Trigonometric Functions

> [!Property] 🧮  
> $$
> \begin{aligned}
> \frac{d}{dx}(\sin^{-1}x) &= \frac{1}{\sqrt{1 - x^2}}, \\
> \frac{d}{dx}(\cos^{-1}x) &= -\frac{1}{\sqrt{1 - x^2}}, \\
> \frac{d}{dx}(\tan^{-1}x) &= \frac{1}{1 + x^2}, \\
> \frac{d}{dx}(\cot^{-1}x) &= -\frac{1}{1 + x^2}, \\
> \frac{d}{dx}(\sec^{-1}x) &= \frac{1}{|x|\sqrt{x^2 - 1}}, \\
> \frac{d}{dx}(\csc^{-1}x) &= -\frac{1}{|x|\sqrt{x^2 - 1}}.
> \end{aligned}
> $$

---

### 10. Derivatives of Hyperbolic Functions

> [!Property] 🧮  
> $$
> \frac{d}{dx}(\sinh x) = \cosh x, \quad
> \frac{d}{dx}(\cosh x) = \sinh x.
> $$

> [!Property] 🧮  
> $$
> \frac{d}{dx}(\tanh x) = \operatorname{sech}^2 x, \quad
> \frac{d}{dx}(\coth x) = -\operatorname{csch}^2 x.
> $$

---

## 📘 Examples & Applications (Exam Mode)

---

### Example 1 — Using the Limit Definition
_(Using: Definition of Derivative)_

$$
f(x) = x^2 + 2x + 1
$$
Compute $f'(x)$ using first principles.

**Solution:**  
$$
f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h} 
= \lim_{h \to 0} \frac{(x + h)^2 + 2(x + h) + 1 - (x^2 + 2x + 1)}{h}
$$
$$
= \lim_{h \to 0} \frac{2xh + h^2 + 2h}{h} = \lim_{h \to 0}(2x + h + 2) = 2x + 2.
$$

---

### Example 2 — Implicit Differentiation
_(Using: Chain Rule)_

Find $\frac{dy}{dx}$ for $x^3 + y^3 = 6xy$.

**Solution:**  
Differentiate both sides:  
$$
3x^2 + 3y^2 \frac{dy}{dx} = 6y + 6x\frac{dy}{dx}.
$$
Group $\frac{dy}{dx}$ terms:  
$$
(3y^2 - 6x)\frac{dy}{dx} = 6y - 3x^2.
$$
$$
\frac{dy}{dx} = \frac{6y - 3x^2}{3y^2 - 6x}.
$$

---

### Example 3 — Logarithmic Differentiation
_(Using: Logarithmic Differentiation)_

$$
y = (x^2 + 1)^x
$$

**Solution:**  
Take $\ln$ both sides:  
$$
\ln y = x \ln(x^2 + 1)
$$
Differentiate:  
$$
\frac{1}{y}\frac{dy}{dx} = \ln(x^2 + 1) + \frac{2x^2}{x^2 + 1}
$$
$$
\frac{dy}{dx} = (x^2 + 1)^x \left[\ln(x^2 + 1) + \frac{2x^2}{x^2 + 1}\right].
$$

---

### Example 4 — Derivative of Inverse Function
_(Using: Inverse Function Theorem)_

Find derivative of $\tan^{-1}x$.

**Solution:**  
Let $y = \tan^{-1}x \Rightarrow \tan y = x.$  
Differentiate:  
$$
\sec^2 y \frac{dy}{dx} = 1.
$$
Hence,  
$$
\frac{dy}{dx} = \frac{1}{\sec^2 y} = \frac{1}{1 + \tan^2 y} = \frac{1}{1 + x^2}.
$$

---

### Example 5 — Higher Derivative
_(Using: Successive Differentiation)_

For $f(x) = e^{2x}$, find $f''(x)$.

**Solution:**  
$f'(x) = 2e^{2x}$  
$f''(x) = 4e^{2x}$.

---

## 🔑 Summary (Revision Mode)

- $f'(a) = \displaystyle \lim_{h \to 0} \frac{f(a + h) - f(a)}{h}$  
- Differentiable ⇒ Continuous.  
- Basic formulas:
  $$
  (x^n)' = nx^{n-1}, \quad (e^x)' = e^x, \quad (\ln x)' = \frac{1}{x}.
  $$
- Product, Quotient, Chain rules essential for composites.  
- Implicit differentiation for relations $F(x,y)=0$.  
- Logarithmic differentiation simplifies powers/products.  
- $(f^{-1})'(x) = \frac{1}{f'(f^{-1}(x))}$.  
- Trig and inverse trig derivatives are core formulas.  
- Higher derivatives: $f''$, $f^{(n)}$.  
- Geometric meaning: slope of tangent = rate of change.

---

✅ **End of File — Chapter 3: Differentiation**
