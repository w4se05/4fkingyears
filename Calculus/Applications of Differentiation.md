## 1. Conceptual Section (Teach Mode)

### 1.1 Related Rates

**Goal:** To find an unknown rate of change using other rates that are known.

> [!Definition] Related Rates
> Problems where variables are functions of time $t$, and the variables are related by an equation. Differentiating this equation with respect to $t$ reveals relationships between their rates of change.


### 1.2 Maxima, Minima, and Optimization

Optimization problems involve finding the optimal (best) way of doing something, which reduces to calculating maximum or minimum values.

> [!Definition] Local Extrema
> * A function $f$ has a **local maximum** at $a$ if there exists $\delta > 0$ such that $f(x) \le f(a)$ whenever $|a - x| < \delta$.
> * A **local minimum** is defined similarly ($f(x) \ge f(a)$).
> * An **extreme** is either a local minimum or maximum.

> [!Definition] Absolute (Global) Extrema
> * A function $f$ has an **absolute maximum** at $a$ if $f(x) \le f(a)$ for all $x$ in the domain $D$.
> * An **absolute minimum** is defined similarly.

#### Existence and Critical Points

> [!Theorem] Weierstrass' Theorem
> If $f$ is a continuous function on a closed interval $[a, b]$, then $f$ attains both its maximum and minimum values on $[a, b]$.
> There exist $x_{min}, x_{max} \in [a, b]$ such that:
> $$m = f(x_{min}) \le f(x) \le f(x_{max}) = M \quad \forall x \in [a, b]$$

> [!Theorem] Fermat's Necessary Condition
> If $f$ has a local maximum or minimum at a point $c \in (a, b)$ and $f'(c)$ exists, then:
> $$f'(c) = 0$$

> [!Note] Critical Point
> A critical point is a point where $f'$ vanishes ($f'(x)=0$) or $f'$ does not exist (DNE).

#### The Closed Interval Method
Steps to find absolute extrema on a closed interval $[a, b]$:
1.  Evaluate $f$ at all **critical points** in $(a, b)$.
2.  Evaluate $f$ at the **endpoints** $a$ and $b$.
3.  The largest value is the absolute maximum; the smallest is the absolute minimum.

---

### 1.3 The Mean Value Theorem (MVT)

> [!Theorem] Mean Value Theorem
> If $f$ is continuous on $[a, b]$ and differentiable on $(a, b)$, then there exists $c \in (a, b)$ such that:
> $$f'(c) = \frac{f(b) - f(a)}{b - a}$$
> Or equivalently: $f(b) - f(a) = f'(c)(b - a)$.

> [!Theorem] Rolle's Theorem
> If $f$ is continuous on $[a, b]$, differentiable on $(a, b)$, and $f(a) = f(b)$, then there exists $c \in (a, b)$ such that:
> $$f'(c) = 0$$

---

### 1.4 First and Second Derivatives

#### Monotonicity and First Derivative Test

> [!Theorem] Monotonicity
> Let $f$ be differentiable on an interval $I$:
> * If $f'(x) > 0$ for all $x \in I$, then $f$ is **increasing** on $I$.
> * If $f'(x) < 0$ for all $x \in I$, then $f$ is **decreasing** on $I$.

> [!Theorem] First-Order Derivative Test
> Let $c$ be a critical number of a continuous function $f$:
> * **Local Max:** If $f'$ changes from positive ($+$) to negative ($-$) at $c$.
> * **Local Min:** If $f'$ changes from negative ($-$) to positive ($+$) at $c$.
> * **No Extremum:** If $f'$ does not change sign at $c$.

#### Concavity and Second Derivative Test
![[Screenshot 2025-12-10 134548.png]]

> [!Definition] Concavity
> * **Concave Upward (Convex):** $f'$ is increasing on $I$.
> * **Concave Downward (Concave):** $f'$ is decreasing on $I$.
> * **Inflection Point:** A point where the curve changes concavity.

> [!Theorem] Concavity Test
> Let $f$ be twice differentiable on $I$:
> * If $f''(x) > 0$ for all $x \in I \implies$ **Concave Upward** (Convex).
> * If $f''(x) < 0$ for all $x \in I \implies$ **Concave Downward**.

> [!Theorem] Second-Order Derivative Test
> Let $f'(c) = 0$.
> * If $f''(c) > 0 \implies f(c)$ is a **Local Minimum**.
> * If $f''(c) < 0 \implies f(c)$ is a **Local Maximum**.
> * If $f''(c) = 0 \implies$ The test is **inconclusive**.

---

### 1.5 L'Hôpital's Rule

> [!Theorem] L'Hôpital's Rule
> Let $f(x)$ and $g(x)$ be differentiable on $I \setminus \{a\}$ with $g'(x) \ne 0$.
> Suppose we have an indeterminate form of type $\frac{0}{0}$ or $\frac{\pm \infty}{\pm \infty}$.
>
> If $\lim_{x \to a} \frac{f'(x)}{g'(x)}$ exists (or is $\pm \infty$), then:
> $$\lim_{x \to a} \frac{f(x)}{g(x)} = \lim_{x \to a} \frac{f'(x)}{g'(x)}$$
> *Note: This rule also applies to limits where $x \to \pm \infty$.*

---

### 1.6 Newton's Method

**Goal:** To provide numerical approximations to the zeros (roots) of a function $f(x)$.



> [!Method] Newton's Iteration Formula
> To find a root of $f(x) = 0$:
> 1.  Choose an initial guess $x_1$ near the root.
> 2.  Form the tangent line at $(x_1, f(x_1))$.
> 3.  Find where the tangent intersects the x-axis to get $x_2$.
> 4.  Repeat using the formula:
> $$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$

---

## 2. 📘 Examples & Applications (Exam Mode)

### Example 1: Sliding Ladder
*`(Using: Related Rates)`*

**Problem:** A 10 ft ladder rests against a vertical wall. The bottom slides away at $1 \text{ ft/s}$. How fast is the top sliding down when the bottom is 6 ft from the wall?

**Solution:**
1.  **Define Variables:**
    Let $x$ be the distance from the bottom to the wall.
    Let $y$ be the distance from the top to the ground.
    Given: $\frac{dx}{dt} = 1$, find $\frac{dy}{dt}$ when $x = 6$.

2.  **Relate Variables:**
    By Pythagorean Theorem: $x^2 + y^2 = 10^2 = 100$.

3.  **Differentiate:**
    Differentiate with respect to $t$:
    $$2x \frac{dx}{dt} + 2y \frac{dy}{dt} = 0$$

4.  **Solve:**
    When $x_0 = 6$, we find $y_0$: $6^2 + y^2 = 100 \implies y_0 = \sqrt{64} = 8$.
    Substitute values:
    $$\frac{dy}{dt} = - \frac{x_0}{y_0} \frac{dx}{dt} = - \frac{6}{8} \cdot 1 = - \frac{3}{4} \text{ ft/s}$$

**Answer:** The top slides down at $3/4 \text{ ft/s}$.

---

### Example 2: Spherical Balloon
*`(Using: Related Rates)`*

**Problem:** Air is pumped into a spherical balloon. Volume increases at $100 \text{ cm}^3/\text{s}$. How fast is the radius increasing when the diameter is 50 cm?

**Solution:**
1.  **Formula:** $V = \frac{4}{3}\pi r^3$.
2.  **Differentiate:** $\frac{dV}{dt} = 4\pi r^2 \frac{dr}{dt}$.
3.  **Solve for Rate:**
    $$\frac{dr}{dt} = \frac{1}{4\pi r^2} \frac{dV}{dt}$$
    Given diameter $= 50 \implies r = 25$. Given $\frac{dV}{dt} = 100$.
    $$\frac{dr}{dt} = \frac{1}{4\pi (25)^2} \times 100 = \frac{100}{2500\pi} = \frac{1}{25\pi} \text{ cm/s}$$

---

### Example 3: Finding Extrema on Closed Interval
*`(Using: Closed Interval Method)`*

**Problem:** Find extremum values of $f(x) = x^2 - 2x + 1$ on $[0, 3]$.

**Solution:**
1.  **Find Critical Points:**
    $f'(x) = 2x - 2 = 0 \implies x = 1$.
2.  **Evaluate Critical Point:**
    $f(1) = 1^2 - 2(1) + 1 = 0$.
3.  **Evaluate Endpoints:**
    $f(0) = 1$
    $f(3) = 3^2 - 6 + 1 = 4$.
4.  **Conclusion:**
    Minimum value: $0$ at $x_{min} = 1$.
    Maximum value: $4$ at $x_{max} = 3$.

---

### Example 4: Indeterminate Limit
*`(Using: L'Hôpital's Rule)`*

**Problem:** Compute $\lim_{x \to 0} \frac{e^x - e^{-x} - 2\sin x}{x - \sin x}$.

**Solution:**
1.  **Check Form:** At $x=0$, numerator is $1 - 1 - 0 = 0$, denominator is $0 - 0 = 0$. Form is $\frac{0}{0}$.
2.  **Apply L'Hôpital (1st time):**
    $$\lim_{x \to 0} \frac{e^x + e^{-x} - 2\cos x}{1 - \cos x}$$
    At $x=0$, this is $\frac{1+1-2}{1-1} = \frac{0}{0}$. Apply again.
3.  **Apply L'Hôpital (2nd time):**
    $$\lim_{x \to 0} \frac{e^x - e^{-x} + 2\sin x}{\sin x}$$
    At $x=0$, this is $\frac{0}{0}$. Apply again.
4.  **Apply L'Hôpital (3rd time):**
    $$\lim_{x \to 0} \frac{e^x + e^{-x} + 2\cos x}{\cos x}$$
    Evaluate: $\frac{1 + 1 + 2(1)}{1} = 4$.

**Answer:** 4.

---

### Example 5: Root Approximation
*`(Using: Newton's Method)`*

**Problem:** Approximate the root of $x^3 - 2x - 5 = 0$ starting with $x_1 = 2$.

**Solution:**
1.  **Set up:**
    $f(x) = x^3 - 2x - 5 \implies f'(x) = 3x^2 - 2$.
    Formula: $x_{n+1} = x_n - \frac{x_n^3 - 2x_n - 5}{3x_n^2 - 2}$.
2.  **Iteration 1:**
    $f(2) = -1$, $f'(2) = 10$.
    $x_2 = 2 - \frac{-1}{10} = 2.1$.
3.  **Iteration 2:**
    $x_3 = 2.1 - \frac{f(2.1)}{f'(2.1)} \approx 2.1 - \frac{0.061}{11.23} \approx 2.094681$.
4.  **Refinement:**
    Continuing iterations gives $x \approx 2.094551$.

---

## 3. Summary Section

* **Critical Point:** $f'(x)=0$ or DNE.
* **Fermat's Theorem:** Local extrema occur at critical points (if derivative exists).
* **Closed Interval Method:** Check critical points inside + endpoints.
* **MVT:** $f'(c) = \frac{f(b)-f(a)}{b-a}$.
* **1st Derivative Test:**
    * $f': (+) \to (-) \implies$ Max.
    * $f': (-) \to (+) \implies$ Min.
* **Concavity:** $f'' > 0$ is Convex (Up), $f'' < 0$ is Concave (Down).
* **2nd Derivative Test:**
    * $f''(c) < 0 \implies$ Max.
    * $f''(c) > 0 \implies$ Min.
* **L'Hôpital:** Use derivatives for $\frac{0}{0}$ or $\frac{\infty}{\infty}$ limits.
* **Newton's Method:** $x_{new} = x_{old} - \frac{f(x_{old})}{f'(x_{old})}$.