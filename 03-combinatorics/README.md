# 03-combinatorics: Combinatorics & Binomial Theorem

Foundations of combinatorics, fundamental counting principles, permutations, dispositions, combinations (simple and with repetition), algebraic properties of binomial coefficients, and Newton's binomial theorem.

---

## Table of Contents

1. [Fundamental Counting Principles](#1-fundamental-counting-principles)
2. [Permutations (Simple & with Repetition)](#2-permutations-simple--with-repetition)
3. [Dispositions (Simple & with Repetition)](#3-dispositions-simple--with-repetition)
4. [Combinations (Simple & with Repetition)](#4-combinations-simple--with-repetition)
5. [Summary Comparison Matrix](#5-summary-comparison-matrix)
6. [Binomial Coefficients & Pascal's Identity](#6-binomial-coefficients--pascals-identity)
7. [Newton's Binomial Theorem](#7-newtons-binomial-theorem)

---

## 1. Fundamental Counting Principles

Let $A$ and $B$ be finite sets with $|A| = n$ and $|B| = m$:

* **Sum Rule (Disjoint Sets):**
  If $A \cap B = \emptyset$, the number of ways to choose an element from $A$ or from $B$ is:

$$|A \cup B| = |A| + |B| = n + m$$

* **Product Rule (Cartesian Product):**
  The number of ordered pairs $(a, b)$ with $a \in A$ and $b \in B$ is:

$$|A \times B| = |A| \cdot |B| = n \cdot m$$

* **Inclusion-Exclusion Principle (Two Sets):**

$$|A \cup B| = |A| + |B| - |A \cap B|$$

---

## 2. Permutations (Simple & with Repetition)

A permutation is an ordered arrangement of all $n$ distinct elements of a set.

### 2.1 Simple Permutations
Arrangements of $n$ distinct objects without repetition:

$$P_n = n! = n \cdot (n-1) \cdot (n-2) \cdots 2 \cdot 1$$

* Convention: $0! = 1$.

### 2.2 Permutations with Repetition
Arrangements of $n$ total objects where object $1$ repeats $n_1$ times, object $2$ repeats $n_2$ times, $\dots$, object $k$ repeats $n_k$ times (with $n_1 + n_2 + \dots + n_k = n$):

$$P_n^{(n_1, n_2, \dots, n_k)} = \frac{n!}{n_1! \, n_2! \, \cdots n_k!}$$

---

## 3. Dispositions (Simple & with Repetition)

A disposition (or variation) is an ordered selection of $k$ elements taken from a set of $n$ elements ($k \le n$).

### 3.1 Simple Dispositions
Ordered sequences of $k$ distinct elements chosen from $n$ distinct elements without repetition:

$$D_{n, k} = \frac{n!}{(n-k)!} = n(n-1)(n-2)\cdots(n-k+1)$$

* Note that for $k = n$: $D_{n, n} = P_n = n!$.

### 3.2 Dispositions with Repetition
Ordered sequences of length $k$ chosen from $n$ distinct elements where repetition is allowed:

$$D'_{n, k} = n^k$$

---

## 4. Combinations (Simple & with Repetition)

A combination is an unordered selection (subset) of $k$ elements taken from a set of $n$ elements.

### 4.1 Simple Combinations
Unordered subsets of $k$ distinct elements chosen from $n$ elements without repetition:

$$C_{n, k} = \binom{n}{k} = \frac{D_{n, k}}{P_k} = \frac{n!}{k!(n-k)!}$$

### 4.2 Combinations with Repetition
Unordered selections of $k$ elements from $n$ distinct types, where each type can be selected multiple times:

$$C'_{n, k} = \binom{n + k - 1}{k} = \frac{(n + k - 1)!}{k!(n - 1)!}$$

---

## 5. Summary Comparison Matrix

| Configuration | Order Matters? | Repetition Allowed? | Formula | Domain |
| :--- | :---: | :---: | :--- | :---: |
| **Simple Permutations** | Yes | No | $P_n = n!$ | $n \ge 0$ |
| **Permutations with Repetition** | Yes | Yes | $P_n^{(n_1, \dots, n_k)} = \frac{n!}{n_1! \cdots n_k!}$ | $\sum n_i = n$ |
| **Simple Dispositions** | Yes | No | $D_{n, k} = \frac{n!}{(n-k)!}$ | $0 \le k \le n$ |
| **Dispositions with Repetition** | Yes | Yes | $D'_{n, k} = n^k$ | $k \ge 0$ |
| **Simple Combinations** | No | No | $C_{n, k} = \binom{n}{k} = \frac{n!}{k!(n-k)!}$ | $0 \le k \le n$ |
| **Combinations with Repetition** | No | Yes | $C'_{n, k} = \binom{n+k-1}{k}$ | $k \ge 0$ |

---

## 6. Binomial Coefficients & Pascal's Identity

For integers $n \ge k \ge 0$, the binomial coefficient is defined as:

$$\binom{n}{k} = \frac{n!}{k!(n-k)!}$$

### 6.1 Fundamental Identities
* **Boundary Values:**

$$\binom{n}{0} = \binom{n}{n} = 1, \quad \binom{n}{1} = n$$

* **Symmetry Identity:**

$$\binom{n}{k} = \binom{n}{n - k}$$

* **Pascal's Recurrence Relation:**

$$\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$$

* **Sum of Binomial Coefficients (Cardinality of Power Set):**

$$\sum_{k=0}^n \binom{n}{k} = 2^n$$

* **Alternating Sum of Binomial Coefficients:**

$$\sum_{k=0}^n (-1)^k \binom{n}{k} = 0$$

---

## 7. Newton's Binomial Theorem

For any real numbers $a, b \in \mathbb{R}$ and integer $n \in \mathbb{N}$:

$$(a + b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k$$

### 7.1 Explicit Expansion

$$(a + b)^n = \binom{n}{0} a^n + \binom{n}{1} a^{n-1}b + \binom{n}{2} a^{n-2}b^2 + \dots + \binom{n}{n-1} ab^{n-1} + \binom{n}{n} b^n$$

### 7.2 General Term Formula
The $(k+1)$-th term in the expansion of $(a + b)^n$ is:

$$T_{k+1} = \binom{n}{k} a^{n-k} b^k \quad (k = 0, 1, \dots, n)$$

---

[Back to Main README](../README.md)
