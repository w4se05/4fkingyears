# 📘 Sequences and Limits

---

## 🧩 Definition — Sequence
A **sequence** is a list of numbers written in a definite order:

$$a_{1}, a_{2}, a_{3}, \dots, a_{n}, \dots \equiv \{a_{n}\}$$

| Symbol | Meaning |
|:--|:--|
| $a_1$ | first term |
| $a_2$ | second term |
| $a_n$ | $n$-th term (general term) |

**Types:**
- **Finite Sequence** → has a finite number of terms  
- **Infinite Sequence** → $\{a_n\}_{n=1}^{\infty}$

**Note:**  
Sequences ≠ Sets → *Order matters in sequences, not in sets.*

**Visualization:**  
Can be plotted on a **number line** or **coordinate plane**.  

> 💡 Recognizing the **pattern** is the essence of working with sequences.  
> Signs alternate when you see terms like $(-1)^n$ or $(-1)^{n-1}$.

---

## 📐 Geometric Sequence
$$a, ar, ar^{2}, ar^{3}, \dots$$

Where  
- $a \neq 0$: first term  
- $r \neq 0$: common ratio  

General term:  
$$a_n = ar^{n-1}$$

---

## ➕ Arithmetic Sequence
$$a, a+d, a+2d, a+3d, \dots$$

Where  
- $a$: first term  
- $d$: common difference  

General term:  
$$a_n = a + (n-1)d$$

---

## 📉 Limit of a Sequence
A sequence $\{a_n\}$ has a limit $L$ if:

$$\forall \epsilon > 0, \exists N \in \mathbb{N} : |a_n - L| < \epsilon \text{ for all } n > N$$

Notation:
$$\lim_{n \to \infty} a_n = L \quad \text{or} \quad a_n \to L$$

Special cases:
- $\lim_{n \to \infty} a_{n+1} = \lim_{n \to \infty} a_n = L$
- If $a_n = C$ (constant), then $\lim a_n = C$

**Useful facts:**
- $\lceil a \rceil$: smallest integer ≥ $a$  
- $\lfloor a \rfloor$: largest integer ≤ $a$  
- If $|r| < 1$, then $\lim_{n \to \infty} r^n = 0$

---

## ⚙️ Limit Laws for Sequences
Given $\lim a_n = A$ and $\lim b_n = B$, both convergent:

1. $\lim (a_n \pm b_n) = A \pm B$  
2. $\lim (c a_n) = cA,\; c \in \mathbb{R}$  
3. $\lim (a_n b_n) = AB$  
4. $\lim \left( \dfrac{a_n}{b_n} \right) = \dfrac{A}{B},\; B \neq 0$  
5. If $a_n < b_n$ for all $n \ge N$, then $\lim a_n \le \lim b_n$  
6. $\lim a_n^p = A^p$, if $p > 0$ and $a_n > 0$

---

## 🔄 Convergence & Divergence

| Type | Condition | Example | Result |
|:--|:--|:--|:--|
| **Convergent** | $\lim a_n = L \in \mathbb{R}$ | $a_n = \frac{1}{n}$ | $\to 0$ |
| **Divergent to $\infty$** | $\lim a_n = \pm \infty$ | $a_n = n$ | $\to +\infty$ |
| **Oscillatory** | limit does not exist | $a_n = (-1)^n$ | Divergent |

If $a_n \to L$, then also $a_{n+1} \to L$.

---

## 📏 Boundedness
A sequence $\{a_n\}$ is **bounded** if  
$$|a_n| \le M, \; \forall n \in \mathbb{N}$$

**Examples:**
- $a_n = \frac{n}{n+1}$ → bounded ($M=1$)  
- $a_n = (-1)^n$ → bounded but not convergent  
- $a_n = n$ → unbounded  

---

## 📈 Monotonicity
A sequence $\{a_n\}$ is:
- **Increasing** if $a_{n+1} \ge a_n$  
- **Decreasing** if $a_{n+1} \le a_n$  
- **Monotone** if either increasing or decreasing  

**Examples:**
- $a_n = \frac{n}{n+1}$ → increasing  
- $a_n = \frac{1}{n}$ → decreasing  

**Weierstrass Theorem:**  
Every **bounded monotone sequence** is **convergent**.

---

## ⚡ Squeeze Theorem
Let $\{a_n\}, \{b_n\}, \{c_n\}$ be sequences such that  
$$a_n \le b_n \le c_n \; \forall n \ge N$$  
If  
$$\lim a_n = \lim c_n = L,$$  
then  
$$\lim b_n = L.$$

**Example:**
$$a_n = \frac{(-1)^n}{2\sqrt{n}}$$  
$$-\frac{1}{2\sqrt{n}} \le a_n \le \frac{1}{2\sqrt{n}}$$  
Thus, $\lim a_n = 0$.

---

## 🧮 Miscellaneous Theorems

### Odd–Even Theorem
If  
$$\lim a_{2k} = \lim a_{2k-1} = L,$$  
then $\lim a_n = L$.  
Otherwise, the sequence diverges.

---

### Absolute Value Theorem
If $\lim |a_n| = 0$, then $\lim a_n = 0$.

---

### Ratio Test
Let $r = \frac{a_{n+1}}{a_n}$.

| Condition | Result |
|:--|:--|
| $\lim r > 1$ | $|a_n| \to \infty$ |
| $\lim r < 1$ | $a_n \to 0$ |
| $\lim r = 1$ | Inconclusive |

---

## ✅ Monotone Convergence Example
$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$$
