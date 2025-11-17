## 🧭 Overview

This chapter introduces the logical foundations used in algebra and proofs. It covers propositions, logical connectives, truth tables, and fundamental laws of logic used in mathematical reasoning.

---

## 🧩 Conceptual Section (Teach Mode)

### ➤ Propositions and Truth Values

> [!Definition] 💡  
> A **proposition** is a declarative statement that is either **true (T)** or **false (F)**, but not both.

Examples:

- “7 is an odd number.” → **True**
    
- “5 < 2.” → **False**
    
- “Close the door!” → Not a proposition (command, not true/false).
    

---

### ➤ Logical Connectives

Let $p$ and $q$ be propositions. We follow the following order while expressing them.

|Connective|Symbol|Read as|Truth rule (conceptual)|
|---|---|---|---|
|**Negation**|$\neg p$|not $p$|Opposite truth value of $p$|
|**Conjunction**|$p \land q$|$p$ and $q$|True only if both $p$ and $q$ are true|
|**Disjunction**|$p \lor q$|$p$ or $q$|True if at least one of $p$, $q$ is true|
|**Implication**|$p \rightarrow q$|if $p$, then $q$|False only if $p$ is true and $q$ is false|
|**Biconditional**|$p \leftrightarrow q$|$p$ if and only if $q$|True if both have same truth value|

---

### ➤ Compound Propositions

> [!Definition] 🧠  
> A **compound proposition** is built from simpler propositions using logical connectives.

Example:  
If $p$: “The number is even”, and $q$: “The number is divisible by 2”,  
then $p \leftrightarrow q$: “The number is even if and only if it is divisible by 2.”

---

### ➤ Truth Tables (Conceptual Representation)

Example for $p \rightarrow q$:

- When $p = T, q = T \Rightarrow$ True
    
- When $p = T, q = F \Rightarrow$ False
    
- When $p = F, q = T \Rightarrow$ True
    
- When $p = F, q = F \Rightarrow$ True
    

> [!Note] 🗝️  
> The conditional $p \rightarrow q$ is **vacuously true** when $p$ is false, regardless of $q$.

---

### ➤ Logical Equivalence

> [!Definition] ♻️  
> Two propositions $p$ and $q$ are **logically equivalent**, written $p \equiv q$, if they have identical truth values.

Common equivalences:

- **Double negation:** $\neg(\neg p) \equiv p$
    
- **Commutative laws:** $p \lor q \equiv q \lor p$, $p \land q \equiv q \land p$
    
- **Associative laws:** $(p \lor q) \lor r \equiv p \lor (q \lor r)$, and similarly for $\land$
    
- **Distributive laws:** $p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$
    
- **De Morgan’s laws:** $\neg(p \land q) \equiv (\neg p) \lor (\neg q)$, $\neg(p \lor q) \equiv (\neg p) \land (\neg q)$
    
- **Implication forms:** $p \rightarrow q \equiv \neg p \lor q$
    
- **Contrapositive:** $p \rightarrow q \equiv \neg q \rightarrow \neg p$
    

---

### ➤ Tautologies and Contradictions

> [!Definition] 🧩  
> A **tautology** is always true; a **contradiction** is always false.

Examples:

- $p \lor \neg p$ — tautology
    
- $p \land \neg p$ — contradiction
    

---

### ➤ Predicate Logic and Quantifiers

> [!Definition] 🔍  
> A **predicate** is a statement involving a variable, e.g., $P(x): x > 3$.  
> When a value replaces the variable, $P(x)$ becomes a proposition.

Key **quantifiers**:

1. **Universal:** $\forall x, P(x)$ — “For all $x$, $P(x)$ is true.”
    
2. **Existential:** $\exists x, P(x)$ — “There exists at least one $x$ for which $P(x)$ is true.”
    

Negation rules:

- $\neg(\forall x, P(x)) \equiv \exists x, \neg P(x)$
    
- $\neg(\exists x, P(x)) \equiv \forall x, \neg P(x)$
    

---

## 📘 Examples & Applications (Exam Mode)

### 🧮 Example 1 — Simplifying a Logical Expression

Simplify $\neg(\neg p \lor q)$:  
$$  
\begin{align*}  
\neg(\neg p \lor q) &\equiv \neg(\neg p) \land \neg q \quad \text{(De Morgan)} \  
&\equiv p \land \neg q \quad \text{(Double Negation)}  
\end{align*}  
$$  
✅ Final: $p \land \neg q$

---

### 🧮 Example 2 — Showing Two Statements Are Equivalent

Show $\neg p \lor q \equiv p \rightarrow q$.

- By definition, $p \rightarrow q$ is false only when $p = T, q = F$.
    
- $\neg p \lor q$ is true except when $p = T, q = F$.  
    ✅ Equivalent.
    

---

### 🧮 Example 3 — Quantifier Negation

Negate the statement:  
$$  
\forall x \in \mathbb{R}, (x^2 \ge 0)  
$$  
Solution:  
$$  
\neg[\forall x (x^2 \ge 0)] \equiv \exists x (x^2 < 0)  
$$  
✅ Meaning: “There exists a real number $x$ such that $x^2 < 0$.”

---

### 🧮 Example 4 — Determining Logical Type

Determine $(p \rightarrow q) \lor (q \rightarrow p)$.

- At least one conditional is always true.  
    ✅ Therefore, this is a **tautology**.
    

---

## 🧾 Summary

|Concept|Key Formula / Idea|
|---|---|
|Negation|$\neg p$ flips truth value|
|Conjunction|$p \land q$: true if both true|
|Disjunction|$p \lor q$: true if at least one true|
|Implication|$p \rightarrow q \equiv \neg p \lor q$|
|Biconditional|$p \leftrightarrow q$: both same truth value|
|Contrapositive|$p \rightarrow q \equiv \neg q \rightarrow \neg p$|
|De Morgan’s Laws|$\neg(p \lor q) \equiv (\neg p \land \neg q)$|
|Quantifiers|$\neg \forall x P(x) \equiv \exists x \neg P(x)$|
