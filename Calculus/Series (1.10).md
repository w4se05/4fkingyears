# 📘 Infinite Series

---

## 🧩 Definition — Infinite Series
Given a sequence $\{a_{n}\}$, the expression  

$$\displaystyle\sum^\infty_{n=1}a_{n}=a_{1}+a_{2}+a_{3}+\dots$$  

is called an **Infinite Series**.

The **Partial Sum** is:  
$$s_{n}=\displaystyle\sum^n_{k=1}a_{k}$$

---

## 🔄 Convergence
If the sequence $\{s_{n}\}$ has a finite limit $s$, then  

$$\displaystyle\sum^\infty_{n=1}a_{n}=s$$  

and the series is **Convergent**. Otherwise, the series is **Divergent**.

> 💡 Note:  
> Convergence for series differs from sequences.  
> - If a series converges, its sum exists and can be computed.  
> - If it diverges, the sum is meaningless.  
> (See lecture slides for examples.)

---

## ⚙️ Algebra of Convergent Series
1. Suppose $\sum a_{n}$ and $\sum b_{n}$ are convergent. Then  
   $$\sum(a_{n}\pm b_{n})=\sum a_{n}\pm \sum b_{n}$$  
2. For any constant $c$,  
   $$\sum c a_{n}=c\sum a_{n}$$

---

### 📜 Theorem — Term Test for Divergence
If $\sum a_{n}$ converges, then $a_{n}\to 0$.

Let $s_{n}=a_{1}+a_{2}+\dots+a_{n}$ be the partial sum.  
If $\sum a_{n}$ converges, then $s_{n}\to S$ for some finite $S$.  

Thus,  
$$a_{n}=s_{n}-s_{n-1}\to S-S=0$$  

Hence, if $\lim_{ n \to \infty }a_{n}\neq 0$, the series **diverges**.  

> ⚠️ This theorem works **one way only** —  
> $a_{n}\to 0$ does **not** guarantee convergence.

---

## ⚖️ Comparison Test
Suppose $0\leq a_{n}\leq b_{n}$ for all $n$.

- If $\sum b_{n}$ **converges**, then $\sum a_{n}$ **also converges**.  
- If $\sum a_{n}$ **diverges**, then $\sum b_{n}$ **also diverges**.

*(Essentially the Squeeze Theorem in series form.)*

---

## 🔢 p-Series Test
For the series  
$$\displaystyle\sum^\infty_{n=1}\frac{1}{n^p}$$  

| Exponent $p$ | Behavior |
|:--|:--|
| $p > 1$ | Converges |
| $p \leq 1$ | Diverges |

---

## 🔍 Limit Comparison Test
If $a_{n},b_{n}>0$ and  
$$\lim_{ n \to \infty } \frac{a_{n}}{b_{n}}=c,\quad 0<c<\infty,$$  
then $\sum a_{n}$ and $\sum b_{n}$ **either both converge or both diverge.**

Special cases:
- If $c=0$ and $\sum b_{n}$ converges → $\sum a_{n}$ converges.  
- If $c=\infty$ and $\sum b_{n}$ diverges → $\sum a_{n}$ diverges.

---

## ⚗️ Ratio Test
For $\sum a_{n}$, let  
$$L=\lim_{ n \to \infty }\left|\frac{a_{n+1}}{a_{n}}\right|.$$

| Condition | Behavior |
|:--|:--|
| $L < 1$ | Series **converges absolutely** |
| $L > 1$ or $L = \infty$ | Series **diverges** |
| $L = 1$ | **Inconclusive** |

---

## 🌱 Root Test
For $\sum a_{n}$, let  
$$L=\lim_{ n \to \infty } \sqrt[n]{|a_{n}| }.$$

| Condition | Behavior |
|:--|:--|
| $L < 1$ | Series **converges absolutely** |
| $L > 1$ or $L = \infty$ | Series **diverges** |
| $L = 1$ | **Inconclusive** |

---

## 🔁 Leibniz Criterion (Alternating Series Test)
Consider $\sum(-1)^{n-1}b_{n}$ with $b_{n}\geq{0}$.  
If:
- $b_{n+1} \leq b_{n}$ (decreasing), and  
- $\lim_{ n \to \infty }b_{n}=0$,  

then the series **converges**.

---

## ⚖️ Absolute and Conditional Convergence
A series $\sum a_{n}$ is:

- **Absolutely convergent** if $\sum|a_{n}|$ converges.  
- **Conditionally convergent** if $\sum a_{n}$ converges but $\sum|a_{n}|$ diverges.

**Remarks:**
- Absolute convergence ⟹ the series converges.  
- Conditional convergence ⟹ convergent, but **not absolutely**.

---
