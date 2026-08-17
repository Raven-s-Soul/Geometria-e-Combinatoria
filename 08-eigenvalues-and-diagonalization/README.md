# 08-eigenvalues-and-diagonalization: Eigenvalues, Eigenvectors & Matrix Diagonalization

Definitions, characteristic polynomial, eigenspaces, algebraic and geometric multiplicities, diagonalizability criteria, construction of modal and diagonal matrices, matrix powers, and the Spectral Theorem for symmetric matrices.

---

## Table of Contents

1. [Eigenvalues & Eigenvectors: Definitions](#1-eigenvalues--eigenvectors-definitions)
2. [Characteristic Polynomial & Spectrum](#2-characteristic-polynomial--spectrum)
3. [Eigenspaces & Multiplicities](#3-eigenspaces--multiplicities)
4. [Diagonalizability Theorems](#4-diagonalizability-theorems)
5. [Step-by-Step Diagonalization Procedure](#5-step-by-step-diagonalization-procedure)
6. [Applications: Matrix Powers](#6-applications-matrix-powers)
7. [Spectral Theorem for Symmetric Matrices](#7-spectral-theorem-for-symmetric-matrices)

---

## 1. Eigenvalues & Eigenvectors: Definitions

Let $A \in \mathbb{R}^{n \times n}$ be a square matrix.

A scalar $\lambda \in \mathbb{R}$ (or $\mathbb{C}$) is called an **eigenvalue** of $A$ if there exists a **non-zero vector** $v \in \mathbb{R}^n \setminus \{0\}$ such that:

$$
A v = \lambda v
$$

* The vector $v \neq 0$ is called an **eigenvector** associated with the eigenvalue $\lambda$.
* Geometrically, $A$ acts on $v$ simply by scaling it by the factor $\lambda$, without altering its span direction.

---

## 2. Characteristic Polynomial & Spectrum

The eigenvalue equation $A v = \lambda v$ can be rewritten as a homogeneous linear system:

$$
(A - \lambda I_n) v = 0
$$

A non-trivial solution $v \neq 0$ exists if and only if the matrix $(A - \lambda I_n)$ is singular:

### 2.1 Characteristic Polynomial
The **characteristic polynomial** of $A$ is defined by:

$$
p_A(\lambda) = \det(A - \lambda I_n)
$$

* $p_A(\lambda)$ is a polynomial of degree $n$ in the variable $\lambda$.
* **Characteristic Equation:** $p_A(\lambda) = 0$.
* **Spectrum:** $\text{Spec}(A)$ denotes the set of all eigenvalues of $A$ (the roots of $p_A(\lambda)$).

### 2.2 Trace and Determinant Invariants
For any $n \times n$ matrix with eigenvalues $\lambda_1, \lambda_2, \dots, \lambda_n$:

$$
\text{tr}(A) = \sum_{i=1}^n \lambda_i = \lambda_1 + \lambda_2 + \dots + \lambda_n
$$

$$
\det(A) = \prod_{i=1}^n \lambda_i = \lambda_1 \cdot \lambda_2 \cdots \lambda_n
$$

---

## 3. Eigenspaces & Multiplicities

### 3.1 Eigenspace
For a given eigenvalue $\lambda$, the **eigenspace** $V_\lambda$ is the set of all eigenvectors associated with $\lambda$, plus the zero vector:

$$
V_\lambda = \ker(A - \lambda I_n) = \{v \in \mathbb{R}^n : (A - \lambda I_n)v = 0\}
$$

$V_\lambda$ is a vector subspace of $\mathbb{R}^n$.

### 3.2 Algebraic Multiplicity - $m_a(\lambda)$
The multiplicity of $\lambda$ as a root of the characteristic equation $p_A(\lambda) = 0$.

### 3.3 Geometric Multiplicity - $m_g(\lambda)$
The dimension of the corresponding eigenspace $V_\lambda$:

$$
m_g(\lambda) = \dim(V_\lambda) = n - \text{rank}(A - \lambda I_n)
$$

### 3.4 Fundamental Multiplicity Inequality
For every eigenvalue $\lambda$:

$$
1 \le m_g(\lambda) \le m_a(\lambda) \le n
$$

* If $m_a(\lambda) = 1$, then $m_g(\lambda) = 1$ automatically.

---

## 4. Diagonalizability Theorems

A square matrix $A \in \mathbb{R}^{n \times n}$ is **diagonalizable** if it is similar to a diagonal matrix $D$, meaning there exists an invertible matrix $P \in \mathbb{R}^{n \times n}$ such that:

$$
P^{-1} A P = D = \begin{pmatrix}
\lambda_1 & 0 & \dots & 0 \\
0 & \lambda_2 & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & \lambda_n
\end{pmatrix}
$$

### 4.1 Fundamental Diagonalization Criterion
A matrix $A \in \mathbb{R}^{n \times n}$ is diagonalizable over $\mathbb{R}$ if and only if **both** conditions hold:

1. **Real Roots:** The characteristic polynomial $p_A(\lambda)$ factors completely into linear factors over $\mathbb{R}$:

$$
\sum_{i=1}^k m_a(\lambda_i) = n
$$

2. **Geometric Regularity:** For every distinct eigenvalue $\lambda_i$, the geometric multiplicity equals the algebraic multiplicity:

$$
m_g(\lambda_i) = m_a(\lambda_i) \quad \forall i = 1, \dots, k
$$

### 4.2 Sufficient Condition
If $p_A(\lambda)$ has $n$ distinct real eigenvalues, then $A$ is guaranteed to be diagonalizable.

---

## 5. Step-by-Step Diagonalization Procedure

Given $A \in \mathbb{R}^{n \times n}$:

1. **Characteristic Polynomial:** Compute $p_A(\lambda) = \det(A - \lambda I_n)$.
2. **Find Eigenvalues:** Solve $p_A(\lambda) = 0$ to get all roots $\lambda_i$ and their algebraic multiplicities $m_a(\lambda_i)$.
3. **Verify Multiplicities:** For each $\lambda_i$, check that:

$$
m_g(\lambda_i) = n - \text{rank}(A - \lambda_i I_n) = m_a(\lambda_i)
$$

4. **Find Eigenspace Bases:** Solve the homogeneous system $(A - \lambda_i I_n)v = 0$ for each $\lambda_i$.
5. **Construct Transition Matrix $P$:** Place the $n$ linearly independent eigenvectors as columns:

$$
P = \begin{pmatrix} v_1 & v_2 & \dots & v_n \end{pmatrix}
$$

6. **Construct Diagonal Matrix $D$:** Place the corresponding eigenvalues along the main diagonal in matching order:

$$
D = \text{diag}(\lambda_1, \lambda_2, \dots, \lambda_n)
$$

---

## 6. Applications: Matrix Powers

Diagonalization allows direct calculation of arbitrary matrix powers $A^k$:

Since $A = P D P^{-1}$, applying induction yields:

$$
A^k = (P D P^{-1})^k = P D^k P^{-1}
$$

Where the power of the diagonal matrix is computed term by term:

$$
D^k = \begin{pmatrix}
\lambda_1^k & 0 & \dots & 0 \\
0 & \lambda_2^k & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & \lambda_n^k
\end{pmatrix}
$$

---

## 7. Spectral Theorem for Symmetric Matrices

Let $A \in \mathbb{R}^{n \times n}$ be a **real symmetric matrix** ($A^T = A$).

### 7.1 Spectral Properties
1. All eigenvalues of $A$ are strictly real.
2. Eigenvectors associated with distinct eigenvalues are mutually orthogonal:

$$
\lambda_i \neq \lambda_j \implies v_i \perp v_j \iff v_i^T v_j = 0
$$

3. $A$ is always orthogonally diagonalizable:

$$
P^T A P = D \quad \text{where } P^{-1} = P^T
$$

### 7.2 Orthonormal Modal Matrix
By normalizing each eigenvector ($u_i = v_i / \|v_i\|$) and applying Gram-Schmidt within eigenspaces with $m_g > 1$, the modal matrix $P$ is orthogonal:

$$
P^T P = P P^T = I_n
$$

---

[Back to Main README](../README.md)
