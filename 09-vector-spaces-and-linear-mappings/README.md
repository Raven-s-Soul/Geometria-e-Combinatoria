# 07-vector-spaces-and-linear-mappings: Vector Spaces, Subspaces & Linear Mappings

Axiomatic definition of real vector spaces, vector subspaces, linear independence, spanning sets, bases and dimension, Grassmann's formula, linear mappings, kernel, image, the Rank-Nullity Theorem, and change of basis.

---

## Table of Contents

1. [Vector Spaces: Axioms & Subspaces](#1-vector-spaces-axioms--subspaces)
2. [Linear Combinations, Span & Independence](#2-linear-combinations-span--independence)
3. [Bases and Dimension](#3-bases-and-dimension)
4. [Subspace Sums & Grassmann's Formula](#4-subspace-sums--grassmanns-formula)
5. [Linear Mappings: Kernel and Image](#5-linear-mappings-kernel-and-image)
6. [The Rank-Nullity (Dimension) Theorem](#6-the-rank-nullity-dimension-theorem)
7. [Associated Matrix of a Linear Map & Change of Basis](#7-associated-matrix-of-a-linear-map--change-of-basis)

---

## 1. Vector Spaces: Axioms & Subspaces

A **real vector space** is a set $V$ equipped with two operations:
* Vector addition: $+ : V \times V \to V$
* Scalar multiplication: $\cdot : \mathbb{R} \times V \to V$

satisfying the 8 standard axioms (commutativity, associativity, additive identity $0$, additive inverse, distributivity over vector/scalar additions, scalar associativity, and scalar unity $1 \cdot v = v$).

### 1.1 Vector Subspaces
A non-empty subset $W \subseteq V$ is a **vector subspace** (written $W \le V$) if and only if it is closed under linear combinations:

1. **Zero Vector:** $0_V \in W$
2. **Closure under Addition:** $\forall u, v \in W \implies u + v \in W$
3. **Closure under Scalar Multiplication:** $\forall \alpha \in \mathbb{R}, \, \forall v \in W \implies \alpha v \in W$

> **Compact Subspace Criterion:**
> $$
> \forall \alpha, \beta \in \mathbb{R}, \quad \forall u, v \in W \implies \alpha u + \beta v \in W
> $$

---

## 2. Linear Combinations, Span & Independence

Let $\{v_1, v_2, \dots, v_k\} \subset V$:

### 2.1 Linear Combinations & Linear Span
A vector $v \in V$ is a linear combination of $\{v_1, \dots, v_k\}$ if there exist scalars $\lambda_1, \dots, \lambda_k \in \mathbb{R}$ such that:

$$
v = \sum_{i=1}^k \lambda_i v_i = \lambda_1 v_1 + \lambda_2 v_2 + \dots + \lambda_k v_k
$$

The **linear span** $\text{Span}(v_1, \dots, v_k)$ is the smallest subspace of $V$ containing the vectors:

$$
\text{Span}(v_1, \dots, v_k) = \{ \sum_{i=1}^k \lambda_i v_i : \lambda_i \in \mathbb{R} \}
$$

### 2.2 Linear Independence
The vectors $\{v_1, \dots, v_k\}$ are **linearly independent** if:

$$
\sum_{i=1}^k \lambda_i v_i = 0 \implies \lambda_1 = \lambda_2 = \dots = \lambda_k = 0
$$

If there exist scalars not all zero such that $\sum \lambda_i v_i = 0$, the set is **linearly dependent** (at least one vector is a linear combination of the others).

---

## 3. Bases and Dimension

### 3.1 Basis of a Vector Space
An ordered set of vectors $\mathcal{B} = (v_1, v_2, \dots, v_n)$ is a **basis** of $V$ if:
1. $\mathcal{B}$ is **linearly independent**.
2. $\mathcal{B}$ is a **spanning set** of $V$: $\text{Span}(\mathcal{B}) = V$.

Every vector $v \in V$ can be uniquely expressed in coordinates with respect to $\mathcal{B}$:

$$
v = x_1 v_1 + x_2 v_2 + \dots + x_n v_n \implies [v]_\mathcal{B} = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix}
$$

### 3.2 Dimension
The **dimension** of a finitely generated vector space $V$, denoted by $\dim(V)$, is the number of vectors in any of its bases.

* If $\dim(V) = n$, any set of $n$ linearly independent vectors forms a basis.
* Any set of more than $n$ vectors in $V$ is necessarily linearly dependent.

---

## 4. Subspace Sums & Grassmann's Formula

Let $U$ and $W$ be two subspaces of $V$.

### 4.1 Sum and Intersection
* **Intersection:** $U \cap W$ is always a vector subspace of $V$.
* **Sum:** $U + W = \{u + w : u \in U, \, w \in W\}$ is the smallest subspace containing both $U$ and $W$.

### 4.2 Grassmann's Dimension Formula

$$
\dim(U + W) = \dim(U) + \dim(W) - \dim(U \cap W)
$$

### 4.3 Direct Sum
The sum is a **direct sum** (written $U \oplus W$) if $U \cap W = \{0\}$. In this case:

$$
\dim(U \oplus W) = \dim(U) + \dim(W)
$$

Every element $v \in U \oplus W$ decomposes uniquely as $v = u + w$ with $u \in U$ and $w \in W$.

---

## 5. Linear Mappings: Kernel and Image

Let $V$ and $W$ be real vector spaces. A function $f: V \to W$ is a **linear mapping (homomorphism)** if:

$$
f(u + v) = f(u) + f(v) \quad \forall u, v \in V
$$

$$
f(\alpha v) = \alpha f(v) \quad \forall \alpha \in \mathbb{R}, \, \forall v \in V
$$

### 5.1 Kernel (Nucleo)
The set of all vectors in $V$ mapped to the zero vector of $W$:

$$
\ker(f) = \{v \in V : f(v) = 0_W\} \le V
$$

* **Injectivity Criterion:**

$$
f \text{ is injective} \iff \ker(f) = \{0_V\} \iff \dim(\ker(f)) = 0
$$

### 5.2 Image (Immagine)
The set of all values attained by $f$ in $W$:

$$
\text{Im}(f) = \{f(v) \in W : v \in V\} \le W
$$

* **Surjectivity Criterion:**

$$
f \text{ is surjective} \iff \text{Im}(f) = W \iff \dim(\text{Im}(f)) = \dim(W)
$$

---

## 6. The Rank-Nullity (Dimension) Theorem

Let $V$ be a finite-dimensional vector space and $f: V \to W$ a linear mapping:

$$
\dim(V) = \dim(\ker(f)) + \dim(\text{Im}(f))
$$

Where $\text{rank}(f) = \dim(\text{Im}(f))$ and $\text{nullity}(f) = \dim(\ker(f))$.

### 6.1 Endomorphisms of Equal Finite Dimension ($\dim V = \dim W$)
If $\dim(V) = \dim(W) = n$, the following statements are logically equivalent:
1. $f$ is injective ($\ker(f) = \{0\}$).
2. $f$ is surjective ($\text{Im}(f) = W$).
3. $f$ is bijective (an isomorphism).

---

## 7. Associated Matrix of a Linear Map & Change of Basis

Let $\mathcal{B}_V = (v_1, \dots, v_n)$ be a basis of $V$ and $\mathcal{B}_W = (w_1, \dots, w_m)$ a basis of $W$.

### 7.1 Representation Matrix
The matrix $M = M_{\mathcal{B}_W}^{\mathcal{B}_V}(f) \in \mathbb{R}^{m \times n}$ has as its $j$-th column the coordinates of $f(v_j)$ with respect to $\mathcal{B}_W$:

$$
f(v_j) = \sum_{i=1}^m a_{ij} w_i \implies M = \begin{pmatrix} [f(v_1)]_{\mathcal{B}_W} & [f(v_2)]_{\mathcal{B}_W} & \dots & [f(v_n)]_{\mathcal{B}_W} \end{pmatrix}
$$

* **Coordinate Transformation:**

$$
[f(v)]_{\mathcal{B}_W} = M_{\mathcal{B}_W}^{\mathcal{B}_V}(f) \cdot [v]_{\mathcal{B}_V}
$$

### 7.2 Change of Basis Formula
If $P$ is the change of basis matrix from $\mathcal{B}$ to $\mathcal{B}'$ on $V$ (modal transition matrix), the matrix $A = M_\mathcal{B}^\mathcal{B}(f)$ transforms to $A' = M_{\mathcal{B}'}^{\mathcal{B}'}(f)$ via similarity:

$$
A' = P^{-1} A P
$$

---

[Back to Main README](../README.md)
