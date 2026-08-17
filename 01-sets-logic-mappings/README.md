# 01. Set Theory, Logic & Mappings

Foundational set operations, propositional calculus, truth tables, logical connectives, and function classifications (injective, surjective, bijective).

---

## Table of Contents

1. [Set Theory Fundamentals](#1-set-theory-fundamentals)
2. [Propositional Logic & Truth Tables](#2-propositional-logic--truth-tables)
3. [Logical Equivalences & Laws](#3-logical-equivalences--laws)
4. [Mappings (Functions) & Classifications](#4-mappings-functions--classifications)
5. [Composition and Inverse Mappings](#5-composition-and-inverse-mappings)
6. [Direct Image and Preimage](#6-direct-image-and-preimage)

---

## 1. Set Theory Fundamentals

Let $X$ be a universal set, and let $A, B \subseteq X$.

### 1.1 Fundamental Operations

* **Subset (Inclusione):** $A \subseteq B \iff \forall x, \, (x \in A \implies x \in B)$
* **Union (Unione):**

$$A \cup B = \{x \in X : x \in A \lor x \in B\}$$

* **Intersection (Intersezione):**

$$A \cap B = \{x \in X : x \in A \land x \in B\}$$

* **Set Difference (Differenza):**

$$A \setminus B = \{x \in X : x \in A \land x \notin B\}$$

* **Complement (Complementare):**

$$A^c = \mathcal{C}_X(A) = X \setminus A = \{x \in X : x \notin A\}$$

* **Cartesian Product (Prodotto Cartesiano):**

$$A \times B = \{(a, b) : a \in A, \, b \in B\}$$

* **Power Set (Insieme delle Parti):**

$$\mathcal{P}(A) = \{S : S \subseteq A\} \implies |\mathcal{P}(A)| = 2^{|A|}$$

---

## 2. Propositional Logic & Truth Tables

A proposition is a declarative statement that is either True (**T**) or False (**F**).

### 2.1 Logical Connectives

| Connective | Symbol | Truth Condition |
| :--- | :---: | :--- |
| **Negation (NOT)** | $\neg p$ | True when $p$ is false |
| **Conjunction (AND)** | $p \land q$ | True only if both $p$ and $q$ are true |
| **Disjunction (OR)** | $p \lor q$ | True if at least one proposition is true |
| **Exclusive OR (XOR)** | $p \veebar q$ | True if exactly one proposition is true |
| **Implication** | $p \implies q$ | False only when $p$ is true and $q$ is false |
| **Biconditional (IFF)** | $p \iff q$ | True when $p$ and $q$ have identical truth values |

### 2.2 Standard Truth Table

| $p$ | $q$ | $\neg p$ | $p \land q$ | $p \lor q$ | $p \veebar q$ | $p \implies q$ | $p \iff q$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **T** | **T** | F | T | T | F | T | T |
| **T** | **F** | F | F | T | T | F | F |
| **F** | **T** | T | F | T | T | T | F |
| **F** | **F** | T | F | F | F | T | T |

---

## 3. Logical Equivalences & Laws

* **De Morgan's Laws:**

$$\neg (p \land q) \iff (\neg p) \lor (\neg q)$$

$$\neg (p \lor q) \iff (\neg p) \land (\neg q)$$

* **Material Implication Law:**

$$(p \implies q) \iff (\neg p \lor q)$$

* **Contrapositive Equivalence (Controinversa):**

$$(p \implies q) \iff (\neg q \implies \neg p)$$

* **Distributive Laws:**

$$p \land (q \lor r) \iff (p \land q) \lor (p \land r)$$

$$p \lor (q \land r) \iff (p \lor q) \land (p \lor r)$$

---

## 4. Mappings (Functions) & Classifications

A mapping $f: A \to B$ assigns to every element $x \in A$ (domain) a single element $f(x) \in B$ (codomain).

### 4.1 Injective Mapping (One-to-One / Iniezione)
Distinct domain elements map to distinct codomain elements:

$$\forall x_1, x_2 \in A, \quad f(x_1) = f(x_2) \implies x_1 = x_2$$

$$\text{Equivalently (contrapositive): } x_1 \neq x_2 \implies f(x_1) \neq f(x_2)$$

* If $A$ and $B$ are finite sets: $|A| \le |B|$.

### 4.2 Surjective Mapping (Onto / Suriezione)
Every element in the codomain is reached by at least one element from the domain:

$$\forall y \in B, \quad \exists x \in A : f(x) = y \iff \text{Im}(f) = B$$

* If $A$ and $B$ are finite sets: $|A| \ge |B|$.

### 4.3 Bijective Mapping (Bijection / Biiezione)
The mapping is both injective and surjective:

$$\forall y \in B, \quad \exists! x \in A : f(x) = y$$

* If $A$ and $B$ are finite sets: $|A| = |B|$.

---

## 5. Composition and Inverse Mappings

### 5.1 Function Composition
Given $f: A \to B$ and $g: B \to C$:

$$(g \circ f): A \to C, \quad (g \circ f)(x) = g(f(x))$$

**Properties:**
* Associative: $h \circ (g \circ f) = (h \circ g) \circ f$
* Non-commutative: $g \circ f \neq f \circ g$ in general.
* If $f, g$ are injective $\implies g \circ f$ is injective.
* If $f, g$ are surjective $\implies g \circ f$ is surjective.
* If $f, g$ are bijective $\implies g \circ f$ is bijective.

### 5.2 Inverse Mapping
A function $f: A \to B$ is invertible if and only if it is **bijective**.

The inverse function $f^{-1}: B \to A$ satisfies:

$$(f^{-1} \circ f) = \text{id}_A, \quad (f \circ f^{-1}) = \text{id}_B$$

* **Inverse of Composition:**

$$(g \circ f)^{-1} = f^{-1} \circ g^{-1}$$

---

## 6. Direct Image and Preimage

Let $f: A \to B$:

### 6.1 Direct Image (Immagine Diretta)
For a subset $S \subseteq A$:

$$f(S) = \{f(x) \in B : x \in S\}$$

* $f(\emptyset) = \emptyset$
* $f(S_1 \cup S_2) = f(S_1) \cup f(S_2)$
* $f(S_1 \cap S_2) \subseteq f(S_1) \cap f(S_2)$ (Equality holds if $f$ is injective)

### 6.2 Preimage / Inverse Image (Controimmagine / Preimmagine)
For a subset $T \subseteq B$:

$$f^{-1}(T) = \{x \in A : f(x) \in T\}$$

* Preimages always preserve both unions and intersections:

$$f^{-1}(T_1 \cup T_2) = f^{-1}(T_1) \cup f^{-1}(T_2)$$

$$f^{-1}(T_1 \cap T_2) = f^{-1}(T_1) \cap f^{-1}(T_2)$$

$$f^{-1}(B \setminus T) = A \setminus f^{-1}(T)$$

---

[Back to Main README](../README.md)
