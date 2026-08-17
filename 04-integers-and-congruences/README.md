# 04-integers-and-congruences: Number Theory & Linear Congruences

Divisibility properties in $\mathbb{Z}$, the Euclidean algorithm for greatest common divisors ($\gcd$), Bézout's identity, modular arithmetic, and systematic methods for solving linear congruences.

---

## Table of Contents

1. [Divisibility & Euclidean Division](#1-divisibility--euclidean-division)
2. [Greatest Common Divisor & Euclidean Algorithm](#2-greatest-common-divisor--euclidean-algorithm)
3. [Bézout's Identity](#3-bézouts-identity)
4. [Modular Arithmetic & Congruence Relations](#4-modular-arithmetic--congruence-relations)
5. [Linear Congruences (ax = b mod m)](#5-linear-congruences-ax--b-mod-m)
6. [Modular Inverses](#6-modular-inverses)

---

## 1. Divisibility & Euclidean Division

Let $a, b \in \mathbb{Z}$. We say that $b$ divides $a$ (written $b \mid a$) if there exists an integer $q \in \mathbb{Z}$ such that:

$$a = b \cdot q$$

### 1.1 Properties of Divisibility
* If $a \mid b$ and $b \mid c \implies a \mid c$ (Transitivity)
* If $a \mid b$ and $a \mid c \implies a \mid (\alpha b + \beta c), \quad \forall \alpha, \beta \in \mathbb{Z}$ (Linear combinations)
* If $a \mid b$ and $b \mid a \implies a = \pm b$

### 1.2 Euclidean Division (Division with Remainder)
For any $a, b \in \mathbb{Z}$ with $b > 0$, there exist unique integers $q$ (quotient) and $r$ (remainder) such that:

$$a = b \cdot q + r \quad \text{with } 0 \le r < b$$

---

## 2. Greatest Common Divisor & Euclidean Algorithm

The **Greatest Common Divisor** of two integers $a, b \in \mathbb{Z}$ (not both zero), denoted by $\gcd(a, b)$ or $\text{MCD}(a, b)$, is the largest positive integer $d$ such that $d \mid a$ and $d \mid b$.

* **Coprime (Relatively Prime):** $a$ and $b$ are coprime if $\gcd(a, b) = 1$.

### 2.1 The Euclidean Algorithm
Compute successive divisions until the remainder becomes $0$:

$$\begin{aligned}
a &= b \cdot q_1 + r_1 \quad &(0 < r_1 < b) \\
b &= r_1 \cdot q_2 + r_2 \quad &(0 < r_2 < r_1) \\
r_1 &= r_2 \cdot q_3 + r_3 \quad &(0 < r_3 < r_2) \\
&\;\;\vdots \\
r_{k-2} &= r_{k-1} \cdot q_k + r_k \quad &(0 < r_k < r_{k-1}) \\
r_{k-1} &= r_k \cdot q_{k+1} + 0
\end{aligned}$$

The greatest common divisor is the **last non-zero remainder**:

$$\gcd(a, b) = r_k$$

---

## 3. Bézout's Identity

For any integers $a, b \in \mathbb{Z}$, there exist integers $x, y \in \mathbb{Z}$ such that:

$$a x + b y = \gcd(a, b)$$

* The coefficients $x$ and $y$ are called **Bézout coefficients**.
* They are determined by backtracking through the steps of the Euclidean algorithm (expressing each remainder as a linear combination of $a$ and $b$).

---

## 4. Modular Arithmetic & Congruence Relations

Let $m \in \mathbb{Z}^+$ with $m \ge 2$. Two integers $a, b \in \mathbb{Z}$ are **congruent modulo $m$** (written $a \equiv b \pmod m$) if $m$ divides their difference:

$$a \equiv b \pmod m \iff m \mid (a - b) \iff a \text{ and } b \text{ have the same remainder when divided by } m$$

### 4.1 Properties of Congruence
* **Equivalence Relation:** Reflexive, symmetric, and transitive.
* **Compatibility with Operations:**
  If $a \equiv b \pmod m$ and $c \equiv d \pmod m$, then:

$$a + c \equiv b + d \pmod m$$

$$a \cdot c \equiv b \cdot d \pmod m$$

$$a^k \equiv b^k \pmod m \quad (\forall k \in \mathbb{N})$$

---

## 5. Linear Congruences (ax = b mod m)

A linear congruence has the form:

$$a x \equiv b \pmod m$$

### 5.1 Solvability Criterion
Let $d = \gcd(a, m)$:
* The congruence is **solvable** if and only if $d \mid b$.
* If $d \mid b$, there are exactly **$d$ incongruent solutions** modulo $m$.
* If $d \nmid b$, there are **no solutions**.

### 5.2 Step-by-Step Resolution Method

1. Compute $d = \gcd(a, m)$ using the Euclidean algorithm.
2. Check if $d \mid b$. If not, stop (incompatible).
3. Divide the entire congruence by $d$:

$$a' x \equiv b' \pmod{m'} \quad \text{where } a' = \frac{a}{d}, \, b' = \frac{b}{d}, \, m' = \frac{m}{d}$$

4. Since $\gcd(a', m') = 1$, find the modular inverse $u = (a')^{-1} \pmod{m'}$ such that:

$$a' u \equiv 1 \pmod{m'}$$

5. Compute the base solution:

$$x_0 \equiv u \cdot b' \pmod{m'}$$

6. The complete set of $d$ solutions modulo $m$ is:

$$x_k = x_0 + k \cdot m' = x_0 + k \cdot \frac{m}{d} \quad (k = 0, 1, 2, \dots, d-1)$$

---

## Chinese Remainder Theorem (CRT) & Systems of Congruences

The Chinese Remainder Theorem guarantees the existence and uniqueness of solutions to systems of simultaneous linear congruences with pairwise coprime moduli.

---

### 1. Theorem Statement

Given a system of linear congruences:

$$\begin{cases}
x \equiv c_1 \pmod{m_1} \\
x \equiv c_2 \pmod{m_2} \\
\quad \vdots \\
x \equiv c_k \pmod{m_k}
\end{cases}$$

If the moduli are **pairwise coprime**, that is:

$$\gcd(m_i, m_j) = 1 \quad \forall i \neq j$$

then there exists a **unique solution modulo $M$**, where $M = \prod_{i=1}^k m_i = m_1 \cdot m_2 \cdots m_k$:

$$x \equiv x_0 \pmod M$$

---

### 2. Constructive Resolution Algorithm

1. **Pre-processing (if needed):**
   If equations are given as $a_i x \equiv b_i \pmod{m_i}$, solve and simplify each individually to the form $x \equiv c_i \pmod{m_i}$.

2. **Total Modulus ($M$):**

$$M = \prod_{i=1}^k m_i = m_1 \cdot m_2 \cdots m_k$$

3. **Partial Moduli ($M_i$):**
   For each equation $i$, calculate the product of all other moduli excluding $m_i$:

$$M_i = \frac{M}{m_i}$$

4. **Modular Inverses ($N_i$):**
   For each $i$, find the modular multiplicative inverse $N_i$ of $M_i$ modulo $m_i$ using Bézout's identity:

$$M_i \cdot N_i \equiv 1 \pmod{m_i}$$

5. **Particular Solution ($x_0$):**

$$x_0 = \sum_{i=1}^k c_i \cdot M_i \cdot N_i = c_1 M_1 N_1 + c_2 M_2 N_2 + \dots + c_k M_k N_k$$

6. **Final Modular Reduction:**
   The general solution is:

$$x \equiv x_0 \pmod M \implies x \equiv (x_0 \bmod M) \pmod M$$

---

### 3. Step-by-Step Worked Example

Solve the following system:

$$\begin{cases}
x \equiv 2 \pmod 3 \\
x \equiv 3 \pmod 5 \\
x \equiv 2 \pmod 7
\end{cases}$$

#### Step 1: Verify Coprimality and Calculate Total Modulus
* $\gcd(3, 5) = \gcd(3, 7) = \gcd(5, 7) = 1 \implies$ Moduli are pairwise coprime.
* $M = 3 \cdot 5 \cdot 7 = 105$.

#### Step 2: Compute Partial Moduli $M_i$
* $M_1 = \frac{105}{3} = 35$
* $M_2 = \frac{105}{5} = 21$
* $M_3 = \frac{105}{7} = 15$

#### Step 3: Compute Modular Inverses $N_i$
* **For $N_1$:** $35 N_1 \equiv 1 \pmod 3 \implies 2 N_1 \equiv 1 \pmod 3 \implies N_1 \equiv 2 \pmod 3$.
* **For $N_2$:** $21 N_2 \equiv 1 \pmod 5 \implies 1 N_2 \equiv 1 \pmod 5 \implies N_2 \equiv 1 \pmod 5$.
* **For $N_3$:** $15 N_3 \equiv 1 \pmod 7 \implies 1 N_3 \equiv 1 \pmod 7 \implies N_3 \equiv 1 \pmod 7$.

#### Step 4: Construct Particular Solution $x_0$

$$x_0 = (2 \cdot 35 \cdot 2) + (3 \cdot 21 \cdot 1) + (2 \cdot 15 \cdot 1) = 140 + 63 + 30 = 233$$

#### Step 5: Reduce Modulo $M$

$$233 = 2 \cdot 105 + 23 \implies x_0 \equiv 23 \pmod{105}$$

**General Solution:**

$$x \equiv 23 \pmod{105} \quad (\text{or } x = 23 + 105k, \, k \in \mathbb{Z})$$

---

### 4. Non-Coprime Moduli (Substitution Method)

If $\gcd(m_i, m_j) = d > 1$, the system is compatible if and only if:

$$c_i \equiv c_j \pmod{\gcd(m_i, m_j)}$$

If consistent, solve by **successive substitution**:
1. From the first equation, write $x = c_1 + k \cdot m_1$ with $k \in \mathbb{Z}$.
2. Substitute this expression for $x$ into the second equation to solve for $k$.
3. Update the modulus using the least common multiple $\text{lcm}(m_1, m_2)$.

---

## 6. Modular Inverses

An element $a$ has a **multiplicative inverse modulo $m$** (an integer $x$ such that $a x \equiv 1 \pmod m$) if and only if:

$$\gcd(a, m) = 1$$

* The inverse $a^{-1} \pmod m$ is unique modulo $m$ and corresponds directly to the Bézout coefficient $x$ in $a x + m y = 1$.

---

[Back to Main README](../README.md)
