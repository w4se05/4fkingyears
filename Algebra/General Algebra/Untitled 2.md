# General Algebra: Comprehensive Course Master Note

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
> * $\neg(p \lor q) \equiv \neg p \land \neg q$
>
> **Implication Equivalences:**
> * $p \Rightarrow q \equiv \neg p \lor q$ (Eliminates the arrow).
> * **Contrapositive:** $p \Rightarrow q \equiv \neg q \Rightarrow \neg p$ (Flipping and negating preserves truth).

### 1.2 Rules of Inference
Valid arguments follow specific templates based on tautologies. The comma in an argument represents an **AND** ($\land$), and the conclusion follows via implication ($\Rightarrow$).

| Rule Name | Tautology Form | Explanation |
| :--- | :--- | :--- |
| **Modus Ponens** | $((p \Rightarrow q) \land p) \Rightarrow q$ | If the rule holds and the condition happens, the result must happen. |
| **Modus Tollens** | $((p \Rightarrow q) \land \neg q) \Rightarrow \neg p$ | If the result did **not** happen, the condition must not have happened. |
| **Hypothetical Syllogism** | $((p \Rightarrow q) \land (q \Rightarrow r)) \Rightarrow (p \Rightarrow r)$ | Chaining implications together (A implies B, B implies C $\to$ A implies C). |

---

### 1.3 Set Theory

> [!Definition] Set Fundamentals
> * **Subset ($A \subseteq B$):** $A$ is a subset of $B$ if every single element in $A$ is also found inside $B$.
> * **Union ($A \cup B$):** Combines two sets (Logic: OR). Includes elements in A, B, or both.
> * **Intersection ($A \cap B$):** Filters for common elements (Logic: AND).
> * **Difference ($A \setminus B$):** Elements inside A, but removing anything that is also in B.

> [!Method] Computer Representation
> Computers represent sets as **Bit Strings** to perform operations in milliseconds.
> * **Concept:** Given a universal order, we write `1` if an element exists and `0` if it doesn't.
> * **Operations:** Union becomes `Bitwise OR`; Intersection becomes `Bitwise AND`.

---

### 1.4 Relations (Core Topic)

> [!Definition] Relation & Matrices
> A relation $R$ is a specific connection between elements of a set $A$.
>
> **Matrix Representation ($M_R$):**
> We use a grid of 0s and 1s.
> * $m_{ij} = 1$ if there is a connection from $a_i$ to $a_j$.
> * $m_{ij} = 0$ if there is no connection.

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
> **Definition:** A relation that is **Reflexive**, **Symmetric**, and **Transitive**.
>
> **Function:** It sorts a chaotic set into disjoint buckets called **Equivalence Classes**.
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

### 1.5 Number Theory & Cryptography

#### A. Modular Arithmetic
> [!Formula] Congruence
> $a \equiv b \pmod n$ means $a$ and $b$ leave the same remainder when divided by $n$.
> * **Modular Inverse:** We seek an $x$ such that $ax \equiv 1 \pmod n$.
> * **Condition:** An inverse exists **if and only if** $\gcd(a, n) = 1$.

#### B. Algorithms
> [!Method] Extended Euclidean Algorithm
> The standard tool for finding inverses.
> 1.  Find $\gcd(a, b)$ using repeated division.
> 2.  Work **backwards** to write the equation $s \cdot a + t \cdot b = \gcd(a, b)$.
> 3.  The coefficient $s$ is the modular inverse of $a$.

> [!Method] Fast Modular Exponentiation
> A method to calculate huge powers (like $5^{2000}$) quickly.
> * **Technique:** Convert the exponent to binary. Scan bits left-to-right. Always **Square** the total; if the bit is `1`, also **Multiply** by the base.

#### C. RSA Cryptography
> [!Concept] The RSA Mechanism
> An asymmetric system relying on the difficulty of factoring large numbers.
>
> **The Process:**
> 1.  **Key Gen:** Pick primes $p, q$. Compute $n = pq$. Compute $\phi(n) = (p-1)(q-1)$.
> 2.  **Public Key ($e$):** Choose $e$ coprime to $\phi(n)$.
> 3.  **Private Key ($d$):** Calculate $d = e^{-1} \pmod{\phi(n)}$ using Extended Euclid.
> 4.  **Encrypt:** $C = M^e \pmod n$.
> 5.  **Decrypt:** $M = C^d \pmod n$.

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