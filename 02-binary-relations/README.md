# 02-binary-relations: Binary Relations: Equivalence & Order

Foundations of binary relations on sets, fundamental properties of relations, equivalence relations, equivalence classes, quotient sets, set partitions, partial and total orders, and extremal elements in ordered sets.

---

## Table of Contents

1. [Definitions & Fundamental Properties](#1-definitions--fundamental-properties)
2. [Equivalence Relations](#2-equivalence-relations)
3. [Equivalence Classes & Quotient Sets](#3-equivalence-classes--quotient-sets)
4. [Fundamental Theorem on Equivalence Relations & Partitions](#4-fundamental-theorem-on-equivalence-relations--partitions)
5. [Order Relations (Posets)](#5-order-relations-posets)
6. [Special Elements in Ordered Sets](#6-special-elements-in-ordered-sets)

---

## 1. Definitions & Fundamental Properties

A **binary relation** $\mathcal{R}$ from a set $A$ to a set $B$ is a subset of the Cartesian product:

$$\mathcal{R} \subseteq A \times B$$

If $A = B$, $\mathcal{R}$ is called a binary relation on $A$. If $(x, y) \in \mathcal{R}$, we write $x \mathcal{R} y$ ($x$ is in relation with $y$).

### 1.1 Key Properties of a Relation on $A$

| Property | Formal Definition |
| :--- | :--- |
| **Reflexive** | $\forall x \in A, \quad x \mathcal{R} x$ |
| **Antireflexive (Irreflexive)** | $\forall x \in A, \quad (x, x) \notin \mathcal{R}$ |
| **Symmetric** | $\forall x, y \in A, \quad x \mathcal{R} y \implies y \mathcal{R} x$ |
| **Antisymmetric** | $\forall x, y \in A, \quad (x \mathcal{R} y \land y \mathcal{R} x) \implies x = y$ |
| **Transitive** | $\forall x, y, z \in A, \quad (x \mathcal{R} y \land y \mathcal{R} z) \implies x \mathcal{R} z$ |
| **Total (Connected)** | $\forall x, y \in A, \quad x \mathcal{R} y \lor y \mathcal{R} x$ |

---

## 2. Equivalence Relations

A relation $\sim$ on a set $A$ is an **equivalence relation** if and only if it is:
1. **Reflexive:** $\forall x \in A, \, x \sim x$
2. **Symmetric:** $\forall x, y \in A, \, x \sim y \implies y \sim x$
3. **Transitive:** $\forall x, y, z \in A, \, (x \sim y \land y \sim z) \implies x \sim z$

### 2.1 Classic Examples
* **Equality:** $x = y$ on any set $A$.
* **Congruence modulo $m$:** On $\mathbb{Z}$, $a \equiv b \pmod m \iff m \mid (a - b)$.
* **Equipotence (Cardinality):** $A \sim B \iff \exists f: A \to B$ bijective.
* **Vector Parallelism:** On the set of geometric vectors in $\mathbb{R}^n$.

---

## 3. Equivalence Classes & Quotient Sets

Let $\sim$ be an equivalence relation on $A$.

### 3.1 Equivalence Class
The **equivalence class** of an element $x \in A$, denoted by $[x]$ or $[x]_\sim$, is the subset of all elements in $A$ related to $x$:

$$[x] = \{y \in A : y \sim x\}$$

* Any element $y \in [x]$ is called a **representative** of the class $[x]$.
* $[x] = [y] \iff x \sim y$.
* If $[x] \neq [y] \implies [x] \cap [y] = \emptyset$ (distinct classes are disjoint).

### 3.2 Quotient Set (Insieme Quoziente)
The **quotient set** of $A$ modulo $\sim$, denoted by $A / \sim$, is the family of all distinct equivalence classes:

$$A / \sim \;= \{[x] : x \in A\}$$

* **Canonical Projection:** The surjective map $\pi: A \to A / \sim$ defined by:

$$\pi(x) = [x]$$

---

## 4. Fundamental Theorem on Equivalence Relations & Partitions

### 4.1 Partition of a Set
A family $\mathcal{P} = \{A_i\}_{i \in I}$ of non-empty subsets of $A$ is a **partition** of $A$ if:
1. **Non-empty:** $A_i \neq \emptyset, \quad \forall i \in I$
2. **Pairwise Disjoint:** $A_i \cap A_j = \emptyset, \quad \forall i \neq j$
3. **Covering:** $\bigcup_{i \in I} A_i = A$

### 4.2 Equivalence Theorem
There is a one-to-one correspondence between equivalence relations on $A$ and partitions of $A$:
* Given an equivalence relation $\sim$, the quotient set $A / \sim$ forms a **partition** of $A$.
* Conversely, given a partition $\mathcal{P}$ of $A$, the relation defined by:

$$x \sim_\mathcal{P} y \iff \exists S \in \mathcal{P} \text{ such that } x \in S \land y \in S$$

is an **equivalence relation** whose quotient set is exactly $\mathcal{P}$.

---

## 5. Order Relations (Posets)

### 5.1 Partial Order (Ordine Parziale)
A relation $\le$ on a set $A$ is a **partial order** if it is:
1. **Reflexive:** $\forall x \in A, \, x \le x$
2. **Antisymmetric:** $\forall x, y \in A, \, (x \le y \land y \le x) \implies x = y$
3. **Transitive:** $\forall x, y, z \in A, \, (x \le y \land y \le z) \implies x \le z$

A set equipped with a partial order $(A, \le)$ is called a **Partially Ordered Set (Poset)**.

### 5.2 Total Order (Ordine Totale / Lineare)
A partial order $\le$ is a **total order** if every pair of elements is comparable:

$$\forall x, y \in A, \quad x \le y \lor y \le x$$

* *Example of Partial Order:* Inclusion $\subseteq$ on the power set $\mathcal{P}(X)$, or divisibility $\mid$ on $\mathbb{N}$.
* *Example of Total Order:* Standard $\le$ on $\mathbb{R}, \mathbb{Q}, \mathbb{Z}, \mathbb{N}$.

---

## 6. Special Elements in Ordered Sets

Let $(A, \le)$ be a poset, and let $S \subseteq A$.

### 6.1 Extrema of a Subset $S \subseteq A$

| Element | Definition | Uniqueness |
| :--- | :--- | :---: |
| **Minimum ($\min S$)** | $m \in S$ such that $\forall x \in S, \, m \le x$ | Unique (if exists) |
| **Maximum ($\max S$)** | $M \in S$ such that $\forall x \in S, \, x \le M$ | Unique (if exists) |
| **Minimal Element** | $m \in S$ such that $\forall x \in S, \, (x \le m \implies x = m)$ | May be multiple |
| **Maximal Element** | $M \in S$ such that $\forall x \in S, \, (M \le x \implies x = M)$ | May be multiple |

* In a totally ordered set, minimal $\equiv$ minimum, and maximal $\equiv$ maximum.

### 6.2 Bounds (Maggioranti e Minoranti)
* **Lower Bound (Minorante):** $k \in A$ such that $\forall x \in S, \, k \le x$.
* **Upper Bound (Maggiorante):** $K \in A$ such that $\forall x \in S, \, x \le K$.
* **Infimum ($\inf S$):** The greatest lower bound in $A$.
* **Supremum ($\sup S$):** The least upper bound in $A$.

---

[Back to Main README](../README.md)
