[[Advanced algorithm and problem solving]] 
Think of a **Min-Heap** as an organized company hierarchy where:

1. **The Golden Rule (Heap Invariant):** Every boss (parent) must have a smaller number than their direct subordinates (children). The CEO (root) is always the absolute minimum number.
2. **The Shape Rule (Completeness):** The company fills desks strictly in order from left to right on each floor. No gaps allowed.

Every operation in a binary heap comes down to just two mechanical moves: **bubbling up** (promoting) or **trickling down** (demoting).

---

### Move 1: Sift-Up ("Promote the Underdog")

Used when a new number enters the heap, or when an existing number gets smaller.

* **The Problem:** A small number is sitting below a bigger parent, violating the rule.
* **The Action:** The node looks up at its parent. If the node is smaller than its parent, they swap positions. Repeat until the parent is smaller, or the node becomes the root.

#### Walkthrough: Inserting `5` into an existing min-heap

Starting tree (represented as a complete tree):

```text
        [ 10 ]
       /      \
    [ 20 ]    [ 30 ]
    /    \
  [ 40 ] [ 50 ]

```

**Step 1: Put the new value in the next available spot** (preserving the complete tree shape).
The next spot is the left child of `30`.

```text
        [ 10 ]
       /      \
    [ 20 ]    [ 30 ]
    /    \    /
  [ 40 ] [50][ 5 ]  <-- New node arrives at the bottom

```

**Step 2: Compare with parent (`30`)**

* Is $5 < 30$? Yes. **Swap them.**

```text
        [ 10 ]
       /      \
    [ 20 ]    [ 5 ]  <-- Moved up
    /    \    /
  [ 40 ] [50][ 30 ]

```

**Step 3: Compare with new parent (`10`)**

* Is $5 < 10$? Yes. **Swap them.**

```text
        [ 5 ]   <-- Reached the top!
       /     \
    [ 20 ]   [ 10 ]
    /    \   /
  [ 40 ] [50][ 30 ]

```

* Because the tree has height $\log_2 n$, the node can swap upward at most $\log_2 n$ times. Insertion is $O(\log n)$.

---

### Move 2: Sift-Down ("Demote the Unqualified")

Used when you remove the top element (`extractMin`) and need a new leader.

* **The Problem:** The root is gone. If you just pull up a child, you create a gaping hole in the tree structure and break the shape rule.
* **The Trick:**
1. Take the **very last element** in the heap (bottom-rightmost node) and place it directly into the vacant root spot. (The shape rule is now preserved).
2. The root is almost certainly way too big. Now **sift it down**: compare it with **both** of its children, find the **smaller child**, and swap with that child.
3. Repeat until the node is smaller than both of its children, or it hits the bottom (becomes a leaf).



*(Why swap with the **smaller** child? If a parent is 50, and its children are 10 and 20, swapping 50 with 10 puts 10 on top, which satisfies $10 < 20$ and $10 < 50$. If you swapped with 20, 20 would become 10's parent, breaking the rule immediately!)*

#### Walkthrough: Extracting the minimum (`5`)

Starting tree:

```text
        [ 5 ]
       /     \
    [ 20 ]   [ 10 ]
    /    \   /
  [ 40 ] [50][ 30 ]

```

**Step 1: Save the root (`5`), take the last element (`30`), and put it at the root.**

```text
        [ 30 ]  <-- Temporary root
       /      \
    [ 20 ]    [ 10 ]
    /    \
  [ 40 ] [ 50 ]

```

**Step 2: Check children of `30**`

* Children are `20` and `10`.
* The smaller child is `10`.
* Is $10 < 30$? Yes. **Swap `30` with `10`.**

```text
        [ 10 ]
       /      \
    [ 20 ]    [ 30 ]  <-- Moved down
    /    \
  [ 40 ] [ 50 ]

```

**Step 3: Check children of `30` again**

* Node `30` has no children now (it's a leaf).
* Done! The minimum (`10`) is naturally at the root, and all parent-child rules hold.

---

### How the Array Handles This Without Pointers

In code, there are no actual tree links or nodes with `left` and `right` pointers. The entire tree is just a normal flat array:

```text
Tree:
        [ 10 ]           Index:  0   1   2   3   4
       /      \          Value: [10, 20, 30, 40, 50]
    [ 20 ]    [ 30 ]
    /    \
  [ 40 ] [ 50 ]

```

Because of the complete shape, parent and children are calculated with simple arithmetic:

* If you are at index `i`:
* **Parent:** `(i - 1) // 2`
* **Left child:** `2 * i + 1`
* **Right child:** `2 * i + 2`



Let’s test index `1` (value `20`):

* Its parent is at `(1 - 1) // 2 = 0` (value `10`).
* Its left child is at `2 * 1 + 1 = 3` (value `40`).
* Its right child is at `2 * 1 + 2 = 4` (value `50`).

To swap elements during a sift-up or sift-down, you just swap two array slots: `array[i], array[parent] = array[parent], array[i]`.

---

### Quick Summary of All Main Operations

| Operation | Action | Time Complexity |
| --- | --- | --- |
| **`peek()` / `findMin()**` | Look at index `0`. No movement. | $O(1)$ |
| **`insert(val)`** | Append to end of array $\rightarrow$ **Sift-Up**. | $O(\log n)$ |
| **`extractMin()`** | Pop index `0`, move last element to index `0` $\rightarrow$ **Sift-Down**. | $O(\log n)$ |
| **`decreaseKey(i, newVal)`** | Overwrite `array[i] = newVal` $\rightarrow$ **Sift-Up** (since it got smaller). | $O(\log n)$ |