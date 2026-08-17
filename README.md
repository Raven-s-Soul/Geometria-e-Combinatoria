# Geometria 1 / Discrete Mathematics & Linear Algebra — Study Notes & Reference

>This repository is organized into dedicated topic directories.
>
>Each directory contains detailed explanations, theoretical foundations, step-by-step procedures, and practical examples.

---

## 🗺️ Course Index & Navigation

* [01. Set Theory, Logic & Mappings](./01-sets-logic-mappings/) — Sets, truth tables, and function classifications.
* [02. Binary Relations: Equivalence & Order](./02-binary-relations/) — Equivalence classes, quotient sets, and orderings.
* [03. Combinatorics & Binomial Theorem](./03-combinatorics/) — Permutations, combinations, and Newton's expansion.
* [04. Number Theory & Linear Congruences](./04-integers-and-congruences/) — $\gcd$, Euclidean algorithm, Bézout, and congruences.
* [05. Matrix Algebra & Operations](./05-matrix-algebra/) — Matrix operations, transposition, and determinants.
* [06. Linear Systems of Equations](./06-linear-systems/) — Rouché-Capelli theorem, Gauss elimination, and Cramer.
* [07. Useful Algebraic Methods & Extra Tools](./07-extra-methods/) — Bézout backtracking and modular inverse algorithms.

---

## 📚 Module Overview

### 1. [Set Theory, Logic & Mappings](./01-sets-logic-mappings/)
* Set operations (union, intersection, difference, complement, Cartesian product)
* Propositional logic, logical connectives ($\neg, \land, \lor, \veebar, \implies, \iff$), and truth tables
* De Morgan's laws, contrapositive proofs, and logical equivalences
* Mappings (functions) between sets: injectivity, surjectivity, and bijectivity
* Composition of mappings and invertibility conditions

### 2. [Binary Relations: Equivalence & Order](./02-binary-relations/)
* Binary relations on sets and fundamental properties (reflexive, symmetric, antisymmetric, transitive)
* Equivalence relations, equivalence classes $[x]$, and quotient sets $A / \sim$
* Partitions of sets and canonical projections
* Order relations: partial order, total order, and well-ordered sets
* Minimal, maximal, infimum, and supremum elements in ordered sets

### 3. [Combinatorics & Binomial Theorem](./03-combinatorics/)
* Fundamental counting principles (addition and multiplication rules)
* Simple permutations $P_n = n!$ and permutations with repetition $P_n^{(n_1, \dots, n_k)}$
* Simple dispositions $D_{n, k}$ and dispositions with repetition $D'_{n, k} = n^k$
* Simple combinations $C_{n, k} = \binom{n}{k}$ and combinations with repetition $C'_{n, k} = \binom{n+k-1}{k}$
* Binomial coefficients, Pascal's triangle identity, and Newton's Binomial Expansion

### 4. [Number Theory & Linear Congruences](./04-integers-and-congruences/)
* Integer divisibility in $\mathbb{Z}$, division algorithm with remainder ($a = bq + r$)
* Greatest Common Divisor ($\gcd(a, b)$ or $\text{MCD}$) and Euclidean Algorithm
* Bézout's Identity ($ax + by = \gcd(a, b)$) and extended Euclidean algorithm
* Congruence modulo $m$ ($a \equiv b \pmod m$) and algebraic properties
* Solvability criteria for linear congruences $ax \equiv b \pmod m$ and modular inverse calculation

### 5. [Matrix Algebra & Operations](./05-matrix-algebra/)
* Matrix definitions, dimensions $\mathbb{R}^{m \times n}$, and standard notation
* Matrix addition, scalar multiplication, and properties of the vector space of matrices
* Matrix multiplication (row-by-column product) and non-commutativity
* Transposition rules ($(AB)^T = B^T A^T$), symmetric ($A^T = A$), and skew-symmetric ($A^T = -A$) matrices
* Square matrices, trace, identity matrix $I_n$, determinant, and invertible matrices

### 6. [Linear Systems of Equations](./06-linear-systems/)
* Matrix formulation of linear systems ($Ax = b$) and augmented matrix $(A \mid b)$
* Rank of a matrix and the Rouché-Capelli Theorem (compatibility conditions)
* Classification of solution spaces (unique solution, $\infty^{n-r}$ solutions, inconsistent)
* Gaussian elimination: elementary row operations, pivots, and Row Echelon Form (REF)
* Back-substitution algorithms and Cramer's Rule for non-singular square systems

### 7. [Useful Algebraic Methods & Extra Tools](./07-extra-methods/)
* **Bézout Backtracking Tableau:** Systematic step-by-step table to extract coefficients $x, y$ from Euclidean remainders
* **Modular Arithmetic Shortcuts:** Fast reduction of large powers modulo $m$ and finding multiplicative inverses
* **Gaussian Row Reduction Worksheets:** Visual guide for tracking row operations without arithmetic sign errors

---

## 📜 License

This repository is distributed under an **All Rights Reserved** License. Refer to the [`LICENSE`](./LICENSE) file for legal details.
