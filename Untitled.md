# 1. Propositional Logic

### 1.1 Basic Definitions & Connectives
> [!Definition] Statement
> A **statement** (or proposition) is an assertion that is definitely **True ($T$)** or **False ($F$)**.
> * $p, q, r, \dots$: Variables representing statements.
> * **Truth Value**: The logic value ($T$ or $F$) assigned to a statement.

> [!Info] Logical Connectives
> We construct **compound statements** using the following operators:
>
> | Name | Symbol | Meaning | Condition for True ($T$) |
> | :--- | :---: | :--- | :--- |
> | **Negation** | $\neg p$ | NOT | True when $p$ is $F$. |
> | **Conjunction** | $p \land q$ | AND | True only if **both** are $T$. |
> | **Disjunction** | $p \lor q$ | OR | True if **at least one** is $T$ (Inclusive). |
> | **Implication** | $p \Rightarrow q$ | If...then | False **only** if $p$ is $T$ and $q$ is $F$. |
> | **Biconditional** | $p \Leftrightarrow q$ | Iff | True if $p$ and $q$ have the **same** value. |

> [!Warning] Order of Precedence
> When evaluating compound statements without brackets, follow this order:
> 1. $\neg$ (Highest)
> 2. $\land$
> 3. $\lor$
> 4. $\Rightarrow$
> 5. $\Leftrightarrow$ (Lowest)

### 1.2 Logical Equivalence
Two statements $P$ and $Q$ are **logically equivalent** ($P \equiv Q$) if they have identical truth tables (i.e., $P \Leftrightarrow Q$ is a **tautology**).

> [!Theorem] Key Laws of Logic
> **De Morgan's Laws:**
> $$\neg(p \land q) \Leftrightarrow \neg p \lor \neg q$$
> $$\neg(p \lor q) \Leftrightarrow \neg p \land \neg q$$
>
> **Distributive Laws:**
> $$p \land (q \lor r) \Leftrightarrow (p \land q) \lor (p \land r)$$
> $$p \lor (q \land r) \Leftrightarrow (p \lor q) \land (p \lor r)$$
>
> **Implication Equivalence:**
> $$p \Rightarrow q \Leftrightarrow \neg p \lor q$$
>
> **Involution:** $\neg(\neg p) \Leftrightarrow p$

### 1.3 Rules of Inference
An argument is **valid** if the conclusion follows from the truth of the premises (based on a tautology).

| Rule Name | Tautology Form |
| :--- | :--- |
| **Modus Ponens** | $(p \land (p \Rightarrow q)) \Rightarrow q$ |
| **Modus Tollens** | $(\neg q \land (p \Rightarrow q)) \Rightarrow \neg p$ |
| **Hypothetical Syllogism** | $((p \Rightarrow q) \land (q \Rightarrow r)) \Rightarrow (p \Rightarrow r)$ |
| **Disjunctive Syllogism** | $((p \lor q) \land \neg p) \Rightarrow q$ |

---

## 2. Set Theory

### 2.1 Basic Concepts
> [!Definition] Sets & Subsets
> * $x \in A$: $x$ is an element of set $A$.
> * $A \subseteq B$: $A$ is a **subset** of $B$ (every element of $A$ is in $B$).
> * $A \subset B$: $A$ is a **proper subset** ($A \subseteq B$ and $A \neq B$).
> * $\emptyset$: The empty set.
> * $|A|$: The **cardinality** (number of elements) of $A$.

### 2.2 Set Operations
Given a universal set $U$:
1.  **Union:** $A \cup B = \{x \mid x \in A \text{ or } x \in B\}$
2.  **Intersection:** $A \cap B = \{x \mid x \in A \text{ and } x \in B\}$
3.  **Difference:** $A - B$ (or $A \setminus B$) $= \{x \mid x \in A \text{ and } x \notin B\}$
4.  **Complement:** $\bar{A} = \{x \mid x \in U \text{ and } x \notin A\}$
5.  **Cartesian Product:** $A \times B = \{(a, b) \mid a \in A, b \in B\}$

> [!Note] Computer Representation
> Sets can be represented as **bit strings**. If $U = \{e_1, e_2, \dots, e_n\}$, a subset $A$ is a string of length $n$ where the $i$-th bit is $1$ if $e_i \in A$, else $0$.
> * $A \cup B \to$ Bitwise OR
> * $A \cap B \to$ Bitwise AND

---

## 3. Relations

### 3.1 Definition & Representation
> [!Definition] Relation
> A **relation** $R$ from $A$ to $B$ is a subset of $A \times B$. If $A=B$, it is a relation **on** $A$.

**Representations:**
1.  **Matrix Representation ($M_R$):** A zero-one matrix where $m_{ij} = 1$ if $(a_i, a_j) \in R$, else $0$.
2.  **Digraph:** Vertices represent elements; a directed edge $a \to b$ exists if $(a, b) \in R$.

### 3.2 Properties of Relations
Let $R$ be a relation on set $A$.

| Property | Definition | Matrix Condition | Digraph Condition |
| :--- | :--- | :--- | :--- |
| **Reflexive** | $\forall a \in A, (a,a) \in R$ | Main diagonal is all $1$s. | All vertices have self-loops. |
| **Symmetric** | If $(a,b) \in R \Rightarrow (b,a) \in R$ | $M_R = M_R^T$ (Symmetric matrix). | $a \to b \Rightarrow b \to a$. |
| **Antisymmetric** | If $(a,b) \in R \land (b,a) \in R \Rightarrow a=b$ | $m_{ij}=1 \land i \neq j \Rightarrow m_{ji}=0$. | No bidirectional edges between distinct nodes. |
| **Transitive** | If $(a,b) \in R \land (b,c) \in R \Rightarrow (a,c) \in R$ | $M_R \odot M_R \leq M_R$ | Path $a \to b \to c \Rightarrow$ edge $a \to c$. |

### 3.3 Operations on Relations
1.  **Inverse ($R^{-1}$):** $\{(b,a) \mid (a,b) \in R\}$. Matrix is $M_R^T$.
2.  **Composition ($S \circ R$):** Relation from $A$ to $C$ via $B$. $(a, c) \in S \circ R$ if $\exists b, (a,b) \in R \land (b,c) \in S$.
    * **Matrix:** $M_{S \circ R} = M_R \odot M_S$ (Boolean Product).
    * **Boolean Product ($\odot$):** $c_{ij} = \bigvee_{k} (a_{ik} \land b_{kj})$.

### 3.4 Closures
> [!Definition] Closure
> The closure of $R$ with respect to property $P$ is the smallest relation containing $R$ that satisfies $P$.

* **Reflexive Closure:** $R \cup \{(a,a) \mid a \in A\}$. (Add diagonal $1$s).
* **Symmetric Closure:** $R \cup R^{-1}$. (Make connections bidirectional).
* **Transitive Closure ($R^*$):** The connectivity relation.
    $$R^* = R \cup R^2 \cup R^3 \dots \cup R^n$$
    *(Naive computation is slow)*.

> [!Theorem] Warshall's Algorithm (Efficient $R^*$)
> Used to find the transitive closure in $O(n^3)$.
> Let $W_0 = M_R$. Compute sequence $W_1, \dots, W_n$:
> $$W_k[i, j] = W_{k-1}[i, j] \lor (W_{k-1}[i, k] \land W_{k-1}[k, j])$$
> *Interpretation:* Path $i \to j$ exists if there is a direct path OR a path via intermediate vertex $k$.

### 3.5 Equivalence Relations
A relation is an **Equivalence Relation** if it is **Reflexive**, **Symmetric**, and **Transitive**.

* **Notation:** $a \sim_R b$ means $(a, b) \in R$.
* **Equivalence Class ($[a]_R$):** $\{s \mid (a, s) \in R\}$. All elements equivalent to $a$.
* **Fundamental Theorem:** Equivalence classes form a **Partition** of set $A$ (Disjoint blocks covering $A$).

### 3.6 Partial Orderings (Posets)
A relation is a **Partial Ordering** if it is **Reflexive**, **Antisymmetric**, and **Transitive**.
* **Notation:** $(S, \preceq)$.
* **Hasse Diagram:** Visual representation of finite posets.
    1.  Remove self-loops (Reflexivity assumed).
    2.  Remove transitive edges (If $a \to b$ and $b \to c$, remove $a \to c$).
    3.  Draw $b$ above $a$ if $a \preceq b$. No arrows needed.

---

## 4. Number Theory & Cryptography

### 4.1 Modular Arithmetic
> [!Definition] Congruence
> $a \equiv b \pmod n$ if $n \mid (a - b)$.
> $a \pmod n$ is the remainder $r$ when $a = nq + r$.

**Operations in $\mathbb{Z}_n$:**
* Addition: $(a + b) \pmod n$.
* Multiplication: $(a \cdot b) \pmod n$.
* **Inverse:** $a^{-1}$ exists in $\mathbb{Z}_n$ iff $\gcd(a, n) = 1$.

### 4.2 Euclidean Algorithms
1.  **Euclid's Algorithm:** Finds $\gcd(a, b)$ by repeated division.
    * $\gcd(a, b) = \gcd(b, a \pmod b)$.
2.  **Extended Euclid:** Finds integers $s, t$ such that:
    $$\gcd(a, b) = s \cdot a + t \cdot b$$
    * Used to find modular inverses: If $\gcd(a, n)=1$, then $s \cdot a + t \cdot n = 1 \Rightarrow s \cdot a \equiv 1 \pmod n$. So $a^{-1} = s$.

### 4.3 RSA Cryptography
An asymmetric system using a Public Key $(n, e)$ and Private Key $(d)$.

> [!Example] RSA Process
> 1.  **Key Gen:**
>     * Pick large primes $p, q$. Compute $n = p \cdot q$.
>     * Compute Euler's Totient $\phi(n) = (p-1)(q-1)$.
>     * Choose $e$ such that $\gcd(e, \phi(n)) = 1$.
>     * Calculate $d$ such that $d \cdot e \equiv 1 \pmod{\phi(n)}$.
> 2.  **Encryption:** $C = M^e \pmod n$.
> 3.  **Decryption:** $M = C^d \pmod n$.

---

## 📘 Examples & Applications

### Example 1: Finding Transitive Closure (Warshall's)
**Tag:** _Using: Warshall's Algorithm, Matrix Logic_

Given $A = \{1, 2, 3\}$ and relation $R$ with matrix:
$$
M_R = W_0 = \begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
0 & 0 & 0
\end{bmatrix}
$$
Find the transitive closure $R^*$.

**Solution:**
We iterate $k$ from $1$ to $3$.
**Step $k=1$ (Pivot via node 1):**
Column 1 is all 0s except row 2? No, Col 1 is $[0, 0, 0]^T$. No new paths created.
$$W_1 = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

**Step $k=2$ (Pivot via node 2):**
Look at Col 2 ($[1, 0, 0]^T$) and Row 2 ($[0, 0, 1]$).
We have $w_{12}=1$ and $w_{23}=1$.
New path $1 \to 3$ created ($1 \to 2 \to 3$). Set $w_{13} = 1$.
$$W_2 = \begin{bmatrix} 0 & 1 & \mathbf{1} \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

**Step $k=3$ (Pivot via node 3):**
Col 3 is $[1, 1, 0]^T$. Row 3 is $[0, 0, 0]$. No new paths (dead end at 3).
$$W_3 = \begin{bmatrix} 0 & 1 & 1 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

**Final Result:** $R^* = \{(1,2), (1,3), (2,3)\}$.

---

### Example 2: Extended Euclidean & Modular Inverse
**Tag:** _Using: Extended Euclid, Modular Arithmetic_

Find the multiplicative inverse of $13$ modulo $60$, i.e., find $x$ such that $13x \equiv 1 \pmod{60}$.

**Solution:**
We use Extended Euclid to find $\gcd(60, 13)$ and coefficients.

1.  **Forward Division:**
    * $60 = 4(13) + 8$
    * $13 = 1(8) + 5$
    * $8 = 1(5) + 3$
    * $5 = 1(3) + 2$
    * $3 = 1(2) + 1$ (GCD is 1)

2.  **Backward Substitution (Linear Combination):**
    * $1 = 3 - 1(2)$
    * Substitute $2 = 5 - 1(3)$:
        $1 = 3 - 1(5 - 3) = 2(3) - 1(5)$
    * Substitute $3 = 8 - 1(5)$:
        $1 = 2(8 - 5) - 1(5) = 2(8) - 3(5)$
    * Substitute $5 = 13 - 1(8)$:
        $1 = 2(8) - 3(13 - 8) = 5(8) - 3(13)$
    * Substitute $8 = 60 - 4(13)$:
        $1 = 5(60 - 4(13)) - 3(13)$
        $1 = 5(60) - 20(13) - 3(13)$
        $1 = 5(60) - 23(13)$

3.  **Result:**
    $$-23(13) \equiv 1 \pmod{60}$$
    Since we need a positive inverse: $-23 \equiv 37 \pmod{60}$.
    **Inverse is 37.**

---

### Example 3: Logic Argument Validity
**Tag:** _Using: Rules of Inference, Propositional Logic_

Check if the following argument is valid:
> If it rains ($p$), the game is cancelled ($q$).
> The game is not cancelled ($\neg q$).
> Therefore, it did not rain ($\neg p$).

**Solution:**
1.  Translate to symbolic form:
    * Premise 1: $p \Rightarrow q$
    * Premise 2: $\neg q$
    * Conclusion: $\therefore \neg p$
2.  Match with Inference Rules.
    * This matches the form of **Modus Tollens**: $((\neg q) \land (p \Rightarrow q)) \Rightarrow \neg p$.
3.  **Conclusion:** The argument is **Valid**.

---

## 5. Summary Recap

* **Logic:** $p \Rightarrow q$ is only False when $T \Rightarrow F$. Know De Morgan's laws for negating brackets.
* **Sets:** $2^n$ subsets in a power set. Bit strings allow fast set ops.
* **Relations:**
    * **Equivalence:** Refl + Sym + Trans $\to$ Partitions.
    * **Partial Order:** Refl + Antisym + Trans $\to$ Hasse Diagrams.
* **Connectivity:** Warshall's Algorithm ($O(n^3)$) is superior to matrix multiplication powers for finding $R^*$.
* **Number Theory:** To find $a^{-1} \pmod n$, use Extended Euclid to solve $sa + tn = 1$. The inverse is $s$.
* **RSA:** Security relies on the difficulty of factoring $n=pq$. Decryption key $d$ is the modular inverse of $e$.