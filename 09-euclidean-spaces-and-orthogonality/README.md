# 09-euclidean-spaces-and-orthogonality: Euclidean Spaces, Inner Products & Orthogonality

Bilinear forms, positive-definite real inner products, induced norms, Cauchy-Schwarz and triangle inequalities, orthogonality, orthogonal complements, the Gram-Schmidt orthonormalization algorithm, orthogonal projections, and orthogonal matrices.

---

## Table of Contents

1. [Real Inner Products & Euclidean Spaces](#1-real-inner-products--euclidean-spaces)
2. [Induced Norms, Angles & Cauchy-Schwarz](#2-induced-norms-angles--cauchy-schwarz)
3. [Orthogonality & Orthogonal Complements](#3-orthogonality--orthogonal-complements)
4. [The Gram-Schmidt Orthonormalization Algorithm](#4-the-gram-schmidt-orthonormalization-algorithm)
5. [Orthogonal Projections & Best Approximation](#5-orthogonal-projections--best-approximation)
6. [Orthogonal Matrices & Isometries](#6-orthogonal-matrices--isometries)

---

## 1. Real Inner Products & Euclidean Spaces

Let $V$ be a real vector space. A **real inner product** (prodotto scalare) is a bilinear map:

$$
\langle \cdot, \cdot \rangle : V \times V \to \mathbb{R}
$$

that satisfies three fundamental axioms for all $u, v, w \in V$ and $\alpha \in \mathbb{R}$:

1. **Symmetry:**

$$
\langle u, v \rangle = \langle v, u \rangle
$$

2. **Bilinearity (Linearity in the first argument):**

$$
\langle u + v, w \rangle = \langle u, w \rangle + \langle v, w \rangle
$$

$$
\langle \alpha u, v \rangle = \alpha \langle u, v \rangle
$$

3. **Positive Definiteness:**

$$
\langle v, v \rangle \ge 0 \quad \forall v \in V, \quad \text{and } \langle v, v \rangle = 0 \iff v = 0_V
$$

A real vector space endowed with a positive-definite inner product is called a **Euclidean Vector Space** $(V, \langle \cdot, \cdot \rangle)$.

### 1.1 Standard Euclidean Inner Product (Dot Product in $\mathbb{R}^n$)

For column vectors $x, y \in \mathbb{R}^n$:

$$
\langle x, y \rangle = x \cdot y = x^T y = \sum_{i=1}^n x_i y_i = x_1 y_1 + x_2 y_2 + \dots + x_n y_n
$$

---

## 2. Induced Norms, Angles & Cauchy-Schwarz

### 2.1 The Induced Norm (Vector Magnitude)
Every inner product induces a canonical Euclidean norm:

$$
\|v\| = \sqrt{\langle v, v \rangle}
$$

* **Non-negativity:** $\|v\| \ge 0$, and $\|v\| = 0 \iff v = 0$
* **Absolute Homogeneity:** $\|\alpha v\| = |\alpha| \, \|v\|$
* **Unit Vector (Versore):** A vector $u$ with $\|u\| = 1$. Normalization: $u = \frac{v}{\|v\|}$.

### 2.2 The Cauchy-Schwarz Inequality
For all vectors $u, v \in V$:

$$
|\langle u, v \rangle| \le \|u\| \cdot \|v\|
$$

Equality holds ($|\langle u, v \rangle| = \|u\| \cdot \|v\|$) if and only if $u$ and $v$ are linearly dependent.

### 2.3 Triangle Inequality

$$
\|u + v\| \le \|u\| + \|v\|
$$

### 2.4 Angle Between Vectors & Euclidean Distance
The angle $\theta \in [0, \pi]$ between non-zero vectors $u, v \in V$ is defined by:

$$
\cos(\theta) = \frac{\langle u, v \rangle}{\|u\| \cdot \|v\|}
$$

The Euclidean distance between two vectors is:

$$
d(u, v) = \|u - v\| = \sqrt{\langle u - v, u - v \rangle}
$$

---

## 3. Orthogonality & Orthogonal Complements

### 3.1 Orthogonality
Two vectors $u, v \in V$ are **orthogonal** (written $u \perp v$) if:

$$
\langle u, v \rangle = 0
$$

* **Pythagorean Theorem:** If $u \perp v$, then:

$$
\|u + v\|^2 = \|u\|^2 + \|v\|^2
$$

### 3.2 Orthogonal and Orthonormal Sets
A set of non-zero vectors $\{v_1, v_2, \dots, v_k\}$ is:
* **Orthogonal:** if $\langle v_i, v_j \rangle = 0$ for all $i \neq j$.
* **Orthonormal:** if it is orthogonal and every vector is normalized:

$$
\langle v_i, v_j \rangle = \delta_{ij} = \begin{cases} 1 & \text{if } i = j \\ 0 & \text{if } i \neq j \end{cases}
$$

> Every orthogonal set of non-zero vectors is **linearly independent**.

### 3.3 Orthogonal Complement
Let $W \subseteq V$ be a subspace. The **orthogonal complement** $W^\perp$ is:

$$
W^\perp = \{v \in V : \langle v, w \rangle = 0, \, \forall w \in W\}
$$

* $W^\perp$ is a vector subspace of $V$.
* $W \cap W^\perp = \{0\}$.
* **Orthogonal Direct Sum:** In finite-dimensional spaces:

$$
V = W \oplus W^\perp \implies \dim(V) = \dim(W) + \dim(W^\perp)
$$

$$
(W^\perp)^\perp = W
$$

---

## 4. The Gram-Schmidt Orthonormalization Algorithm

Given a linearly independent basis $\mathcal{B} = (v_1, v_2, \dots, v_k)$ of a subspace $W$, Gram-Schmidt constructs an **orthogonal basis** $(u_1, u_2, \dots, u_k)$:

### 4.1 Step-by-Step Construction

**Step 1:**

$$
u_1 = v_1
$$

**Step 2:**

$$
u_2 = v_2 - \frac{\langle v_2, u_1 \rangle}{\|u_1\|^2} u_1
$$

**Step 3:**

$$
u_3 = v_3 - \frac{\langle v_3, u_1 \rangle}{\|u_1\|^2} u_1 - \frac{\langle v_3, u_2 \rangle}{\|u_2\|^2} u_2
$$

**Step k (General Formula):**

$$
u_k = v_k - \sum_{j=1}^{k-1} \frac{\langle v_k, u_j \rangle}{\|u_j\|^2} u_j
$$

### 4.2 Orthonormal Normalization Step
To obtain an **orthonormal basis** $(e_1, e_2, \dots, e_k)$:

$$
e_i = \frac{u_i}{\|u_i\|} \quad (i = 1, 2, \dots, k)
$$

---

## 5. Orthogonal Projections & Best Approximation

Let $W \le V$ be a finite-dimensional subspace with an orthonormal basis $(e_1, e_2, \dots, e_k)$.

### 5.1 Orthogonal Projection Formula
The **orthogonal projection** of any vector $v \in V$ onto $W$ is:

$$
\pi_W(v) = \text{proj}_W(v) = \sum_{i=1}^k \langle v, e_i \rangle e_i
$$

If using an orthogonal (non-normalized) basis $(u_1, \dots, u_k)$:

$$
\pi_W(v) = \sum_{i=1}^k \frac{\langle v, u_i \rangle}{\|u_i\|^2} u_i
$$

### 5.2 Best Approximation Theorem
The orthogonal projection $\pi_W(v)$ is the unique vector in $W$ closest to $v$:

$$
\|v - \pi_W(v)\| < \|v - w\| \quad \forall w \in W \setminus \{\pi_W(v)\}
$$

The minimum distance from $v$ to the subspace $W$ is:

$$
\text{dist}(v, W) = \|v - \pi_W(v)\|
$$

---

## 6. Orthogonal Matrices & Isometries

A real square matrix $Q \in \mathbb{R}^{n \times n}$ is **orthogonal** if its columns form an orthonormal basis of $\mathbb{R}^n$:

$$
Q^T Q = Q Q^T = I_n \iff Q^{-1} = Q^T
$$

### 6.1 Fundamental Properties
* **Preservation of Inner Products:** $\langle Qx, Qy \rangle = \langle x, y \rangle$
* **Preservation of Norms (Isometry):** $\|Qx\| = \|x\|$
* **Preservation of Angles and Distances:** $d(Qx, Qy) = d(x, y)$
* **Determinant:** $\det(Q) = \pm 1$
  * If $\det(Q) = +1$: $Q$ represents a pure rotation (Special Orthogonal Group $SO(n)$).
  * If $\det(Q) = -1$: $Q$ represents a reflection or rotoreflection.
* **Eigenvalues:** If $\lambda \in \mathbb{C}$ is an eigenvalue of $Q$, then $|\lambda| = 1$.

---

[Back to Main README](../README.md)
