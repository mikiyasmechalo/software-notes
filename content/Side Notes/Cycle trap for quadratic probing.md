[[Advanced algorithm and problem solving]]
The **cycle trap** in quadratic probing refers to a pathological failure mode where the probe sequence loops through a small subset of array indices over and over, **missing empty slots elsewhere in the table**.

When this happens, an insertion or search fails to find an available bucket, even if the table is mostly empty.

---

### The Root Cause: Number Theory & Quadratic Residues

Under the standard quadratic probing formula:

$$h(k, i) = (h'(k) + i^2) \pmod m$$

The relative offsets from the base index $h'(k)$ are simply the squares modulo $m$:

$$0^2 \pmod m, \quad 1^2 \pmod m, \quad 2^2 \pmod m, \quad 3^2 \pmod m, \quad \dots$$

In modular arithmetic, the values of $x^2 \pmod m$ are known as **quadratic residues**.

#### The Fundamental Ceiling: At Most $\lceil m / 2 \rceil$ Values

For any prime $m > 2$, every non-zero quadratic residue modulo $m$ has **exactly two square roots**:

$$x^2 \equiv (-x)^2 \pmod m$$

Because $-x \equiv m - x \pmod m$, the square of any probe index $i$ produces the exact same offset as the probe index $m - i$:

$$i^2 \equiv (m - i)^2 \pmod m$$

This symmetry causes the sequence of offsets to fold in on itself:

* Probe $1$ lands on the same offset as probe $m - 1$.
* Probe $2$ lands on the same offset as probe $m - 2$.
* Probe $i$ lands on the same offset as probe $m - i$.

Because of this mirror symmetry, pure quadratic probing ($i^2$) can generate at most:

$$\frac{m - 1}{2} + 1 = \frac{m + 1}{2}$$

distinct offsets across the entire infinite sequence. **Roughly half of the array slots are mathematically unreachable** by that probe sequence, no matter how many times it loops.

---

### A Concrete Walkthrough: Table Size $m = 11$

Suppose a table has capacity $m = 11$ (a prime number), and a key collides at base index $h'(k) = 0$.

Let's compute the sequence of probe offsets $i^2 \pmod{11}$:

| Probe ($i$) | $i^2$ | $i^2 \pmod{11}$ | Slot Visited |
| --- | --- | --- | --- |
| **0** | $0$ | $0$ | **0** |
| **1** | $1$ | $1$ | **1** |
| **2** | $4$ | $4$ | **4** |
| **3** | $9$ | $9$ | **9** |
| **4** | $16$ | $5$ | **5** |
| **5** | $25$ | $3$ | **3** |
| **6** | $36$ | $3$ (mirrors $i=5$) | **3** |
| **7** | $49$ | $5$ (mirrors $i=4$) | **5** |
| **8** | $64$ | $9$ (mirrors $i=3$) | **9** |
| **9** | $81$ | $4$ (mirrors $i=2$) | **4** |
| **10** | $100$ | $1$ (mirrors $i=1$) | **1** |
| **11** | $121$ | $0$ (mirrors $i=0$) | **0** |

#### The Resulting Cycle

The probe sequence only ever visits indices:

$$\{0, 1, 3, 4, 5, 9\}$$

That is exactly $6$ out of $11$ possible slots ($\frac{11 + 1}{2} = 6$).

The remaining slots:

$$\{2, 6, 7, 8, 10\}$$

are **invisible** to this key.

* **The Trap:** If slots $\{0, 1, 3, 4, 5, 9\}$ happen to be occupied by previously inserted keys, an insertion for this key will enter an infinite loop checking those same 6 slots forever, despite the fact that 5 slots in the table are completely empty.

---

### Non-Prime Table Sizes Make It Worse

If $m$ is not prime and arbitrary coefficients are used, the situation deteriorates further.

Consider $m = 8$ and $h(k, i) = (h'(k) + i^2) \pmod 8$:

* $i = 0 \implies 0 \pmod 8 = \mathbf{0}$
* $i = 1 \implies 1 \pmod 8 = \mathbf{1}$
* $i = 2 \implies 4 \pmod 8 = \mathbf{4}$
* $i = 3 \implies 9 \pmod 8 = \mathbf{1}$
* $i = 4 \implies 16 \pmod 8 = \mathbf{0}$

The probe sequence cycles strictly between **three** slots: $\{0, 1, 4\}$. It never checks the other 5 slots ($62.5\%$ of the table is inaccessible).

---

### How Implementations Defeat the Cycle Trap

Engineers bypass this limitation using two primary mathematical guarantees:

#### 1. The Prime $+ \; \alpha < 0.5$ Invariant

If $m$ is prime and pure quadratic probing ($i^2$) is used, the first $\lceil m / 2 \rceil$ probes are guaranteed to visit distinct slots.

* By enforcing a strict load factor threshold of **$\alpha < 0.5$**, the table guarantees that at least one of the tested slots will be empty.
* The table resizes before $\alpha$ reaches $0.5$, ensuring the cycle trap is never encountered.

#### 2. The Triangular Numbers Formulation ($m = 2^k$)

Instead of pure squares, set:

$$h(k, i) = \left(h'(k) + \frac{i^2 + i}{2}\right) \pmod m$$

Where $m$ is a power of 2 ($m = 2^k$).

Because the difference between consecutive triangular numbers increases by $1$ each step ($\Delta = i$), this formula is proven to generate a **complete permutation** of $\langle 0, 1, \dots, m-1 \rangle$. Every single slot in the table is visited before any slot is repeated, entirely eliminating the cycle trap.