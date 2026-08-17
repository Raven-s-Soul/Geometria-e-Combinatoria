# 05-matrix-algebra: Matrix Algebra & Operations

Definitions, matrix spaces, algebraic operations (addition, scalar multiplication, row-by-column product), transposition, symmetric and skew-symmetric matrices, trace, determinants, and matrix inversion.

---

## Table of Contents

1. [Definitions & Special Matrix Classes](#1-definitions--special-matrix-classes)
2. [Linear Operations: Addition & Scalar Multiplication](#2-linear-operations-addition--scalar-multiplication)
3. [Matrix Multiplication (Row-by-Column)](#3-matrix-multiplication-row-by-column)
4. [Matrix Transpose & Symmetries](#4-matrix-transpose--symmetries)
5. [Trace of a Square Matrix](#5-trace-of-a-square-matrix)
6. [Determinant & Laplace Expansion](#6-determinant--laplace-expansion)
7. [Matrix Inversion & Adjugate Matrix](#7-matrix-inversion--adjugate-matrix)
8. [Rank of a Matrix (Minors Method)](#8-rank-of-a-matrix-minors-method)

---

## 1. Definitions & Special Matrix Classes

A real matrix $A \in \mathbb{R}^{m \times n}$ is a rectangular array of real numbers arranged in $m$ rows and $n$ columns:

$$A = (a_{ij}) = \begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}$$

### 1.1 Special Matrix Classes

| Matrix Type | Condition / Form | Properties |
| :--- | :--- | :--- |
| **Square Matrix** | $m = n$ | Defines determinants, eigenvalues, traces |
| **Zero Matrix ($0_{m \times n}$)** | $a_{ij} = 0, \quad \forall i, j$ | Additive neutral element |
| **Identity Matrix ($I_n$)** | $a_{ii} = 1, \quad a_{ij} = 0 \; (i \neq j)$ | Multiplicative neutral element: $A I_n = I_m A = A$ |
| **Diagonal Matrix** | $a_{ij} = 0, \quad \forall i \neq j$ | Easy powers and inversion ($\lambda_i^{-1}$) |
| **Upper Triangular** | $a_{ij} = 0, \quad \forall i > j$ | Determinant is the product of diagonal entries |
| **Lower Triangular** | $a_{ij} = 0, \quad \forall i < j$ | Determinant is the product of diagonal entries |

---

## 2. Linear Operations: Addition & Scalar Multiplication

Let $A, B \in \mathbb{R}^{m \times n}$ and $\lambda, \mu \in \mathbb{R}$.

### 2.1 Matrix Addition
Entrywise sum for matrices of the **same dimensions**:

$$(A + B)_{ij} = a_{ij} + b_{ij}$$

* **Commutative:** $A + B = B + A$
* **Associative:** $(A + B) + C = A + (B + C)$
* **Identity:** $A + 0_{m \times n} = A$
* **Inverse:** $A + (-A) = 0_{m \times n}$

### 2.2 Scalar Multiplication
Entrywise product by a scalar $\lambda \in \mathbb{R}$:

$$(\lambda A)_{ij} = \lambda \cdot a_{ij}$$

* **Distributive over matrices:** $\lambda(A + B) = \lambda A + \lambda B$
* **Distributive over scalars:** $(\lambda + \mu)A = \lambda A + \mu A$
* **Associative:** $(\lambda \mu)A = \lambda(\mu A)$
* **Vector Space Structure:** The set $(\mathbb{R}^{m \times n}, +, \cdot)$ forms a real vector space of dimension $\dim(\mathbb{R}^{m \times n}) = m \cdot n$.

---

## 3. Matrix Multiplication (Row-by-Column)

Given $A \in \mathbb{R}^{m \times p}$ and $B \in \mathbb{R}^{p \times n}$ (the number of columns of $A$ must match the number of rows of $B$), the product $C = A B \in \mathbb{R}^{m \times n}$ has entries:

$$c_{ij} = \sum_{k=1}^p a_{ik} b_{kj} = a_{i1}b_{1j} + a_{i2}b_{2j} + \dots + a_{ip}b_{pj}$$

### 3.1 Properties of Matrix Multiplication
* **Associativity:** $(AB)C = A(BC)$
* **Distributivity:** $A(B + C) = AB + AC$ and $(A + B)C = AC + BC$
* **Scalar Compatibility:** $\lambda(AB) = (\lambda A)B = A(\lambda B)$
* **Non-Commutative:** In general, $AB \neq BA$ even for square matrices.
* **Zero Divisors (Divisori dello Zero):** $AB = 0$ does **not** imply $A = 0$ or $B = 0$.
* **No Cancellation Law:** $AB = AC$ and $A \neq 0$ does **not** imply $B = C$.

---

## 4. Matrix Transpose & Symmetries

The transpose of $A \in \mathbb{R}^{m \times n}$, denoted by $A^T \in \mathbb{R}^{n \times m}$, is obtained by swapping rows with columns:

$$(A^T)_{ij} = a_{ji}$$

### 4.1 Transposition Properties
* $(A^T)^T = A$
* $(A + B)^T = A^T + B^T$
* $(\lambda A)^T = \lambda A^T$
* **Product Rule:** $(AB)^T = B^T A^T$

### 4.2 Symmetries (for Square Matrices $n \times n$)
* **Symmetric Matrix:** $A^T = A \iff a_{ij} = a_{ji}$
* **Skew-Symmetric (Antisymmetric) Matrix:** $A^T = -A \iff a_{ij} = -a_{ji}$ (diagonal entries must be $0$).

> **Canonical Decomposition:** Every square matrix $A$ can be uniquely decomposed into the sum of a symmetric and a skew-symmetric matrix:
> $$A = \underbrace{\frac{A + A^T}{2}}_{\text{Symmetric}} + \underbrace{\frac{A - A^T}{2}}_{\text{Skew-Symmetric}}$$

---

## 5. Trace of a Square Matrix

The trace of a square matrix $A \in \mathbb{R}^{n \times n}$, denoted by $\text{tr}(A)$, is the sum of its main diagonal elements:

$$\text{tr}(A) = \sum_{i=1}^n a_{ii} = a_{11} + a_{22} + \dots + a_{nn}$$

### 5.1 Properties of the Trace
* **Linearity:** $\text{tr}(\alpha A + \beta B) = \alpha \text{tr}(A) + \beta \text{tr}(B)$
* **Transpose Invariance:** $\text{tr}(A^T) = \text{tr}(A)$
* **Cyclic Invariance:** $\text{tr}(AB) = \text{tr}(BA)$ for any $A \in \mathbb{R}^{m \times n}$ and $B \in \mathbb{R}^{n \times m}$.

---

## 6. Determinant & Laplace Expansion

The determinant is a scalar-valued function on square matrices: $\det: \mathbb{R}^{n \times n} \to \mathbb{R}$.

### 6.1 Basic Dimensions

**1x1 Matrix:**

$$
\det(a) = a
$$

**2x2 Matrix:**

$$
\begin{vmatrix}
a & b \\
c & d
\end{vmatrix}
= ad - bc
$$

**3x3 Matrix (Sarrus Rule):**

$$
\begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix}
= (aei + bfg + cdh) - (ceg + bdi + afh)
$$

### 6.2 Laplace Expansion Theorem (General n x n)

Let $A_{ij}$ denote the $(n-1) \times (n-1)$ submatrix obtained by deleting row $i$ and column $j$. The cofactor (algebraic complement) is:

$$
\alpha_{ij} = (-1)^{i+j} \det(A_{ij})
$$

* **Expansion along row $i$:**

$$
\det(A) = \sum_{j=1}^n a_{ij} \alpha_{ij} = \sum_{j=1}^n (-1)^{i+j} a_{ij} \det(A_{ij})
$$

* **Expansion along column $j$:**

$$
\det(A) = \sum_{i=1}^n a_{ij} \alpha_{ij} = \sum_{i=1}^n (-1)^{i+j} a_{ij} \det(A_{ij})
$$

### 6.3 Determinant Properties

* **Binet's Theorem:** $\det(AB) = \det(A) \cdot \det(B)$
* **Transpose:** $\det(A^T) = \det(A)$
* **Scalar Multiplication:** $\det(\lambda A) = \lambda^n \det(A)$ for $A \in \mathbb{R}^{n \times n}$
* **Row Swaps:** Swapping two rows (or columns) reverses the sign: $\det(A') = -\det(A)$
* **Zero Determinant:** If a matrix contains an all-zero row/column, or two proportional rows/columns, $\det(A) = 0$
* **Row Operations:** Adding a linear combination of other rows to a row does not change $\det(A)$
* **Triangular/Diagonal:** $\det(A) = \prod_{i=1}^n a_{ii}$

---

## 7. Matrix Inversion & Adjugate Matrix

A square matrix $A \in \mathbb{R}^{n \times n}$ is **invertible (non-singular / regular)** if there exists a matrix $A^{-1} \in \mathbb{R}^{n \times n}$ such that:

$$A A^{-1} = A^{-1} A = I_n$$

### 7.1 Invertibility Criterion

$$A \text{ is invertible} \iff \det(A) \neq 0$$

If $A$ is invertible:

$$\det(A^{-1}) = \frac{1}{\det(A)}$$

### 7.2 Inverse Formula via Adjugate Matrix
The adjugate matrix $\text{adj}(A)$ is the transpose of the cofactor matrix $(\alpha_{ij})$:

$$\text{adj}(A) = (\alpha_{ij})^T = \begin{pmatrix}
\alpha_{11} & \alpha_{21} & \dots & \alpha_{n1} \\
\alpha_{12} & \alpha_{22} & \dots & \alpha_{n2} \\
\vdots & \vdots & \ddots & \vdots \\
\alpha_{1n} & \alpha_{2n} & \dots & \alpha_{nn}
\end{pmatrix}$$

The inverse is given by:

$$A^{-1} = \frac{1}{\det(A)} \text{adj}(A)$$

### 7.3 Properties of Inverses
* $(A^{-1})^{-1} = A$
* $(AB)^{-1} = B^{-1} A^{-1}$
* $(A^T)^{-1} = (A^{-1})^T$
* $(\lambda A)^{-1} = \frac{1}{\lambda} A^{-1} \quad (\lambda \neq 0)$

---

## 8. Rank of a Matrix (Minors Method)

The **rank** of a matrix $A \in \mathbb{R}^{m \times n}$, denoted by $\text{rank}(A)$ or $\text{rg}(A)$, is the maximum number of linearly independent rows (or columns).

* **Minor of order $k$:** The determinant of a $k \times k$ square submatrix extracted from $A$.
* **Rank Definition via Minors:**
  $\text{rank}(A) = r$ if and only if:
  1. There exists at least one non-zero minor of order $r$.
  2. Every minor of order $r + 1$ (if any exist) is zero.

* **Fundamental Bound:**

$$0 \le \text{rank}(A) \le \min(m, n)$$

---

[Back to Main README](../README.md)
