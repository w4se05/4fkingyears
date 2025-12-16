## 1. Conceptual Section (Teach Mode)

### 1.1 Propositional Logic

> [!Definition] Statement
> A **statement** (or proposition) is a declarative sentence that is definitively **True ($T$)** or **False ($F$)**. It cannot be an opinion or a question.
> * **Notation:** We typically use variables like $p, q,$ and $r$.
> * *Example:* "$2+2=4$" is a statement because it is definitively True.

> [!Concept] Logical Connectives
> We build complex arguments by connecting simple statements.
>
> | Connective | Symbol | Logic & Explanation |
> | :--- | :---: | :--- |
> | **Negation** | $\neg p$ | **NOT.** It simply flips the value. If $p$ is True, $\neg p$ is False. |
> | **Conjunction** | $p \land q$ | **AND.** This is strict; it is True **only if** both individual components are True. |
> | **Disjunction** | $p \lor q$ | **OR.** This is inclusive. It is True if **at least one** of the components is True. |
> | **Implication** | $p \Rightarrow q$ | **If..then.** Think of this as a **promise**. It is False *only* if the condition ($p$) happens but the result ($q$) does not. If $p$ never happens, the promise isn't broken, so it is Vacuously True. |
> | **Biconditional** | $p \Leftrightarrow q$ | **Iff.** True only when both statements share the exact same truth value. |

> [!Theorem] Key Laws of Logic
> **De Morgan's Laws:**
> These explain how to negate groups.
> * $\neg(p \land q) \equiv \neg p \lor \neg q$ (The negation of "A and B" is "Not A **OR** Not B").
> * $\neg(p \lor q) \equiv \neg p \land \neg q$ (The negation of "A or B" is "Not A **AND** Not B")
>
> **Implication Equivalences:** $p \Rightarrow q \equiv \neg p \lor q$ (Eliminates the arrow).
>  **Contrapositive:** $p \Rightarrow q \equiv \neg q \Rightarrow \neg p$ (Flipping and negating preserves truth).

### 1.2 Rules of Inference

| Rule Name | Tautology Form | Explanation |
| :--- | :--- | :--- |
| **Modus Ponens** | $((p \Rightarrow q) \land p) \Rightarrow q$ | If the rule holds and the condition happens, the result must happen. |
| **Modus Tollens** | $((p \Rightarrow q) \land \neg q) \Rightarrow \neg p$ | If the result did **not** happen, the condition must not have happened. |
| **Hypothetical Syllogism** | $((p \Rightarrow q) \land (q \Rightarrow r)) \Rightarrow (p \Rightarrow r)$ | Chaining implications together (A implies B, B implies C $\to$ A implies C). |

**Tautology:** A statement that is always True (e.g., $p \vee \neg p$). 
**Contradiction:** A statement that is always False (e.g., $p \wedge \neg p$).
**Satisfiable:** A statement is satisfiable if there is at least one assignment of truth values that results in True.

#### Normal Forms
* **Literal:** A variable ($p$) or its negation ($\neg p$).
* **Disjunctive Normal Form (DNF):** A disjunction of conjunctions (e.g., $(p \wedge q) \vee (\neg p \wedge r)$).
* **Conjunctive Normal Form (CNF):** A conjunction of disjunctions (e.g., $(p \vee q) \wedge (\neg p \vee r)$).

#### Quantifiers
Used to turn open sentences (predicates like $f(x)$) into propositions.

* **Universal Quantifier ($\forall$):** $\forall x, f(x)$ means "$f(x)$ is true for all $x$".
* **Existential Quantifier ($\exists$):** $\exists x, f(x)$ means "There exists an $x$ such that $f(x)$ is true".

> [!Tip] Negating Quantifiers
> * $\neg (\forall x, f(x)) \equiv \exists x, \neg f(x)$
> * $\neg (\exists x, f(x)) \equiv \forall x, \neg f(x)$
---

### 1.3 Set Theory

> [!Definition] Set Fundamentals
> * **Subset ($A \subseteq B$):** $A$ is a subset of $B$ if every single element in $A$ is also found inside $B$.
> * **Union ($A \cup B$):** Combines two sets (Logic: OR). Includes elements in A, B, or both.
> * **Intersection ($A \cap B$):** Filters for common elements (Logic: AND).
> * **Difference ($A \setminus B$):** Elements inside A, but removing anything that is also in B.
> * **Symmetric Difference ($A \oplus B$):** $(A \cup B) \setminus (A \cap B)$ or elements in exactly one of the sets.
> * **Complement ($\bar{A}$):** $\{x \in U \mid x \notin A\}$.

> [!Method] Computer Representation
> Computers represent sets as **Bit Strings** to perform operations in milliseconds.
> * **Concept:** Given a universal order, we write `1` if an element exists and `0` if it doesn't.
> * **Operations:** Union becomes `Bitwise OR`; Intersection becomes `Bitwise AND`.

---

### 1.4 Relations (Core Topic)

#### Definitions & Representation

> [!Definition] Relation & Matrices
> A relation $R$ is a specific connection between elements of a set $A$.
>A **Binary Relation** $R$ from set $X$ to set $Y$ is a subset of the Cartesian product $X \times Y$.
>* Notation: $(x,y) \in R$ or $x R y$.
>* **Inverse Relation ($R^{-1}$):** $\{(y,x) \in Y \times X \mid (x,y) \in R\}$.
>
> **Matrix Representation ($M_R$):**
> We use a grid of 0s and 1s.
> * $m_{ij} = 1$ if there is a connection from $a_i$ to $a_j$.
> * $m_{ij} = 0$ if there is no connection.
#### Composite Relations
The composite of $R$ (from $X$ to $Y$) and $S$ (from $Y$ to $Z$), denoted $S \circ R$, is:
$$S \circ R = \{(x,z) \mid \exists y \in Y \text{ such that } (x,y) \in R \text{ and } (y,z) \in S\}$$
* *Matrix:* $M_{S \circ R} = M_R \odot M_S$ (Boolean Product).
#### A. Properties of Relations
To classify a relation, we check for these three specific behaviors:

1.  **Reflexive (The Self Rule):**
    Every element connects to itself. In a matrix, the entire main diagonal is $1$s.
2.  **Symmetric (The Two-Way Rule):**
    If $a$ connects to $b$, then $b$ must connect to $a$. The matrix looks the same if transposed.
3.  **Antisymmetric (The One-Way Rule):**
    Connections never go "both ways" between different items. If $a \to b$ and $b \to a$, then $a$ and $b$ must be the same item.
4.  **Transitive (The Shortcut Rule):**
    If $a \to b$ and $b \to c$, there must be a direct connection $a \to c$.

#### B. Connectivity & Closures
> [!Definition] Transitive Closure ($R^*$)
> $R^*$ represents **reachability**. While $R$ lists direct connections (flights), $R^*$ lists all possible destinations (can I get there eventually?).
> $$R^* = R \cup R^2 \cup \dots \cup R^n$$

> [!Algorithm] Warshall's Algorithm
> A specific method to find $R^*$ in $O(n^3)$ time, avoiding slow matrix multiplication.
>
> **Logic:** We iterate through every node $k$ and treat it as a "bridge".
> **Formula:**
> $$W_k = W_{k-1} \lor (\text{col}_k \text{ of } W_{k-1} \odot \text{row}_k \text{ of } W_{k-1})$$
> * **Explanation:** We keep all old paths ($W_{k-1}$). We add a new path $i \to j$ IF we can go $i \to k$ (found in column $k$) AND $k \to j$ (found in row $k$).

#### C. Equivalence Relations
> [!Concept] The "Grouper"
> **Definition:** An equivalence relation is **Reflexive**, **Symmetric**, and **Transitive**.
>
>**Function:** It sorts a chaotic set into disjoint buckets called **Equivalence Classes**. **Denoted:** $[a]_R$: $\{x \mid (a,x) \in R\}$.
>**Partition:** The set of all equivalence classes partitions $X$.
> * **Theorem:** Every element belongs to exactly one class. Two classes are either identical or completely disjoint.
> * *Example:* "Having the same age" sorts students into non-overlapping age groups.

#### D. Partial Orderings (Posets)
> [!Concept] The "Ranker"
> **Definition:** A relation that is **Reflexive**, **Antisymmetric**, and **Transitive**.
>
> **Function:** It establishes a hierarchy or ranking.
> * **Antisymmetry is Key:** It ensures that if $A$ is ranked higher than $B$, $B$ cannot be higher than $A$ (no cycles).
> * **Hasse Diagrams:** Visual graphs for Posets where we remove loops and transitive lines to show the "skeleton" of the hierarchy.

---

## 1.5 Number Theory & Cryptography
### 1. Basic Notions & Divisibility
Number theory primarily deals with the integers, denoted by $\mathbb{Z}$.

> [!Definition] Divisibility
> Let $a, b \in \mathbb{Z}$ with $a \neq 0$. We say **$a$ divides $b$** (denoted $a \mid b$) if there exists an integer $m$ such that:
> $$b = m \cdot a$$
> * $b$ is a **multiple** of $a$.
> * $a$ is a **factor** or **divisor** of $b$.

> [!Theorem] The Division Algorithm
> Given $a, b \in \mathbb{Z}$ with $a > 0$, there exist unique integers $q$ (quotient) and $r$ (remainder) such that:
> $$b = a \cdot q + r, \quad 0 \leq r < a$$
> * **Notation:** $q = b \text{ div } a$ and $r = b \mod a$.

### 2. Primes and GCD

> [!Definition] Prime & Composite
> An integer $p > 1$ is **prime** if its only positive divisors are $1$ and $p$. Otherwise, it is **composite**.

> [!Theorem] Fundamental Theorem of Arithmetic
> Every integer $n > 1$ can be represented **uniquely** as a product of prime powers:
> $$n = p_1^{e_1} p_2^{e_2} \dots p_k^{e_k}$$
> * Note: Prime factorization is computationally hard (NP-hard), which forms the basis of RSA cryptography.

> [!Definition] GCD and LCM
> * **Greatest Common Divisor (GCD):** $\gcd(a, b)$ is the largest integer $d$ such that $d \mid a$ and $d \mid b$.
> * **Least Common Multiple (LCM):** $\text{lcm}(a, b)$ is the smallest positive integer $m$ such that $a \mid m$ and $b \mid m$.
> * **Relation:** $\gcd(a,b) \cdot \text{lcm}(a,b) = |a \cdot b|$.

### 3. Euclidean Algorithms

> [!Algorithm] Euclidean Algorithm (EA)
> To find $\gcd(r_0, r_1)$:
> 1.  Apply successive division: $r_{i-2} = q_{i-1} r_{i-1} + r_i$
> 2.  Stop when the remainder is $0$. The last non-zero remainder is the GCD.
> 3.  Complexity: $O(\log(\min(a,b)))$.

> [!Theorem] Bezout's Identity
> For any integers $a, b$, there exist integers $s, t$ such that:
> $$\gcd(a, b) = s \cdot a + t \cdot b$$
> These coefficients $s, t$ are found using the **Extended Euclidean Algorithm (EEA)**.

### 4. Modular Arithmetic
> [!Definition] Congruence
> Let $n > 0$. Integers $a$ and $b$ are **congruent modulo $n$**, written $a \equiv b \pmod n$, if $n \mid (a - b)$.
> * Equivalently, $a$ and $b$ have the same remainder when divided by $n$.

> [!Property] Modular Arithmetic Operations
> * $(a + b) \mod n = ((a \mod n) + (b \mod n)) \mod n$
> * $(a \cdot b) \mod n = ((a \mod n) \cdot (b \mod n)) \mod n$
> * $a^m \mod n = ((a \mod n)^m) \mod n$

> [!Definition] The Set $\mathbb{Z}_n$
> $\mathbb{Z}_n = \{0, 1, \dots, n-1\}$ is the set of remainders modulo $n$.
> * **Group Properties:** $(\mathbb{Z}_n, +_n)$ forms an additive group. $(\mathbb{Z}_n^\times, \cdot_n)$ forms a multiplicative group containing elements **coprime** to $n$.

> [!Definition] Multiplicative Inverse
> An element $a$ has an inverse $a^{-1} \pmod n$ if $a \cdot a^{-1} \equiv 1 \pmod n$.
> * **Condition:** The inverse exists **if and only if** $\gcd(a, n) = 1$.

### 5. Euler's Totient & Important Theorems

> [!Definition] Euler's Totient Function $\phi(n)$
> $\phi(n)$ is the count of positive integers less than $n$ that are relatively prime to $n$.
> * If $p$ is prime: $\phi(p) = p - 1$.
> * If $n = p \cdot q$ (distinct primes): $\phi(n) = (p-1)(q-1)$.
> * General formula: $\phi(n) = n \prod_{p|n} (1 - \frac{1}{p})$.

> [!Theorem] Key Theorems
> 1.  **Fermat's Little Theorem:** If $p$ is prime and $\gcd(a, p) = 1$, then $a^{p-1} \equiv 1 \pmod p$.
> 2.  **Euler's Theorem:** If $\gcd(a, n) = 1$, then $a^{\phi(n)} \equiv 1 \pmod n$.

### 6. Cryptography
Cryptography is the study of secure communication.

**A. Symmetric Cryptography (Private Key)**
Sender and Receiver share the same key.
1.  **Shift Cipher (Caesar):** $e(x) = x + k \pmod{26}$.
2.  **Affine Cipher:** $e(x) = ax + b \pmod n$. Requires $\gcd(a, n)=1$.
    * Decryption: $d(y) = a^{-1}(y - b) \pmod n$.

**B. Asymmetric Cryptography (Public Key - RSA)**
Uses a pair of keys: Public $(n, e)$ and Private $d$.

> [!Algorithm] RSA Setup
> 1.  Choose two large primes $p, q$.
> 2.  Compute $n = p \cdot q$ and $\phi(n) = (p-1)(q-1)$.
> 3.  Choose public exponent $e$ such that $\gcd(e, \phi(n)) = 1$.
> 4.  Compute private key $d$ such that $e \cdot d \equiv 1 \pmod{\phi(n)}$ (using Extended Euclidean Algo).
> 5.  **Encryption:** $C = M^e \pmod n$.
> 6.  **Decryption:** $M = C^d \pmod n$.

---

## II. Application Section (Exam Mode)

### 📘 Examples & Applications

#### Example 1: Extended Euclidean Algorithm
**(Using: Euclidean Algorithm, Bezout's Identity)**
Find $\gcd(973, 301)$ and express it as $s \cdot 973 + t \cdot 301$.

**Solution:**
1.  **Forward Pass (Euclidean Algo):**
    $$973 = 3 \cdot 301 + 70$$
    $$301 = 4 \cdot 70 + 21$$
    $$70 = 3 \cdot 21 + 7$$
    $$21 = 3 \cdot 7 + 0$$
    $\implies \gcd(973, 301) = 7$.

2.  **Backward Pass (Substitution):**
    $$7 = 70 - 3(21)$$
    Substitute $21 = 301 - 4(70)$:
    $$7 = 70 - 3(301 - 4 \cdot 70) = 70 - 3 \cdot 301 + 12 \cdot 70 = 13 \cdot 70 - 3 \cdot 301$$
    Substitute $70 = 973 - 3 \cdot 301$:
    $$7 = 13(973 - 3 \cdot 301) - 3 \cdot 301$$
    $$7 = 13 \cdot 973 - 39 \cdot 301 - 3 \cdot 301$$
    $$7 = 13 \cdot 973 - 42 \cdot 301$$
    
    Thus, $s = 13, t = -42$.

#### Example 2: Finding Multiplicative Inverse
**(Using: Modular Arithmetic, EEA)**
Find $4^{-1} \pmod 9$.

**Solution:**
We need $x$ such that $4x \equiv 1 \pmod 9$. This is equivalent to finding $4x + 9y = 1$.
Using EEA on 9 and 4:
$$9 = 2 \cdot 4 + 1$$
$$1 = 9 - 2 \cdot 4$$
Taking mod 9:
$$1 \equiv -2 \cdot 4 \pmod 9$$
$$1 \equiv 7 \cdot 4 \pmod 9$$
Thus, $4^{-1} \equiv -2 \equiv 7 \pmod 9$.

#### Example 3: RSA Encryption/Decryption
**(Using: RSA Algorithm, Fast Exponentiation)**
Let $p=7, q=11$. Choose public key $e=7$.
1.  Find $n$ and $\phi(n)$.
2.  Find private key $d$.
3.  Encrypt message $M=5$.

**Solution:**
1.  $n = p \cdot q = 77$.
    $\phi(n) = (7-1)(11-1) = 6 \cdot 10 = 60$.
2.  Find $d$ such that $e \cdot d \equiv 1 \pmod{60}$, i.e., $7d \equiv 1 \pmod{60}$.
    Using EEA: $60 = 8 \cdot 7 + 4 \to 7 = 1 \cdot 4 + 3 \to 4 = 1 \cdot 3 + 1$.
    Back substitute:
    $1 = 4 - 3 = 4 - (7 - 4) = 2 \cdot 4 - 7 = 2(60 - 8 \cdot 7) - 7 = 2 \cdot 60 - 17 \cdot 7$.
    So, $-17 \cdot 7 \equiv 1 \pmod{60}$.
    $d \equiv -17 \equiv 43 \pmod{60}$.
3.  Encrypt $M=5$:
    $C = M^e \pmod n = 5^7 \pmod{77}$.
    Using Fast Exponentiation ($7 = 111_2 = 4+2+1$):
    $5^1 \equiv 5$
    $5^2 \equiv 25$
    $5^4 \equiv 25^2 = 625 = 8 \cdot 77 + 9 \equiv 9$.
    $5^7 = 5^4 \cdot 5^2 \cdot 5^1 \equiv 9 \cdot 25 \cdot 5 = 9 \cdot 125 \equiv 9 \cdot 48 \pmod{77} \dots = 47$.

---

## III. Summary

* **Division:** $b = aq + r$.
* **Bezout:** $\gcd(a,b) = sa + tb$.
* **Inverse:** $a^{-1} \pmod n$ exists iff $\gcd(a, n)=1$.
* **Euler's Thm:** $a^{\phi(n)} \equiv 1 \pmod n$.
* **RSA Keys:** Public $(n, e)$, Private $d$. Relation: $ed \equiv 1 \pmod{\phi(n)}$.
* **Check Digits:** Used in ISBN/Credit cards (using mod 10/11 sum checks).
---

## 2. Application Section (Exam Mode)

### 📘 Examples & Applications

#### Example 1: Warshall's Algorithm Calculation
**Tag:** _Using: Warshall's Algorithm, Matrix Logic_

Given $A=\{1,2,3\}$ and $W_0 = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{bmatrix}$. Find $W_1$ (the matrix after processing node 1).

**Solution:**
**Step 1: Identify Pivots for $k=1$**
We look at **Column 1** (paths entering 1) and **Row 1** (paths leaving 1).
* Col 1 is $[0, 0, 1]^T$. (Node 3 enters Node 1).
* Row 1 is $[0, 1, 0]$. (Node 1 goes to Node 2).

**Step 2: Apply Logic**
Since we have a path $3 \to 1$ and $1 \to 2$, Warshall's logic creates a shortcut $3 \to 2$.

**Step 3: Update Matrix**
We add a `1` at position $(3,2)$.
$$W_1 = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & \mathbf{1} & 0 \end{bmatrix}$$

---

#### Example 2: Extended Euclidean for Inverse
**Tag:** _Using: Extended Euclid, Bezout's Identity_

Find the multiplicative inverse of $5$ in $\mathbb{Z}_{11}$.

**Solution:**
We need $x$ such that $5x \equiv 1 \pmod{11}$.
1.  **Forward Division:**
    $11 = 2(5) + 1$
2.  **Backward Substitution:**
    $1 = 11 - 2(5)$
3.  **Result:**
    $1 \equiv -2(5) \pmod{11}$
    The inverse is $-2$. In $\mathbb{Z}_{11}$, $-2 \equiv 9$.
    **Answer:** 9.

---

#### Example 3: Proving Equivalence Relations
**Tag:** _Using: Definition of Equivalence_

Prove $R = \{(a,b) : a \equiv b \pmod n\}$ is an equivalence relation.

**Solution:**
1.  **Reflexive:** $a - a = 0$. Since $n$ always divides $0$, $a \equiv a$. (**True**)
2.  **Symmetric:** If $a \equiv b$, then $n \mid (a-b)$. This implies $n \mid -(a-b)$, so $n \mid (b-a)$. Thus $b \equiv a$. (**True**)
3.  **Transitive:** If $a \equiv b$ (diff is $kn$) and $b \equiv c$ (diff is $jn$):
    Adding the differences: $(a-b) + (b-c) = kn + jn \implies a-c = (k+j)n$.
    Since $n$ divides the sum, $a \equiv c$. (**True**)
**Conclusion:** $R$ is an equivalence relation.

---

### Example 1: Proving Logical Equivalence (De Morgan's)
**Task:** Using a truth table, verify that $\neg(p \wedge q) \leftrightarrow (\neg p \vee \neg q)$ is a tautology.

**Solution:**
We construct the table step-by-step.

| $p$ | $q$ | $p \wedge q$ | $\neg(p \wedge q)$ (LHS) | $\neg p$ | $\neg q$ | $\neg p \vee \neg q$ (RHS) | LHS $\leftrightarrow$ RHS |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| T | T | T | **F** | F | F | **F** | **T** |
| T | F | F | **T** | F | T | **T** | **T** |
| F | T | F | **T** | T | F | **T** | **T** |
| F | F | F | **T** | T | T | **T** | **T** |

Since the final column is all **T**, the statement is a tautology.

### Example 2: Computing Transitive Closure (Warshall’s Algorithm)
> [!Info] Using: Warshall's Algorithm
> $W_k[i, j] = W_{k-1}[i, j] \vee (W_{k-1}[i, k] \wedge W_{k-1}[k, j])$
> Concept: "Is there a path from $i$ to $j$ using only intermediate vertices $\{1, \dots, k\}$?"

**Task:** Find the transitive closure matrix $W_n$ for relation $R$ on $\{1, 2, 3\}$ given by:
$$M_R = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$
*(Paths: $1 \to 2$ and $2 \to 3$)*

**Step 0 ($W_0$):** Initialize with $M_R$.
$$W_0 = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

**Step 1 ($k=1$):** Pivot on Row 1, Col 1. No changes because Col 1 is all 0s.
$$W_1 = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

**Step 2 ($k=2$):** Pivot on Row 2, Col 2.
* Look for $1$s in **Col 2** ($W_1[1,2]$) and **Row 2** ($W_1[2,3]$).
* Since $(1,2)$ and $(2,3)$ exist, we create a path $(1,3)$.
* Update $W_2[1,3] = 1$.
$$W_2 = \begin{bmatrix} 0 & 1 & \mathbf{1} \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

**Step 3 ($k=3$):** Pivot on Row 3, Col 3. Row 3 is all 0s, so no new paths can be formed extending from 3.
**Final Result:** $W_3 = W_2$. The transitive closure includes $(1,2), (2,3), (1,3)$.

### Example 3: Set Operations with Bit Strings
**Task:** Given $U=\{1,2,3,4,5\}$, $A=\{1,3,4\}$, $B=\{2,3,4\}$. Find $A \oplus B$ using bit strings.

**Solution:**
1. **Represent Sets:**
   * $A = 10110$ (1st, 3rd, 4th bits set)
   * $B = 01110$ (2nd, 3rd, 4th bits set)
2. **Calculate XOR (Symmetric Difference):**
   * $A \oplus B = 10110 \oplus 01110$
   * Result: $11000$
3. **Convert back to Set:**
   * The 1st and 2nd bits are set.
   * Resulting Set: $\{1, 2\}$.

---

## 3. Summary & Cheatsheet

### Logic
* **Implication:** $p \rightarrow q$ is False only if $T \rightarrow F$. Equivalent to $\neg p \vee q$.
* **Valid Argument:** An argument structure where the premises imply the conclusion is a tautology.
* **Quantifiers:** Negating flips $\forall \leftrightarrow \exists$.

### Sets
* **Cardinality:** $|\mathcal{P}(A)| = 2^{|A|}$.
* **Operations:** $\overline{A \cup B} = \bar{A} \cap \bar{B}$ (De Morgan for Sets).
* **Symmetric Difference ($\oplus$):** Elements in $A$ or $B$, but not both.

### Relations
* **Properties Matrix Check:**
    * Reflexive: Diagonal $= 1$.
    * Symmetric: $M = M^T$.
    * Transitive: $M^2 \le M$ (boolean arithmetic).
* **Equivalence Relation:** Partitions the set into disjoint equivalence classes.
* **Partial Order:** Creates a hierarchy (like $\le$ or $\subseteq$). Visualized with Hasse Diagrams.
* **Warshall's Algorithm:** Efficient way to find connectivity (Transitive Closure).
#### Example 4: RSA Decryption
**Tag:** _Using: RSA Algorithm, Modular Exponentiation_

Given $n=33$. Public key $e=3$. Decrypt ciphertext $y=31$.

**Solution:**
1.  **Factor $n$:** $33 = 3 \times 11$. So $p=3, q=11$.
2.  **Find $\phi(n)$:** $\phi(33) = (3-1)(11-1) = 20$.
3.  **Find Private Key $d$:** We need $d$ such that $3d \equiv 1 \pmod{20}$.
    $3 \times 7 = 21 \equiv 1$. So **$d = 7$**.
4.  **Decrypt:** $x = 31^7 \pmod{33}$.
    Shortcut: $31 \equiv -2 \pmod{33}$.
    $(-2)^7 = -128$.
    $-128 = -4(33) + 4$.
**Plaintext Answer:** 4.

---

## 3. Summary Section

* **Logic:** Remember that $p \Rightarrow q$ works like a promise; it is only False if the promise is broken ($T \to F$). Be comfortable using **Modus Tollens** (denying the result denies the cause) to solve validities.
* **Sets:** Computer sets are bit-strings. Union is OR; Intersection is AND.
* **Relations:**
    * **Equivalence:** Reflexive + Symmetric + Transitive. Creates **Partitions**.
    * **Partial Order:** Reflexive + Antisymmetric + Transitive. Creates **Hasse Diagrams** (Hierarchy).
    * **Connectivity:** Use **Warshall's Algorithm** (Col/Row cross-product) for $O(n^3)$ efficiency.
* **Number Theory:**
    * Inverse exists iff $\gcd(a,n)=1$.
    * RSA relies on factoring $n=pq$.
    * Decryption key $d$ is derived as the inverse of $e$ using Extended Euclid.