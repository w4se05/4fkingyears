
## 1. Binary Choice Questions
*Evaluate as True (t) or False (f).* 
\[cite:.*?\]
1.  **Statement:** Transpose of an invertible matrix is invertible. 
    * **Answer: True**
    * **Reasoning:** If $A$ is invertible, then $(A^T)^{-1} = (A^{-1})^T$. The determinant $\det(A^T) = \det(A) \neq 0$, so the transpose is also invertible.

2.  **Statement:** Given a square matrix $A$ such that $\det A=0$. Then the system $Ax=0$ is inconsistent. 
    * **Answer: False**
    * **Reasoning:** A homogeneous system ($Ax=0$) is **always** consistent because the trivial solution ($x=0$) always exists. If $\det A = 0$, there are infinitely many solutions, not zero solutions (inconsistent).

3.  **Statement:** Let $S$ be a spanning set for a finite dimensional vector space $V$. Then, the dimension of $V$ is equal to $|S|$. 
    * **Answer: False**
    * **Reasoning:** The size of a spanning set $|S|$ is greater than or equal to the dimension of $V$. Only if $S$ is a *basis* (linearly independent spanning set) is the size equal to the dimension.

4.  **Statement:** $-2020 \mod 7 = 4$ 
    * **Answer: False**
    * **Reasoning:**
        * Perform division: $2020 \div 7$. $2020 = 7 \times 288 + 4$.
        * So, $2020 \equiv 4 \pmod 7$.
        * Therefore, $-2020 \equiv -4 \pmod 7$.
        * To find the positive residue: $-4 + 7 = 3$.
        * $3 \neq 4$.

5.  **Statement:** Let $n$ denote an RSA modulus and $e$ an RSA public exponent. Then $e$ must satisfy $\gcd(e,\phi(n))=1$. 
    * **Answer: True**
    * **Reasoning:** This is the requirement for the modular multiplicative inverse $d$ (the private key) to exist.

---

## 2. Short Answer Questions
*Insert answers in the blanks.* 

**(a) Matrix Operations**
Given $B = \begin{bmatrix}1&3\\2&-4\\3&5\end{bmatrix}$ and $C = \begin{bmatrix}-1&2&-4\\5&3&-1\end{bmatrix}$. Find $2B - C^T$. 

* **Step 1:** Calculate $2B$:
    $$2 \begin{bmatrix}1&3\\2&-4\\3&5\end{bmatrix} = \begin{bmatrix}2&6\\4&-8\\6&10\end{bmatrix}$$
* **Step 2:** Calculate $C^T$ (Transpose):
    $$\begin{bmatrix}-1&2&-4\\5&3&-1\end{bmatrix}^T = \begin{bmatrix}-1&5\\2&3\\-4&-1\end{bmatrix}$$
* **Step 3:** Subtract:
    $$\begin{bmatrix}2&6\\4&-8\\6&10\end{bmatrix} - \begin{bmatrix}-1&5\\2&3\\-4&-1\end{bmatrix} = \begin{bmatrix}2-(-1)&6-5\\4-2&-8-3\\6-(-4)&10-(-1)\end{bmatrix} = \begin{bmatrix}3&1\\2&-11\\10&11\end{bmatrix}$$

**Answer:** $\begin{bmatrix}3&1\\2&-11\\10&11\end{bmatrix}$

**(b) Vector Area**
Given $u=(2,3)$ and $v=(4,1)$ in $\mathbb{R}^2$. Area of parallelogram? 

* **Reasoning:** Area is the absolute value of the determinant of the matrix formed by vectors $u$ and $v$.
    $$\text{Area} = |\det(u, v)| = |(2)(1) - (3)(4)| = |2 - 12| = |-10| = 10$$

**Answer:** $10$

**(c) Subsets**
Set $A = \{1, 2, ..., n\}$. Total subsets containing both 1 and $n$. 

* **Reasoning:** We must include 1 and $n$. For the remaining $n-2$ elements, each can either be in the subset or not (2 choices each).
    $$\text{Total} = 2^{n-2}$$

**Answer:** $2^{n-2}$

**(d) Relations**
Given matrix representation $M_R = \begin{pmatrix}1&0&1\\0&1&1\end{pmatrix}$ for sets {mouse, case} to {black, white, orange}. 

* **Mapping:**
    * Rows: $r_1=$ mouse, $r_2=$ case.
    * Cols: $c_1=$ black, $c_2=$ white, $c_3=$ orange.
* **Entries with 1:**
    * (1,1) $\to$ (mouse, black)
    * (1,3) $\to$ (mouse, orange)
    * (2,2) $\to$ (case, white)
    * (2,3) $\to$ (case, orange)

**Answer:** $R = \{(\text{mouse, black}), (\text{mouse, orange}), (\text{case, white}), (\text{case, orange})\}$ 


## 3. Homogeneous Linear System
Consider the system: 
$$
\begin{cases}
x+2y-z+2t=0 \\
2x+4y+z-2t=0 \\
3x+6y+2z-6t=0
\end{cases}
$$

**(a) Coefficient Matrix** 
**Answer:**
$$A = \begin{bmatrix} 1 & 2 & -1 & 2 \\ 2 & 4 & 1 & -2 \\ 3 & 6 & 2 & -6 \end{bmatrix}$$

**(b) Prove W is a subspace** 
**Proof:** $W$ is the set of solutions to a homogeneous linear system $Ax=0$. This is the Null Space (Kernel) of matrix $A$. 
The Kernel of a linear map is always a subspace because:
1.  $A(0) = 0$, so $0 \in W$.
2.  If $u, v \in W$, then $A(u+v) = Au + Av = 0+0=0$, so $u+v \in W$.
3.  If $c \in \mathbb{R}, u \in W$, then $A(cu) = c(Au) = c(0) = 0$, so $cu \in W$.

**(c) Basis and Dimension** 
Use Gaussian Elimination on $A$:
1.  $R_2 \leftarrow R_2 - 2R_1$:
    $$\begin{bmatrix} 1 & 2 & -1 & 2 \\ 0 & 0 & 3 & -6 \\ 3 & 6 & 2 & -6 \end{bmatrix}$$
2.  $R_3 \leftarrow R_3 - 3R_1$:
    $$\begin{bmatrix} 1 & 2 & -1 & 2 \\ 0 & 0 & 3 & -6 \\ 0 & 0 & 5 & -12 \end{bmatrix}$$
3.  From Row 2: $3z - 6t = 0 \implies z = 2t$.
4.  Substitute into Row 3: $5(2t) - 12t = 0 \implies 10t - 12t = -2t = 0 \implies t=0$.
5.  If $t=0$, then $z = 2(0) = 0$.
6.  Substitute into Row 1: $x + 2y - 0 + 0 = 0 \implies x = -2y$.
7.  $y$ is a free variable.

Solution vector: $v = (x, y, z, t) = (-2y, y, 0, 0) = y(-2, 1, 0, 0)$.

**Basis:** $\{(-2, 1, 0, 0)\}$
**Dimension:** 1

---

## 4. Matrix Inversion
Given $A = \begin{pmatrix}2&1&2\\0&3&-1\\4&1&1\end{pmatrix}$. 

**(a) Prove A is invertible** 
Calculate determinant $\det(A)$:
Expand along the first column (or row 1):
$$\det(A) = 2 \begin{vmatrix} 3 & -1 \\ 1 & 1 \end{vmatrix} - 0 + 4 \begin{vmatrix} 1 & 2 \\ 3 & -1 \end{vmatrix}$$
$$= 2(3 - (-1)) + 4(-1 - 6)$$
$$= 2(4) + 4(-7)$$
$$= 8 - 28 = -20$$
Since $\det(A) = -20 \neq 0$, $A$ is invertible.

**(b) Find the inverse of A** 
Using the cofactor matrix method $C_{ij}$:
* $C_{11} = (3)(1) - (-1)(1) = 4$
* $C_{12} = -(0 - (-4)) = -4$
* $C_{13} = 0 - 12 = -12$
* $C_{21} = -(1 - 2) = 1$
* $C_{22} = 2 - 8 = -6$
* $C_{23} = -(2 - 4) = 2$
* $C_{31} = -1 - 6 = -7$
* $C_{32} = -(-2 - 0) = 2$
* $C_{33} = 6 - 0 = 6$

Matrix of Cofactors $C = \begin{pmatrix} 4 & -4 & -12 \\ 1 & -6 & 2 \\ -7 & 2 & 6 \end{pmatrix}$.
Adjugate is $C^T = \begin{pmatrix} 4 & 1 & -7 \\ -4 & -6 & 2 \\ -12 & 2 & 6 \end{pmatrix}$.
$$A^{-1} = \frac{1}{-20} \begin{pmatrix} 4 & 1 & -7 \\ -4 & -6 & 2 \\ -12 & 2 & 6 \end{pmatrix}$$

**(c) Solve $Ax = b$ where $b=(1, 2, 1)$** 
$$x = A^{-1}b = -\frac{1}{20} \begin{pmatrix} 4 & 1 & -7 \\ -4 & -6 & 2 \\ -12 & 2 & 6 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix}$$
Multiply rows by $b$:
1.  $4(1) + 1(2) - 7(1) = 4 + 2 - 7 = -1$
2.  $-4(1) - 6(2) + 2(1) = -4 - 12 + 2 = -14$
3.  $-12(1) + 2(2) + 6(1) = -12 + 4 + 6 = -2$

$$x = -\frac{1}{20} \begin{pmatrix} -1 \\ -14 \\ -2 \end{pmatrix} = \begin{pmatrix} 1/20 \\ 7/10 \\ 1/10 \end{pmatrix}$$

---

## 5. Linear Maps
$T$ is rotation counterclockwise by $\pi/4$. 

**(a) Find $T(e_1)$ and $T(e_2)$** 
Rotation matrix structure for angle $\theta$:
Col 1 ($e_1$): $(\cos \theta, \sin \theta)$
Col 2 ($e_2$): $(-\sin \theta, \cos \theta)$

For $\theta = \pi/4$:
$$T(e_1) = (\cos \frac{\pi}{4}, \sin \frac{\pi}{4}) = \left(\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2}\right)$$
$$T(e_2) = (-\sin \frac{\pi}{4}, \cos \frac{\pi}{4}) = \left(-\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2}\right)$$

**(b) Matrix Representation** 
$$[T] = \begin{bmatrix} \frac{\sqrt{2}}{2} & -\frac{\sqrt{2}}{2} \\ \frac{\sqrt{2}}{2} & \frac{\sqrt{2}}{2} \end{bmatrix} = \frac{\sqrt{2}}{2} \begin{bmatrix} 1 & -1 \\ 1 & 1 \end{bmatrix}$$

**(c) Find $T^2(3e_1 - 2e_2)$** 
$T$ rotates by $45^\circ$. $T^2$ is the composition of $T$ with itself, meaning a rotation by $45^\circ + 45^\circ = 90^\circ$ ($\pi/2$).
Rotation by $90^\circ$ maps $(x, y) \to (-y, x)$.
Input vector: $v = 3e_1 - 2e_2 = (3, -2)$.
$$T^2(3, -2) = (-(-2), 3) = (2, 3)$$

---

## 6. Propositional Logic I

**(a) Equivalence** 
Show $p \to q \equiv \neg p \vee q$.
This is the standard definition of implication.
* If $p$ is T, $q$ must be T for expression to be T. ($\neg T \vee T = T$).
* If $p$ is F, expression is T regardless of $q$. ($\neg F \vee q = T \vee q = T$).
* Matches truth table of $p \to q$.

**(b) Negation (without conditional)** 
i. "I have no special talent ($p$) AND I am only passionately curious ($q$)."
   * Original: $\neg S \wedge C$
   * Negation: $\neg(\neg S \wedge C) \equiv S \vee \neg C$
   * **Answer:** "I have special talent OR I am not only passionately curious."

ii. $(p \vee q) \to r$
   * Use equivalence from 6a: $\neg(p \vee q) \vee r$
   * Negate this: $\neg(\neg(p \vee q) \vee r) \equiv (p \vee q) \wedge \neg r$
   * **Answer:** $(p \vee q) \wedge \neg r$

**(c) Validity** 
Premise 1: Exam Easy $\to$ Pass ($E \to P$)
Premise 2: Pass ($P$)
Conclusion: Exam Easy ($E$)
**Validity:** **Invalid**. This is the fallacy of affirming the consequent. You could pass for other reasons (e.g., you studied hard).

---

## 7. Propositional Logic II

**(a) De Morgan Law** 
Verify $\neg(p \vee q) = \neg p \wedge \neg q$ via Truth Table.

| p | q | p $\vee$ q | $\neg(p \vee q)$ | $\neg p$ | $\neg q$ | $\neg p \wedge \neg q$ |
|---|---|---|---|---|---|---|
| T | T | T | **F** | F | F | **F** |
| T | F | T | **F** | F | T | **F** |
| F | T | T | **F** | T | F | **F** |
| F | F | F | **T** | T | T | **T** |

Columns match. Verified.

**(b) Negation** 
"If a machine is expected to be infallible ($p$), it cannot also be intelligent ($q$)." ($p \to q$)
* Negation of $p \to q$ is $p \wedge \neg q$.
* **Answer:** "A machine is expected to be infallible AND it is intelligent."

**(c) Satisfiability** 
Formula: $(p \to q) \wedge (p \to \neg q)$.
We need to find truth values for $p, q$ that make this true.
* If $p = \text{False}$:
    * $F \to q$ is True.
    * $F \to \neg q$ is True.
    * $T \wedge T = T$.
* **Answer:** Satisfiable when $p$ is False (q can be T or F).

**(d) Validity of Inference** 
1. $J \vee \neg S$ (Jasmine skis OR Not Snowing)
2. $S \vee B$ (Snowing OR Bart plays hockey)
3. Therefore: $J \vee B$.
* **Reasoning:** This is the **Resolution Rule**. If it is snowing ($S$), Bart plays hockey ($B$). If it is not snowing ($\neg S$), Jasmine Skis ($J$). In either case (snow or no snow), one of the outcomes ($J$ or $B$) must occur.
* **Answer:** Valid.

---

## 8. Relations
$A_n$ are bit strings. $R_n$ relates strings with same number of 1s. 

**(a) List elements of $R_2$** 
$A_2 = \{00, 01, 10, 11\}$.
* 0 ones: $\{00\}$. Pair: $(00, 00)$.
* 1 one: $\{01, 10\}$. Pairs: $(01, 01), (01, 10), (10, 01), (10, 10)$.
* 2 ones: $\{11\}$. Pair: $(11, 11)$.

**(b) Matrix Representation** 
Ordering: $00, 01, 10, 11$.
$$M_{R_2} = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 1 & 0 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}$$

**(c) Properties** 
This is an **Equivalence Relation**.
* **Reflexive:** Yes (string has same 1s as itself).
* **Symmetric:** Yes (if $a$ has same 1s as $b$, $b$ has same as $a$).
* **Transitive:** Yes.
* **Answer:** Circle (i), (ii), (iv), (vi).

**(d) Partition** 
Since it's an equivalence relation (vi), show partition of $A_3$ ($A_3 = \{000, 001, 010, 100, 011, 101, 110, 111\}$).
* $C_0$ (0 ones): $\{000\}$
* $C_1$ (1 one): $\{001, 010, 100\}$
* $C_2$ (2 ones): $\{011, 101, 110\}$
* $C_3$ (3 ones): $\{111\}$

---

## 9. Checksum
*Requires Matriculation Number ($x_1...x_k$).* 

**Method to solve (Example ID: 12345):**
1.  **Formula:** $\sum_{i=1}^{k} i \cdot x_i \pmod{11}$.
    For 12345: $1(1) + 2(2) + 3(3) + 4(4) + 5(5) = 1 + 4 + 9 + 16 + 25 = 55$.
    $55 \pmod{11} = 0$.
2.  **Check digit ($x_{k+1}$):** 
    We need $\sum_{i=1}^{k+1} i \cdot x_i \equiv 0 \pmod{11}$.
    Let $S$ be the sum from part (a). We need $S + (k+1)x_{k+1} \equiv 0 \pmod{11}$.
    Solve for $x_{k+1}$.

---

## 10. RSA Cryptography
$n = 91$. 
$91 = 7 \times 13$. ($p=7, q=13$).

**(a) Euler's Totient $\phi(n)$** 
$$\phi(91) = (7-1)(13-1) = 6 \times 12 = 72$$

**(b) Find public exponent $e$** 
Criteria: $\gcd(e, 72) = 1$. Prompt asks for "non-trivial second smallest valid exponent".
* Candidates (integers $>1$):
    * 2: $\gcd(2, 72) \neq 1$
    * 3: $\gcd(3, 72) = 3 \neq 1$
    * 4: $\gcd(4, 72) \neq 1$
    * **5:** $\gcd(5, 72) = 1$. (Smallest)
    * 6: $\gcd(6, 72) \neq 1$
    * **7:** $\gcd(7, 72) = 1$. (Second Smallest)

**Answer:** $e = 7$.

**(c) Encrypt $x=87$** 
Using $e=7$.
Cipher $C = 87^7 \pmod{91}$.
Note that $87 \equiv -4 \pmod{91}$.
$C \equiv (-4)^7 = -16384 \pmod{91}$.
$16384 \div 91$: $16384 = 180 \times 91 + 4$.
So $16384 \equiv 4 \pmod{91}$.
Thus $-16384 \equiv -4 \equiv 87 \pmod{91}$.
**Answer:** 87.

**(d) Find private exponent $d$** 
Solve $de \equiv 1 \pmod{72}$ using $e=7$.
Extended Euclidean Algorithm on 72 and 7:
1.  $72 = 10(7) + 2$
2.  $7 = 3(2) + 1$
3.  Back substitute:
    $1 = 7 - 3(2)$
    $1 = 7 - 3(72 - 10(7))$
    $1 = 7 - 3(72) + 30(7)$
    $1 = 31(7) - 3(72)$
Thus, $31 \times 7 \equiv 1 \pmod{72}$.
**Answer:** $d = 31$.

**(e) RSA Risk** 
* **Risk:** If the plaintext $x$ is not relatively prime with $n$ ($\gcd(x, n) \neq 1$), then $x$ shares a factor with $n$ (either $p$ or $q$).
* **Attack:** The attacker can compute $\gcd(x_{\text{intercepted}}, n)$. This calculation (Euclidean algorithm) is very fast and will yield one of the prime factors of $n$ (e.g., 7 or 13). Once a factor is known, the attacker can compute $\phi(n)$ and the private key $d$.