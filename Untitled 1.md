# Number Theory & Applications in Cryptography

## I. Conceptual Section (Teach Mode)

### 1. Basic Notions & Divisibility
Number theory primarily deals with the integers, denoted by $\mathbb{Z}$.

> [!Definition] Divisibility
> Let $a, b$ be integers with $a \neq 0$. We say **$a$ divides $b$** (denoted $a \mid b$) if there exists an integer $m$ such that:
> $$b = a \cdot m$$
> * $b$ is a **multiple** of $a$.
> * $a$ is a **factor** of $b$.

> [!Theorem] The Division Algorithm
> Given two arbitrary integers $m$ and $n$ (where $n > 0$), there exist unique integers $q$ (quotient) and $r$ (remainder) such that:
> $$m = n \cdot q + r, \quad 0 \leq r < n$$
> * **Notation:** $q = m \div n$ and $r = m \mod n$.

### 2. Primes and GCD

> [!Definition] Prime & Composite
> A positive integer $p > 1$ is **prime** if it is divisible only by $1$ and itself. An integer greater than $1$ that is not prime is called a **composite number**.

> [!Theorem] Fundamental Theorem of Arithmetic
> Any integer greater than $1$ can be written **uniquely** as a product of powers of distinct primes.

> [!Definition] GCD and LCM
> * **Greatest Common Divisor (GCD):** $\gcd(a, b)$ is the greatest integer $d$ that is a divisor of both $a$ and $b$.
> * **Least Common Multiple (LCM):** $\text{lcm}(a, b)$ is the smallest positive integer that is divisible by both $a$ and $b$.
> * **Theorem:** $a \cdot b = \gcd(a, b) \cdot \text{lcm}(a, b)$.

### 3. Euclidean Algorithms

> [!Algorithm] Euclidean Algorithm (EA)
> To find $\gcd(a, b)$ where $a \ge b$:
> 1.  Let $r_0 = a$ and $r_1 = b$.
> 2.  Apply successive division: $r_{i-2} = q_{i-1} r_{i-1} + r_i$ with $0 \le r_i < r_{i-1}$.
> 3.  The procedure stops when $r_{\ell+1} = 0$. The GCD is the last non-zero remainder $r_{\ell}$.

> [!Theorem] Bezout's Theorem
> If $a$ and $b$ are positive integers, then there exist integers $x$ and $y$ such that:
> $$\gcd(a, b) = a \cdot s + b \cdot t$$

> [!ABSTRACT] Algorithm: Extended Euclidean Algorithm (EEA)
> 
> To find the coefficients $s$ and $t$ such that $\gcd(r_0, r_1) = s \cdot r_0 + t \cdot r_1$, we use recursive formula.
> 
> We set initial values:
> 
> - $s_0 = 1, s_1 = 0$
> - $t_0 = 0, t_1 = 1$
> 
> For each step $i \geq 2$, using the quotient $q_{i-1}$ from the division $r_{i-2} = q_{i-1} r_{i-1} + r_i$, we update:
> 
> $$s_i = s_{i-2} - q_{i-1} \cdot s_{i-1}$$
> 
> $$t_i = t_{i-2} - q_{i-1} \cdot t_{i-1}$$
> 
> At the end, the GCD is expressed as a linear combination of the original numbers.

---

### Modular Arithmetic


> [!Theorem] Euler's Theorem

>
> * **Fermat's Little Theorem:** If $p$ is prime, $a^{p-1} \equiv 1 \pmod p$.

---

## 2. 📘 Examples & Applications

### Example 1: Extended Euclidean Algorithm

**Problem:** Find $\gcd(973, 301)$ and express it as a linear combination.

**Solution:**

**Step 1: Euclidean Division**
$$973 = 3 \cdot 301 + 70$$
$$301 = 4 \cdot 70 + 21$$
$$70 = 3 \cdot 21 + 7$$
$$21 = 3 \cdot 7 + 0$$
$\implies \gcd(973, 301) = 7$.

**Step 2: Linear Combination (Back-Substitution)**
$$7 = 70 - 3(21)$$
Substitute $21 = 301 - 4(70)$:
$$7 = 70 - 3(301 - 4 \cdot 70) = 13 \cdot 70 - 3 \cdot 301$$
Substitute $70 = 973 - 3 \cdot 301$:
$$7 = 13(973 - 3 \cdot 301) - 3 \cdot 301$$
$$7 = 13 \cdot 973 - 42 \cdot 301$$

Result: $\gcd(973, 301) = 13 \cdot 973 + (-42) \cdot 301$.

---

### Example 2: Finding Multiplicative Inverse

**Problem:** Find the multiplicative inverse of $16$ in $Z_{103}$.

**Solution:**
We need to solve $16x \equiv 1 \pmod{103}$. This is equivalent to finding $s, t$ such that $16s + 103t = \gcd(16, 103) = 1$.
Using EEA:
$$103 = 6 \cdot 16 + 7$$
$$16 = 2 \cdot 7 + 2$$
$$7 = 3 \cdot 2 + 1$$

Back substitute:
$$1 = 7 - 3(2) = 7 - 3(16 - 2 \cdot 7) = 7 \cdot 7 - 3 \cdot 16$$
Substitute $7 = 103 - 6 \cdot 16$:
$$1 = 7(103 - 6 \cdot 16) - 3 \cdot 16 = 7 \cdot 103 - 45 \cdot 16$$

Thus, $-45 \cdot 16 \equiv 1 \pmod{103}$.
$-45 \equiv 58 \pmod{103}$.
The inverse is **58**.

---

### Example 3: RSA Cryptography

> [!INFO] RSA System
> 1. **Key Generation:**
>    * Pick large primes $p, q$. Compute $n = p \cdot q$.
>    * Compute $\phi(n) = (p-1)(q-1)$.
>    * Choose public exponent $e$ such that $\gcd(e, \phi(n)) = 1$.
>    * Find private key $d$ such that $d = e^{-1} \pmod{\phi(n)}$.
>    * **Public Key:** $k_{pub} = (n, e)$. **Private Key:** $k_{pri} = d$.
> 2. **Encryption:** $y = x^e \pmod n$.
> 3. **Decryption:** $x = y^d \pmod n$.

**Problem:** Let $p=7, q=11$. Public key $e=7$. Encrypt plaintext $x=5$.

**Solution:**
1.  $n = 7 \cdot 11 = 77$.
    $\phi(n) = 6 \cdot 10 = 60$.
2.  Find $d$: Solve $7d \equiv 1 \pmod{60}$.
    Using EEA, we find $d = 43$.
3.  Encrypt $x=5$:
    $y = 5^7 \pmod{77}$.
    Using **Fast Exponentiation (Binary Method)**:
    $5^1 \equiv 5$
    $5^2 \equiv 25$
    $5^4 \equiv 625 \equiv 9 \pmod{77}$.
    $5^7 = 5^4 \cdot 5^2 \cdot 5^1 \equiv 9 \cdot 25 \cdot 5 \equiv 47 \pmod{77}$.
    
    Ciphertext $y = 47$.

---

## III. Summary

* **Division:** $m = nq + r$.
* **Bezout:** $\gcd(a, b) = ax + by$.
* **Modular Group:** $Z_n^\times$ contains elements relatively prime to $n$.
* **RSA:** Secure because factoring $n$ (to find $\phi(n)$ and thus $d$) is NP-hard.
* **Check Digits:** ISBN-10 uses condition $\sum_{i=1}^{10} i x_i \equiv 0 \pmod{11}$.