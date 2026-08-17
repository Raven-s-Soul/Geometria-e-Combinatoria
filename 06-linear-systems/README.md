# 06-linear-systems: Linear Systems of Equations

Matrix formulation of linear systems, the Rouché-Capelli compatibility theorem, Gaussian elimination, row echelon forms, parametric solution extraction, homogeneous systems, and Cramer's rule.

---

## Table of Contents

1. [Matrix Formulation of Linear Systems](#1-matrix-formulation-of-linear-systems)
2. [The Rouché-Capelli Theorem](#2-the-rouché-capelli-theorem)
3. [Homogeneous Linear Systems](#3-homogeneous-linear-systems-ax--0)
4. [Gaussian Elimination & Row Operations](#4-gaussian-elimination--row-operations)
5. [Row Echelon Form (REF) & Reduced Form (RREF)](#5-row-echelon-form-ref--reduced-form-rref)
6. [Back-Substitution & Parametric Solutions](#6-back-substitution--parametric-solutions)
7. [Cramer's Rule](#7-cramers-rule)

---

## 1. Matrix Formulation of Linear Systems

A system of $m$ linear equations in $n$ unknowns ($x_1, x_2, \dots, x_n$) is defined as:

$$
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2 \\
\quad \vdots \\
a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = b_m
\end{cases}
$$

### 1.1 Compact Matrix Form

$$
A x = b
$$

Where:
* **Coefficient Matrix:** $A \in \mathbb{R}^{m \times n}$

$$
A = \begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

* **Unknowns Vector:** $x = \begin{pmatrix} x_1 & x_2 & \dots & x_n \end{pmatrix}^T \in \mathbb{R}^n$
* **Constants Vector:** $b = \begin{pmatrix} b_1 & b_2 & \dots & b_m \end{pmatrix}^T \in \mathbb{R}^m$
* **Augmented Matrix:** $(A \mid b) \in \mathbb{R}^{m \times (n+1)}$

$$
(A \mid b) = \begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} & \bigm| & b_1 \\
a_{21} & a_{22} & \dots & a_{2n} & \bigm| & b_2 \\
\vdots & \vdots & \ddots & \vdots & \bigm| & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn} & \bigm| & b_m
\end{pmatrix}
$$

---

## 2. The Rouché-Capelli Theorem

A linear system $A x = b$ is **consistent (compatible)** if and only if the rank of the coefficient matrix equals the rank of the augmented matrix:

$$
\text{rank}(A) = \text{rank}(A \mid b) = r
$$

### 2.1 Classification of Solutions

| Condition | Number of Solutions | Geometry of Solution Set |
| :--- | :--- | :--- |
| $\text{rank}(A) < \text{rank}(A \mid b)$ | **$0$ solutions** (Inconsistent) | $\emptyset$ (No intersection) |
| $\text{rank}(A) = \text{rank}(A \mid b) = n$ | **$1$ unique solution** | Single point in $\mathbb{R}^n$ |
| $\text{rank}(A) = \text{rank}(A \mid b) = r < n$ | **$\infty^{n-r}$ solutions** | Linear affine subspace of dimension $n-r$ |

* $n$: total number of unknowns.
* $r$: common rank of $A$ and $(A \mid b)$.
* $n - r$: degrees of freedom (number of arbitrary free parameters).

---

## 3. Homogeneous Linear Systems ($Ax = 0$)

When the vector of constants is zero ($b = 0_{m \times 1}$):

$$
A x = 0
$$

### 3.1 Fundamental Properties
* **Always Consistent:** $\text{rank}(A) = \text{rank}(A \mid 0) = r$ is always satisfied.
* **Trivial Solution:** $x = (0, 0, \dots, 0)^T$ is always a valid solution.
* **Non-Trivial Solutions:** Non-zero solutions exist if and only if:

$$
\text{rank}(A) < n
$$

* **Kernel / Null Space:** The solution set $V_0 = \{x \in \mathbb{R}^n : Ax = 0\}$ forms a vector subspace of $\mathbb{R}^n$ with dimension:

$$
\dim(V_0) = n - \text{rank}(A) = n - r
$$

### 3.2 General Solution Structure for Non-Homogeneous Systems
If $x_p$ is any particular solution to $Ax = b$, the complete solution set $S$ is:

$$
S = x_p + V_0 = \{x_p + v : v \in V_0\}
$$

---

## 4. Gaussian Elimination & Row Operations

Gaussian elimination transforms $(A \mid b)$ into an equivalent, upper-triangular / stepped augmented matrix without changing the solution set.

### 4.1 Elementary Row Operations (EROs)

1. **Row Swap ($R_i \leftrightarrow R_j$):** Swap two rows.
2. **Scalar Multiplication ($R_i \leftarrow \lambda R_i$):** Multiply a row by a non-zero scalar $\lambda \neq 0$.
3. **Row Addition ($R_i \leftarrow R_i + \lambda R_j$):** Add a scalar multiple of row $j$ to row $i$.

---

## 5. Row Echelon Form (REF) & Reduced Form (RREF)

### 5.1 Row Echelon Form (REF)
A matrix is in **Row Echelon Form** if:
1. All all-zero rows are grouped at the bottom.
2. The leading coefficient (first non-zero entry, called **pivot**) of each non-zero row is strictly to the right of the pivot in the row above it.
3. All entries directly below a pivot are zero.

$$
\begin{pmatrix}
\mathbf{p_1} & * & * & * & \bigm| & * \\
0 & \mathbf{p_2} & * & * & \bigm| & * \\
0 & 0 & 0 & \mathbf{p_3} & \bigm| & * \\
0 & 0 & 0 & 0 & \bigm| & 0
\end{pmatrix}
$$

* The **rank** equals the number of non-zero rows (or pivots) in the echelon form.

### 5.2 Reduced Row Echelon Form (RREF / Gauss-Jordan)
A matrix is in **RREF** if, in addition to REF:
1. Every pivot is equal to $1$.
2. Every pivot is the *only* non-zero entry in its entire column.

---

## 6. Back-Substitution & Parametric Solutions

Once $(A \mid b)$ is reduced to REF:

### 6.1 Systematic Step-by-Step Procedure
1. **Identify Pivot Variables:** Variables corresponding to columns containing a pivot.
2. **Identify Free Variables:** Columns without pivots $\implies$ assign them as parameters ($t_1, t_2, \dots$).
3. **Back-Substitution:** Starting from the bottom non-zero row upwards, solve for each pivot variable in terms of the free variables.

### 6.2 Example ($3$ equations, $4$ unknowns)

Given the reduced echelon form:

$$
\begin{pmatrix}
1 & 2 & 0 & -1 & \bigm| & 4 \\
0 & 0 & 1 & 3  & \bigm| & 2 \\
0 & 0 & 0 & 0  & \bigm| & 0
\end{pmatrix}
$$

* Pivots are in columns 1 and 3 $\implies x_1, x_3$ are **pivot variables**.
* Columns 2 and 4 have no pivots $\implies x_2 = t_1, \, x_4 = t_2$ are **free parameters**.
* Row 2: $x_3 + 3x_4 = 2 \implies x_3 = 2 - 3t_2$
* Row 1: $x_1 + 2x_2 - x_4 = 4 \implies x_1 = 4 - 2t_1 + t_2$

**Vector Solution:**

$$
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{pmatrix} = \begin{pmatrix} 4 \\ 0 \\ 2 \\ 0 \end{pmatrix} + t_1 \begin{pmatrix} -2 \\ 1 \\ 0 \\ 0 \end{pmatrix} + t_2 \begin{pmatrix} 1 \\ 0 \\ -3 \\ 1 \end{pmatrix} \quad (t_1, t_2 \in \mathbb{R})
$$

---

## 7. Cramer's Rule 
>($n \times n$ Systems)

For a square linear system where the number of equations equals the number of unknowns ($A \in \mathbb{R}^{n \times n}$):

### 7.1 Cramer's Theorem
If $\det(A) \neq 0$, the system $Ax = b$ is non-singular and has a **unique solution** given by:

$$
x_i = \frac{\det(A_i)}{\det(A)} \quad (i = 1, 2, \dots, n)
$$

Where $A_i$ is the matrix formed by replacing column $i$ of $A$ with the constants vector $b$:

$$
A_i = \begin{pmatrix}
a_{11} & \dots & b_1 & \dots & a_{1n} \\
a_{21} & \dots & b_2 & \dots & a_{2n} \\
\vdots & \ddots & \vdots & \ddots & \vdots \\
a_{n1} & \dots & b_n & \dots & a_{nn}
\end{pmatrix}
$$

---

[Back to Main README](../README.md)
