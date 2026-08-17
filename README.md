# Geometria 1 & Discrete Mathematics — Study Notes & Reference

> This repository is organized into dedicated topic directories.  
> Each directory contains detailed explanations, theoretical foundations, step-by-step procedures, practical examples, and curated learning materials.

---

## 🗺️ Course Index & Navigation

* [01. Set Theory, Logic & Mappings](./01-sets-logic-mappings/) — Sets, truth tables, logic connectives, and function properties.
* [02. Binary Relations: Equivalence & Order](./02-binary-relations/) — Equivalence classes, quotient sets, and partial/total orderings.
* [03. Combinatorics & Binomial Theorem](./03-combinatorics/) — Permutations, combinations, partitions, and Newton's expansion.
* [04. Number Theory & Linear Congruences](./04-integers-and-congruences/) — $\gcd$, Euclidean algorithm, Bézout identity, and Chinese Remainder Theorem.
* [05. Matrix Algebra & Operations](./05-matrix-algebra/) — Matrix operations, transposition, determinants, and matrix inversion.
* [06. Linear Systems of Equations](./06-linear-systems/) — Rouché-Capelli theorem, Gaussian elimination, and Cramer's rule.
* [07. Vector Spaces & Linear Mappings](./07-vector-spaces-and-linear-maps/) — Subspaces, bases, dimension, Grassmann's formula, $\ker$, and $\text{Im}$.
* [08. Eigenvalues & Diagonalization](./08-eigenvalues-and-diagonalization/) — Characteristic polynomial, eigenspaces, and matrix diagonalizability.
* [09. Euclidean Spaces & Orthogonality](./09-euclidean-spaces-orthogonality/) — Inner products, norms, Gram-Schmidt process, and orthogonal projections.
* [10. Extra Resources & Media](./10-extra-resources/) — Curated video lectures, geometric visualizers, Python tools, and reference sheets.

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
* Partitions of sets and canonical projection maps
* Order relations: partial order, total order, and well-ordered sets (Posets)
* Minimal, maximal, minimum, maximum, infimum, and supremum elements

### 3. [Combinatorics & Binomial Theorem](./03-combinatorics/)
* Fundamental counting principles (sum rule and product rule)
* Simple permutations $P_n = n!$ and permutations with repetition $P_n^{(n_1, \dots, n_k)}$
* Simple dispositions $D_{n, k}$ and dispositions with repetition $D'_{n, k} = n^k$
* Simple combinations $C_{n, k} = \binom{n}{k}$ and combinations with repetition $C'_{n, k} = \binom{n+k-1}{k}$
* Binomial coefficients, Pascal's recurrence identity, and Newton's Binomial Expansion

### 4. [Number Theory & Linear Congruences](./04-integers-and-congruences/)
* Integer divisibility in $\mathbb{Z}$ and the Euclidean division algorithm with remainder ($a = bq + r$)
* Greatest Common Divisor ($\gcd(a, b)$ or $\text{MCD}$) and the Euclidean Algorithm
* Bézout's Identity ($ax + by = \gcd(a, b)$) and extended Euclidean backtracking
* Congruence modulo $m$ ($a \equiv b \pmod m$) and algebraic compatibility
* Solvability criteria for linear congruences $ax \equiv b \pmod m$ and modular inverse calculation
* Chinese Remainder Theorem (CRT) for simultaneous systems of modular congruences

### 5. [Matrix Algebra & Operations](./05-matrix-algebra/)
* Matrix definitions, dimensions $\mathbb{R}^{m \times n}$, and standard notation
* Matrix addition, scalar multiplication, and algebraic properties
* Matrix multiplication (row-by-column product), non-commutativity, and zero divisors
* Transposition rules ($(AB)^T = B^T A^T$), symmetric ($A^T = A$), and skew-symmetric ($A^T = -A$) matrices
* Trace of a matrix, determinants (Laplace expansion and Sarrus rule), and matrix inversion via adjugate matrix
* Matrix rank via submatrix minors

### 6. [Linear Systems of Equations](./06-linear-systems/)
* Matrix formulation of linear systems ($Ax = b$) and augmented matrix $(A \mid b)$
* The Rouché-Capelli Theorem (compatibility conditions: $\text{rank}(A) = \text{rank}(A \mid b)$)
* Classification of solution spaces (unique solution, $\infty^{n-r}$ parametric solutions, inconsistent)
* Homogeneous systems ($Ax = 0$) and null spaces
* Gaussian elimination: elementary row operations, pivots, Row Echelon Form (REF), and RREF
* Back-substitution algorithms and Cramer's Rule for non-singular square systems

### 7. [Vector Spaces & Linear Mappings](./07-vector-spaces-and-linear-maps/)
* Axiomatic definition of real vector spaces and vector subspace criteria
* Linear combinations, linear span $\text{Span}(v_1, \dots, v_k)$, and linear independence
* Bases of vector spaces, coordinate vectors, and space dimension
* Subspace operations (sum, direct sum $U \oplus W$) and Grassmann's Dimension Formula
* Linear mappings (homomorphisms): kernel ($\ker(f)$), image ($\text{Im}(f)$), and injectivity/surjectivity criteria
* The Rank-Nullity (Dimension) Theorem ($\dim(V) = \dim(\ker(f)) + \dim(\text{Im}(f))$)
* Associated matrix of a linear map and change of basis transformation ($A' = P^{-1}AP$)

### 8. [Eigenvalues & Diagonalization](./08-eigenvalues-and-diagonalization/)
* Eigenvalues, eigenvectors, and geometric interpretation ($Av = \lambda v$)
* Characteristic polynomial $p_A(\lambda) = \det(A - \lambda I)$ and spectrum of a matrix
* Eigenspaces $V_\lambda = \ker(A - \lambda I)$, algebraic multiplicity $m_a(\lambda)$, and geometric multiplicity $m_g(\lambda)$
* Fundamental diagonalizability criteria ($m_g(\lambda) = m_a(\lambda)$)
* Construction of the modal matrix $P$ and diagonal matrix $D$ ($P^{-1}AP = D$)
* Computing arbitrary matrix powers ($A^k = P D^k P^{-1}$)
* The Spectral Theorem for real symmetric matrices and orthogonal diagonalization ($P^T A P = D$)

### 9. [Euclidean Spaces & Orthogonality](./09-euclidean-spaces-orthogonality/)
* Real inner products $\langle u, v \rangle$, Euclidean vector spaces, and standard dot products
* Induced Euclidean norms $\|v\|$, Cauchy-Schwarz inequality, triangle inequality, and angles between vectors
* Orthogonality, orthogonal sets, and orthogonal complements ($W^\perp$)
* The Gram-Schmidt Orthonormalization Algorithm
* Orthogonal projections onto subspaces and the Best Approximation Theorem
* Orthogonal matrices ($Q^T Q = I$) and length-preserving isometries

### 10. [Extra Resources & Media](./10-extra-resources/)
* **Recommended Video Series:** Curated video lectures (3Blue1Brown's *Essence of Linear Algebra*, MIT 18.06, university lecture playlists)
* **Interactive Visualization Tools:** 2D/3D transformation sandboxes, eigenspace visualizers, and vector field graphers
* **Computational Notebooks & Scripts:** Python (NumPy/SymPy) code snippets for RREF reduction, Bézout step verification, and Gram-Schmidt
* **Cheatsheets & Solved Exercises:** Quick-reference formula sheets and step-by-step exam problems

---

## 📜 License

This repository is distributed under an **All Rights Reserved** License. Refer to the [`LICENSE`](./LICENSE) file for legal details.
