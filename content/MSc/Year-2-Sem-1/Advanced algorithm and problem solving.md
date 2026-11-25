---
teacher: Dr. Melak
Split: MSc
---
# Chapter 1: Introduction to Algorithms & Problem Solving

### 1.1 Fundamentals of Problem Solving
* **Problem Definition:** The process of defining a problem, finding its root cause, identifying and prioritizing alternatives for a solution, and implementing the selected approach in an effective and timely manner.
* **Problem:** A condition, situation, or barrier to achieving a goal or activity.
* **Problem Solving:** Removing that barrier through a systematic, sequenced set of activities.
* **Open Problems:** Problems that have been formally stated but not yet solved by existing algorithms or mathematical proofs.

### 1.2 What is an Algorithm?
An **algorithm** is a well-defined computational procedure (a tool) that takes some value (or set of values) as **input** and produces some value (or set of values) as **output** after finite execution.

#### Core Characteristics: by Donald Ervin Knuth 
1. **Output:** Produces a specific output after execution.
2. **Input:** Accepts zero or more externally supplied inputs.
3. **Finiteness:** Terminates after a discrete, finite number of steps.
4. **Definiteness (Unambiguous):** Each step must be clearly defined and clear in meaning.
5. **Effectiveness:** Operations must be basic enough that they can, in principle, be executed exactly in a finite amount of time (often using paper and pencil).

### 1.3 Algorithm Analysis

#### Types of Complexity Analysis
* **Time Complexity:** The measure of execution time as a function of input size $n$.
* **Space Complexity:** The measure of memory required by the algorithm:
$$S(P) = C + S_P(I)$$
  * $C$: **Fixed part** (independent of characteristics of inputs/outputs; includes instruction space, simple variables, constants).
  * $S_P(I)$: **Variable part** (depends on the specific problem instance $I$; includes dynamic memory allocation, recursion stack space, dynamically-sized data arrays).
* **Time-Space Trade-off:** Solving a problem using less execution time by increasing space consumption, or vice-versa.

#### Analysis Paradigms
1. **A Priori Analysis (Theoretical):** 
	* Performed *before* implementation and execution.
	* Independent of hardware, operating systems, and processor speeds.
	* Assumes basic operations take constant time ($O(1)$) and expresses complexity asymptotically as a function of input size $n$.

2. **A Posteriori Analysis (Empirical / Practical):** 
	* Performed *after* writing code and running it on target hardware.
	* Measures actual wall-clock time and memory consumption in bytes/kilobytes.
	* Heavily dependent on compiler optimizations, CPU architecture, memory bandwidth, and system load.

#### Asymptotic Notations
Describes how resource consumption grows as input size $n \to \infty$:
* **Big-$O$ ($O$):** Asymptotic Upper Bound ($f(n) \le c \cdot g(n)$). Worst-case upper limit.
* **Big-$\Omega$ ($\Omega$):** Asymptotic Lower Bound ($f(n) \ge c \cdot g(n)$). Best-case lower limit.
* **Big-$\Theta$ ($\Theta$):** Asymptotically Tight Bound ($c_1 \cdot g(n) \le f(n) \le c_2 \cdot g(n)$). Average/exact growth rate.

### 1.4 Stable Marriage Problem (Gale-Shapley Algorithm)
#### The Problem
Given two sets of equal size $n$ (traditionally $M$ men and $W$ women), where each person ranks all members of the opposite sex in strict order of preference:
* **Goal:** Pair everyone together such that the matching is **stable**.
* **Instability:** A pairing is unstable if there exists a man $m$ and woman $w$ who are **not** married to each other, but prefer each other over their assigned partners (called a *blocking pair*).

#### Gale-Shapley (Propose-and-Reject) Algorithm
```text
Initialize all m ∈ M and w ∈ W as free/unmatched
While exists an unmatched man m who still has a woman w to propose to:
    w = highest-ranked woman on m's list to whom m has not yet proposed
    If w is free:
        (m, w) become engaged
    Else (w is currently engaged to m'):
        If w prefers m to m':
            (m, w) become engaged
            m' becomes free
        Else:
            m remains free (proposal rejected)
```

#### Key Guarantees
* **Termination:** Terminates in at most $n^2$ iterations (Total time complexity: $O(n^2)$).
* **Correctness & Stability:** Always produces a complete, stable matching.
* **Optimality:** Yields **proposer-optimal** matching (men obtain the best possible valid partner, while women obtain their least optimal valid partner).
	* Key word "**valid**" here:
	* It does not mean a woman ends up with her absolute bottom choice on her entire preference sheet. It means she ends up with the worst possible partner among those she could realistically be paired with in any stable matching.

# Chapter 2: Advanced Data Structures

### 2.1 Abstract Data Types (ADTs) & Basics
* **Data Structure:** A systematic format for organizing, storing, and manipulating data efficiently.
	* *Primitive:* Built-in types (`int`, `float`, `char`, `pointer`).
	* *Non-primitive:* Linear (Arrays, Linked Lists, Stacks, Queues) and Non-linear (Trees, Graphs).

* **ADT (Abstract Data Type):** Mathematical model specifying a set of data objects and the operations that can be performed on them, independent of implementation details.
	* Standard Libraries: C++ STL (`vector`, `stack`, `queue`, `priority_queue`, `map`, `set`); Java Collections Framework (`java.util.*`).


### 2.2 Tree Fundamentals (General Trees)

#### Core Concept & Terminology
A **tree** is a non-linear, hierarchical data structure consisting of nodes connected by directed or undirected edges, containing no cycles. A tree with $n$ nodes contains exactly $n - 1$ edges.

* **Root:** The topmost node with no parent.
* **Edge:** The directed or undirected connection linking a parent node to a child node.
* **Parent / Child:** A node directly above another is its parent; a node directly below is its child.
* **Siblings:** Nodes that share the exact same parent node.
* **Leaf (Terminal Node):** A node with degree 0 (no children).
* **Internal Node:** A non-leaf node with at least one child.
* **Path:** A sequence of consecutive edges connecting a sequence of nodes.
* **Degree:**
	* *Degree of a node:* The number of children that node has.
	* *Degree of a tree:* The maximum degree over all nodes in the tree.
* **Depth & Height:**
	* **Depth of a node:** The number of edges on the path from the root down to that node ($\text{Depth}(\text{root}) = 0$).
	* **Height of a node:** The length of the longest path from that node down to a leaf ($\text{Height}(\text{leaf}) = 0$).
	* **Height of a tree:** The height of the root node (maximum depth among all nodes).

#### Binary Trees vs. General Trees
* **General Tree:** Each node may have an arbitrary, unbounded number of children (often represented via *First-Child / Next-Sibling* pointer chains).
* **Binary Tree:** An ordered tree where each node has at most **two** children, designated strictly as the *left child* and *right child*.

#### Standard Tree Traversals
1. **Depth-First Search (DFS):**
	 * **Pre-order ($N \to L \to R$):** Visit root node first, then traverse left subtree, then right subtree.
	 * **In-order ($L \to N \to R$):** Traverse left subtree, visit root, traverse right subtree (yields sorted order in a BST).
	 * **Post-order ($L \to R \to N$):** Traverse left subtree, traverse right subtree, visit root (used for bottom-up cleanup / node deletion).
2. **Breadth-First Search (BFS / Level-Order):**
   * Visits nodes level by level from top to bottom, left to right (implemented using a Queue).

### 2.3 Binary Search Trees (BST)
#### Definition & Structural Invariants
* A hierarchical non-linear data structure (tree) where each node has at most two children.
* **BST Property:** For any node $x$:
$$\forall y \in \text{LeftSubtree}(x), \quad \text{key}(y) \le \text{key}(x)$$
$$\forall z \in \text{RightSubtree}(x), \quad \text{key}(z) \ge \text{key}(x)$$

#### Operations
* **Search / Insert / Delete:**
	* Traverses left if target is smaller, right if target is larger.
* **Best/Average Case Time:** $O(\log n)$ (when balanced).
* **Worst Case Time:** $O(n)$ (devolves into a degenerate linked list under sorted inputs).

### 2.4 AVL Trees (Self-Balancing BST)
#### Structural Invariant
* An AVL tree is a BST that enforces a strict height balance.
* **Balance Factor ($BF$):**   
$$BF(\text{node}) = \text{Height}(\text{LeftSubtree}) - \text{Height}(\text{RightSubtree})$$
* **Invariant:** For every node $x$, $BF(x) \in \{-1, 0, +1\}$.
* **Height:** Guarantees height $h < 1.44 \log_2(n + 2)$, ensuring worst-case lookup, insertion, and deletion in $O(\log n)$ time.

An AVL tree is:
- Balanced: $\text{BF}(N) \in \{-1, 0, 1\}$ 
- Left-Heavy: $\text{BF}(N) > 1$ 
- Right-Heavy: $\text{BF}(N) < -1$ 

#### Rotations
**Rotations** are local operations that change the structure of the tree without violating the binary search tree property: $\text{Left Child} < \text{Root} < \text{Right Child}$.

**Right Rotation** (Clockwise)Used when a node’s left child is too tall. It pulls the left child up and pushes the root down to the right.
```
        y                              x
       / \                            / \
      x   T3   -- Right Rotate(y) -> T1   y
     / \                                 / \
    T1  T2                              T2  T3
```
Pointer adjustments:
1. `x = y.lefty` 
2. `left = x.right` ($T_2$ transfers to $y$)
3. `x.right = y` 
4. Update heights of $y$, then $x$.

**Left Rotation** (Counter-Clockwise)Used when a node’s right child is too tall. It pulls the right child up and pushes the root down to the left.
```
      x                                y
     / \                              / \
    T1  y      -- Left Rotate(x) ->  x   T3
       / \                          / \
      T2  T3                       T1  T2
```
Pointer adjustments:
1. `y = x.right` 
2. `x.right = y.left` ($T_2$ transfers to $x$)
3. `y.left = x` 
4. Update heights of $x$, then $y$.

#### Rotations for Rebalancing (Upon Insertion / Deletion)
When a node $Z$ becomes unbalanced ($\text{BF}(Z) = +2$ or $-2$), the imbalance stems from one of four structural patterns.

| Case | Condition at $Z$ | Condition at Child | Required Rotation |
| --- | --- | --- | --- |
| **Left-Left (LL)** | $\text{BF}(Z) = +2$ | $\text{BF}(Z.\text{left}) \ge 0$ | Right Rotate on $Z$ |
| **Right-Right (RR)** | $\text{BF}(Z) = -2$ | $\text{BF}(Z.\text{right}) \le 0$ | Left Rotate on $Z$ |
| **Left-Right (LR)** | $\text{BF}(Z) = +2$ | $\text{BF}(Z.\text{left}) < 0$ | Left Rotate on $Z.\text{left}$, then Right Rotate on $Z$ |
| **Right-Left (RL)** | $\text{BF}(Z) = -2$ | $\text{BF}(Z.\text{right}) > 0$ | Right Rotate on $Z.\text{right}$, then Left Rotate on $Z$ |

##### 1. Left-Left (LL) Case
* **Symptom:** Insertion occurred in the left subtree of the left child of $Z$.
* **Fix:** Single **Right Rotation** at $Z$.
```text
       Z (+2)
      /
     Y (+1)         -- RightRotate(Z) ->        Y (0)
    /                                          / \
   X (0)                                     X   Z
```

##### 2. Right-Right (RR) Case
* **Symptom:** Insertion occurred in the right subtree of the right child of $Z$.
* **Fix:** Single **Left Rotation** at $Z$.
```text
   Z (-2)
    \
     Y (-1)         -- LeftRotate(Z) ->         Y (0)
      \                                        / \
       X (0)                                  Z   X
```

##### 3. Left-Right (LR) Case
* **Symptom:** Insertion occurred in the right subtree of the left child of $Z$. A single right rotation fails here because the "zigzag" shape prevents balanced redistribution.
* **Fix:**
	1. **Left Rotation** on $Y$ (transforms the subtree into an LL case).
	2. **Right Rotation** on $Z$.
```text
     Z (+2)                  Z (+2)
    /                       /
   Y (-1)   -- Left(Y) ->  X (+1)   -- Right(Z) ->     X (0)
    \                     /                           / \
     X                   Y                           Y   Z
```

##### 4. Right-Left (RL) Case
* **Symptom:** Insertion occurred in the left subtree of the right child of $Z$.
* **Fix:**
	1. **Right Rotation** on $Y$ (transforms into an RR case).
	2. **Left Rotation** on $Z$.
```text
   Z (-2)                 Z (-2)
    \                      \
     Y (+1)  -- Right(Y) -> X (-1)  -- Left(Z) ->      X (0)
    /                        \                        / \
   X                          Y                      Z   Y
```

#### Step-by-Step Rebalancing Algorithm
Whether inserting or deleting, the rebalancing procedure follows the same bottom-up path:
1. **Standard BST Operation:** Perform regular BST insertion or deletion.
2. **Backtrack up the call stack:** For each ancestor node $N$ moving back toward the root:
* Recalculate height:
$$\text{Height}(N) = 1 + \max(\text{Height}(N.\text{left}), \text{Height}(N.\text{right}))$$
* Calculate Balance Factor:
$$\text{BF}(N) = \text{Height}(N.\text{left}) - \text{Height}(N.\text{right})$$

* If $\text{BF}(N) > 1$:
* If $\text{BF}(N.\text{left}) \ge 0 \rightarrow$ **LL Case**: `RightRotate(N)` 
* If $\text{BF}(N.\text{left}) < 0 \rightarrow$ **LR Case**: `N.left = LeftRotate(N.left)`, then `RightRotate(N)` 

* If $\text{BF}(N) < -1$:
* If $\text{BF}(N.\text{right}) \le 0 \rightarrow$ **RR Case**: `LeftRotate(N)` 
* If $\text{BF}(N.\text{right}) > 0 \rightarrow$ **RL Case**: `N.right = RightRotate(N.right)`, then `LeftRotate(N)` 

#### Insertion vs. Deletion Rebalancing
* **Insertion:** 
	* Adding a node alters height along a single path.
	* At most **one rotation operation** (single or double) is required to restore the entire tree's balance. Once the lowest unbalanced ancestor is rotated, its subtree height returns to what it was before insertion, terminating further propagation.
	* **Rotations:** At most $2$ (in LR/RL double rotation).

* **Deletion:**
	* Removing a node can shorten a subtree, which may cause an ancestor to become unbalanced.
	* Rebalancing that ancestor reduces its height, which can propagate an imbalance further up to its parent.
	* Rebalancing may require up to $O(\log n)$ rotations all the way to the root.

### 2.5 Splay Trees
* A self-adjusting binary search tree created by Sleator and Tarjan. It is NOT "self-balancing".
* Does not store explicit balance factors or subtree heights.
* **Splaying Operation:** Whenever an element is accessed (Search, Insert, or Delete), it is moved to the root via a series of tree rotations.

#### The Splaying Operation
To splay a node $X$ to the root, we repeatedly apply two-step rotations until $X$ is either at the root or one step away.
Let:
- $X$ = Target node
- $P$ = Parent of $X$
- $G$ = Grandparent of $X$ (if it exists)

At each step, exactly one of three cases applies:
* **Zig Step:** Single rotation (similar to standard AVL rotation) performed when $P$ is the root.
```
    P                     X
	 / \                   / \
	X   C   -- Right -->  A   P
 / \                       / \
A   B                     B   C
```
* **Zig-Zig Step:** Performed when $X$ and $P$ are both left (or both right) children. Rotates parent about $G$ first, then $X$ about $P$.
```
          G                         P                       X
         / \                       / \                     / \
        P   D                     X   G                   A   P
       / \         -- Rotate --> / \ / \   -- Rotate -->     / \
      X   C           (G, P)    A  B C  D     (P, X)        B   G
     / \                                                       / \
    A   B                                                     C   D
> in this case AVL would've done 2 rotations around X, but in splay we rotate P around G first and then X around P. this order compresses long paths and prevents worst-case degeneration.
```
* **Zig-Zag Step:** Performed when $X$ is a right child and $P$ is a left child (or vice versa). Standard double rotation.
```
        G                           G                           X
       / \                         / \                         / \
      P   D                       X   D                       P   G
     / \           -- Rotate --> / \           -- Rotate --> / \ / \
    A   X             (P, X)    P   C             (G, X)    A  B C   D
       / \                     / \                         
      B   C                   A   B
```

#### Standard Operations
**Search**
1. Traverse down the tree using standard BST search.
2. If the key is found, **splay that node to the root**.
3. If the key is not in the tree, **splay the last non-null node visited** to the root.

**Insert** 
1. Perform standard BST insertion to place the new node $K$.
2. **Splay $K$ to the root**.

*(Alternative Split-Join method: Splay the predecessor/successor of $K$ to root, then attach $K$ directly at the root by splitting subtrees).*

**Delete** 
Deletion is typically implemented without the complex predecessor replacement logic of standard BSTs:
```
Step 1: Splay target K to root
        [ K ]
       /     \
     ( L )   ( R )

Step 2: Disconnect K, splay max(L) to root of L
     [ max(L) ]
     /        \
   (...)     null      ( R )

Step 3: Attach R as right child
        [ max(L) ]
       /          \
     (...)        ( R )
```

#### Complexity & Trade-offs
* **Worst-Case Single Operation:** $O(n)$ (can degrade temporarily into a linked list).
* **Amortized Time Complexity:** $O(\log n)$ over any sequence of $m$ operations.
* **Strength:** Exploits **temporal locality** (frequently accessed elements sit near the root, yielding extremely fast consecutive lookups).

>[!note] Amortized time
>Amortized time is the average time per operation over a long sequence of operations, specifically in algorithms where an occasional expensive step is guaranteed to be paid for by many cheap steps.

Unlike standard "average-case" analysis (which assumes random or typical inputs), amortized analysis provides a strict mathematical guarantee across the worst-case sequence of operations.
### 2.6 Hashing & Collision Resolution

#### Core Concept
Maps arbitrary keys to fixed table indices using a hash function:
$$h(k): \text{Key} \to [0, \dots, m - 1]$$
* **Lookup Time:** Ideal average performance is $O(1)$.
* **Collision:** Occurs when two distinct keys hash to the same bucket index ($h(k_1) = h(k_2)$ for $k_1 \ne k_2$).

#### Collision Resolution Strategies
##### 1. Separate Chaining (Open Hashing)
* Each bucket in the hash table points to a linked list (or dynamic array/tree) of entries mapping to that bucket.
```
Index    Bucket
 [0]  -> [Key A | Val] -> [Key B | Val] -> null
 [1]  -> null
 [2]  -> [Key C | Val] -> null
 [3]  -> [Key D | Val] -> [Key E | Val] -> [Key F | Val] -> null
```
* *Pros:* Simple deletion; table never fills up completely.
* *Cons:* Pointer memory overhead; cache performance drops.
* *Worst Case:* $O(n)$ if all elements hash to the same linked list.

##### 2. Open Addressing (Closed Hashing)
 * all entry records are stored directly inside the array itself. If a collision occurs, alternate slots are probed:
 * open addressing guarantees that every element occupies a slot within the table array: $$\text{Load Factor } \alpha = \frac{n}{m} \le 1$$
	* $n$ is the number of stored keys and $m$ is the table capacity.
* if the array is full no further elements can be inserted without resizing.

 * **Linear Probing:** simplest approach, inspects sequential adjacent slots: $$h(k, i) = (h'(k) + i) \pmod m$$
	* $k$ is the search key.
	* $i$ is the probe trial count (0 for the initial attempt).
	* $m$ is the table size.
	 * Suffers from *Primary Clustering*: Long contiguous runs of occupied slots build up over time. Any key hashing into or near the cluster extends it further, causing average search and insertion times to degrade rapidly as $\alpha \to 1$.
```text
Hash Slot:   0    1    2    3    4    5    6    7
Occupied:   [ ]  [A]  [B]  [C]  [D]  [ ]  [ ]  [ ]
                  ^--- Continuous block expands easily (Primary Cluster)
```

 * **Quadratic Probing:** the step distance grows quadratically with the probe count: $$h(k, i) = (h'(k) + c_1 i + c_2 i^2) \pmod m$$
	 * $c_1$ and $c_2$ are constant auxiliary coefficients (tuning parameters) used to shape the step sizes of the probe sequence.
	 * common simplified form is: $h(k, i) = (h'(k) + i^2) \pmod m$ 
	 * Suffers from *Secondary Clustering*: Keys that produce the identical initial hash $h'(k)$ follow the exact same probe sequence, creating milder overhead than linear probing.
	 * *Cycle Trap*: Does not automatically guarantee visiting all $m$ slots. 
		 * Theorem: If $m$ is prime and $c_1 = c_2 = \frac{1}{2}$ (or $h(k, i) = (h'(k) + i^2) \pmod m$ with $m$ prime and $\alpha < 0.5$), it is guaranteed to test at least $\lceil m/2 \rceil$ distinct slots. Once $\alpha \ge 0.5$, quadratic probing can fail to find an empty slot even if one exists.
		 * [[Cycle trap for quadratic probing]] - More on the Cycle trap

 * **Double Hashing:** Uses two independent hash functions, $h_1(k)$ and $h_2(k)$. The second function generates the step offset: $$h(k, i) = (h_1(k) + i \cdot h_2(k)) \pmod m$$
	- Elimination of Clustering: Even if two keys collide on the first hash ($h_1(k_1) = h_1(k_2)$), their probe steps ($h_2(k_1)$ vs. $h_2(k_2)$) will differ, yielding completely different search trajectories.
	- Requirements for Full Coverage: To cycle through all $m$ slots:
		1. $h_2(k)$ must never evaluate to $0$ (otherwise, step size is 0 and it enters an infinite loop).
		2. $h_2(k)$ must be relatively prime to $m$ ($\gcd(h_2(k), m) = 1$).
	- Standard implementation: Choose $m$ as a prime number, let $h_1(k) = k \pmod m$, and set $h_2(k) = 1 + (k \pmod{m - 1})$.


- **Robin Hood Hashing** (Modern Optimization)
	- a variation of linear or quadratic probing designed to minimize variance in probe lengths.
	
	* **Principle:** "Take from the rich, give to the poor."
	* **Mechanism:** Every entry tracks its **Distance to Initial Bucket (DIB)** how many steps it has moved from its initial hash.
	* During insertion, if the incoming element has traveled *further* from its home bucket than the element currently sitting in that slot ($\text{DIB}_{\text{new}} > \text{DIB}_{\text{existing}}$), the existing element is evicted.
	* The incoming element takes the slot, and the evicted element continues probing down the line. 
	* **Advantage:** Eliminates worst-case variance. All elements end up close to their mean probe distance. Lookups for missing keys terminate much earlier because a search can stop as soon as the scanned slot's DIB is smaller than the search key's current probe distance.


**The Deletion Problem: Tombstones** 
A naive deletion cannot simply set an array slot to `NULL`/empty. Doing so breaks the probe path for subsequent keys that collided and were placed further down the sequence.

```text
Insert A (hashes to 2) -> Slot 2
Insert B (hashes to 2) -> Slot 3 (via collision)

If A is deleted by setting Slot 2 to EMPTY:
Search for B:
- Hash B -> 2
- Slot 2 is EMPTY -> Lookup aborts with "Not Found" (False Negative)
```

**The Fix: Lazy Deletion (Tombstones)** 
To prevent premature termination:
1. Mark the slot with a special sentinel value: **`DELETED`** (or a "tombstone").
2. **Search Operations:** Treat `DELETED` as an occupied slot and continue probing.
3. **Insert Operations:** Treat `DELETED` as an empty slot and reclaim it to store new data (while continuing to probe during that insert to ensure the key is not already present further down the line).
4. **Cleanup:** When the ratio of tombstones becomes too high, perform a full rehash to clear dead slots and compact the table.
##### Probe Count Growth Under Open Addressing

As $\alpha$ exceeds $0.7$, performance degrades sharply:
* At $\alpha = 0.5$: Unsuccessful search takes $\approx \frac{1}{1 - 0.5} = 2$ probes.
* At $\alpha = 0.8$: Unsuccessful search takes $\approx \frac{1}{1 - 0.8} = 5$ probes.
* At $\alpha = 0.9$: Unsuccessful search takes $\approx \frac{1}{1 - 0.9} = 10$ probes.
* At $\alpha \to 1.0$: Approaches $O(n)$ linear scan time.

For this reason, production hash tables using open addressing (such as Python's `dict` or C++ `flat_hash_map`) typically trigger dynamic resizing when $\alpha$ reaches **$0.66$ to $0.75$**.

### 2.7 Priority Queues (ADT)
#### Conceptual Overview
A **Priority Queue** is an Abstract Data Type that generalizes the FIFO Queue. Instead of serving elements by chronological arrival order, each element is associated with a priority key:
* **Min-Priority Queue:** Lowest numerical key holds the highest priority (e.g., shortest-path distances in Dijkstra's, simulation event times).
* **Max-Priority Queue:** Highest numerical key holds the highest priority (e.g., CPU task scheduling by importance, OS interrupt handling).

#### Standard ADT Interface
* `insert(x, key)` (or `push`): Inserts element $x$ with given **priority key**.
* `findMin()` (or `peek`): Inspects the element with the highest priority without removing it.
* `deleteMin()` (or `extractMin` / `pop`): Removes and returns the element with the highest priority.
* `decreaseKey(handle, newKey)`: Reduces the *priority key* of an element already residing in the priority queue (vital for Prim's and Dijkstra's graph algorithms).
* `merge(PQ1, PQ2)`: Combines two priority queues into a single valid priority queue.

#### Primitive Implementations Comparison
* **Unsorted Array / Linked List:** 
	* `insert`: $O(1)$ (append to end).
	* `findMin` / `deleteMin`: $O(n)$ (requires scanning every element).
* **Sorted Array / Linked List:** 
	* `findMin` / `deleteMin`: $O(1)$ (located at head/end).
	* `insert`: $O(n)$ (requires shifting elements or linear scan to preserve order).
* **Balanced BST (e.g., AVL):** 
	* `insert` / `deleteMin`: $O(\log n)$.
	* *Drawback:* Overhead of pointer manipulation and full ordering when only partial ordering is needed.

### 2.8 Heaps (Concrete Implementations of Priority Queues)
A **Heap** is a tree-based data structure satisfying the **Heap-Order Property**:
* **Min-Heap Property:** $\text{key}(\text{parent}) \le \text{key}(\text{child})$. Root is always the minimum element.
* **Max-Heap Property:** $\text{key}(\text{parent}) \ge \text{key}(\text{child})$. Root is always the maximum element.
It is the primary underlying engine for priority queues and the Heapsort algorithm.

**Core Heap Operations** 
**A. Sift-Up (Percolate Up / Bubble Up)** - Used during *insertions* and `decreaseKey` operations when a value becomes larger than its parent (in a max-heap).
1. Compare node at index $i$ with its parent $\lfloor \frac{i - 1}{2} \rfloor$.
2. If `heap[i] > heap[parent]`, swap them.
3. Update $i \leftarrow \text{parent}$ and repeat until the root is reached or the heap property holds.

- Time Complexity: $O(\log n)$

**B. Sift-Down (Percolate Down / `Heapify`)** — Used during `extractMax`/`extractMin` operations when a node at index $i$ is smaller than one or both of its children.
1. Identify the largest among: node $i$, its left child $2i + 1$, and its right child $2i + 2$.
2. If the largest is not node $i$, swap node $i$ with the largest child.
3. Recurse or loop down to the swapped child's index until the node is larger than both children or becomes a leaf.

- Time Complexity: $O(\log n)$
[[Simpler explanations for Heap operations]] 

#### 1. Binary Heap
A complete binary tree stored implicitly in a contiguous array without explicit pointers:
* **Structural Rule:** Completely filled on all levels, except the last level.
	* If the last level is not complete, all nodes are packed as far left as possible.
	* Because of this property, a heap of $n$ elements always has a minimal, predictable height of: $h = \lfloor \log_2 n \rfloor$ 
* **Array Indexing (1-based):** 
	* Root at index `1` , 0 if 0 based
	* Left child of $i$: `2i` , `2i+1` if 0 based
	* Right child of $i$: `2i + 1` , `2i+2` if 0 based
	* Parent of $i$: $\lfloor i / 2 \rfloor$ , `(i-1)/2` if 0 based
* **Core Operations:** 
	* `insert`: Place at index $n+1$ (end) and perform `sift-up` / `bubble-up` ($O(\log n)$ worst case, $O(1)$ average).
	* `deleteMin/Max`: Move the last element (index $n$) to the root and perform `sift-down` / `percolate-down` with smaller child ($O(\log n)$).
	* `buildHeap` (`Heapify`): Bottom-up sift-downs on non-leaf nodes ($\lfloor n/2 \rfloor \dots 1$) executes in linear $O(n)$ time.
	* Why non leaf nodes only? Because leaf nodes by themselves are already heaps ($A[\lfloor n/2\rfloor +1 ... n]$)
* **Limitation:** Merging two binary heaps requires re-building from scratch ($O(n)$ time).

#### 2. $d$-Ary Heap ($d$-Heap)
Generalizes the binary heap so that every internal node has up to $d$ children ($d \ge 2$):
* **Height:** Compresses tree height to $\lfloor \log_d n\rfloor$.
	* For $d = 4$, the tree is roughly half as deep as a binary heap ($d = 2$).
* Array Indexing (0-based):
	- For a node at index $i$:
		- Parent: $\lfloor \frac{i - 1}{d} \rfloor$
		- $k$-th Child (for $k \in [1, d]$): $d \cdot i + k$ (d children of node i are stored in contingious memory)
* **Operations:** 
	* `insert` / `decreaseKey`: Sifts upward (compare to parent and swap) $\to O(\log_d n)$. (Faster than binary heap, by just being a shorter tree).
	* `deleteMin`: Sifts downward, but must compare all $d$ children per level to find the smallest $\to O(d \log_d n)$. (Slower than binary heap).

**Practical Trade-Offs**:
* **Memory & Caching:** For large heaps stored in memory hierarchies or on disk (external memory), a 4-heap or 8-heap often outperforms a binary heap because shallower trees reduce cache misses and page faults.
* **Algorithm Tuning:** In algorithms where insertions and `decreaseKey` operations heavily outnumber `deleteMin` calls (such as Dijkstra’s algorithm on dense graphs with $\vert{}E\vert{} \gg \vert{}V\vert{}$), choosing $d \approx \vert{}E\vert{} / \vert{}V\vert{}$ optimizes the total asymptotic running time.

#### 3. Leftist Heap
A pointer-based binary tree explicitly designed for fast merges in $O(\log n)$ time by intentionally creating an unbalanced left-heavy shape.
* **Null Path Length (NPL / $s(x)$) (Rank):** The length of the shortest path from node $x$ to an external empty node (null/leaf node). $$s(x) = 1 + \min(s(x.\text{left}), \, s(x.\text{right})), \quad s(\text{NULL}) = -1$$
* **Leftist Invariant:** For every node $x$:  $$\text{NPL}(x.\text{left}) \ge \text{NPL}(x.\text{right})$$
* **Key Consequence:** The right spine (root $\to$ rightmost leaf) is always the shortest path to a leaf node, bounded strictly by $\lfloor \log_2(n+1) \rfloor = O(\log n)$.

**Fundamental Operation: Recursive Merge** 
All primary leftist heap operations reduce to a single core subroutine: `merge(H1, H2)`.
```c
Algorithm Merge(H1, H2):
If H1 is NULL, return H2; if H2 is NULL, return H1.
If key(H1) > key(H2), swap(H1, H2).  // Ensure H1 has smaller root
H1.right = Merge(H1.right, H2).      // Recursively merge into the right subtree
If NPL(H1.left) < NPL(H1.right):     // Check leftist property
       swap(H1.left, H1.right)          // Restore leftist property
H1.npl = 1 + NPL(H1.right)           // Update rank
Return H1
```

* **`insert(x)`:** Simply create a single-node leftist tree $H_{new}$ containing $x$, and run `merge(H, H_{new})` in $O(\log n)$ time.
* **`deleteMin()`:** Remove the root node, and execute `merge(root.left, root.right)` in $O(\log n)$ time.

#### 4. Skew Heap
The self-adjusting, amortized counterpart to the Leftist Heap (analogous to Splay Trees vs. AVL Trees):
* **Structure:** Binary tree satisfying heap order, but stores **no NPL ranks** and enforces no structural invariants.
* **Operation:** Merges recursively like a leftist heap, but **unconditionally swaps the left and right subtrees** of every visited node along the merge path.
* **Complexity:** A single worst-case merge may take $O(n)$, but over an arbitrary sequence of operations, it achieves an **amortized time of $O(\log n)$**.

## Quick Reference Summary Table

| Data Structure / ADT         | `findMin` / Search          | Insert                      | DeleteMin / Delete          | Merge                   |
| :--------------------------- | :-------------------------- | :-------------------------- | :-------------------------- | :---------------------- |
| **Unsorted Array (PQ)**      | $O(n)$                      | $O(1)$                      | $O(n)$                      | $O(1)$                  |
| **Sorted Array (PQ)**        | $O(1)$                      | $O(n)$                      | $O(1)$                      | $O(n)$                  |
| **Binary Search Tree**       | $O(n)$ [$O(\log n)$ avg]    | $O(n)$                      | $O(n)$                      | $O(n)$                  |
| **AVL Tree**                 | $O(\log n)$                 | $O(\log n)$                 | $O(\log n)$                 | $O(n)$                  |
| **Splay Tree**               | $O(n)$ [$O(\log n)$ amort.] | $O(n)$ [$O(\log n)$ amort.] | $O(n)$ [$O(\log n)$ amort.] | $O(n)$                  |
| **Hash Table**               | $O(1)$ avg / $O(n)$ worst   | $O(1)$ avg / $O(n)$ worst   | $O(1)$ avg / $O(n)$ worst   | $O(n)$                  |
| **Binary Heap (Min)**        | $O(1)$                      | $O(\log n)$ [$O(1)$ avg]    | $O(\log n)$                 | $O(n)$                  |
| **$d$-Ary Heap**             | $O(1)$                      | $O(\log_d n)$               | $O(d \log_d n)$             | $O(n)$                  |
| **Leftist Heap**             | $O(1)$                      | $O(\log n)$                 | $O(\log n)$                 | $O(\log n)$             |
| **Skew Heap**                | $O(1)$                      | $O(\log n)$ (amort.)        | $O(\log n)$ (amort.)        | $O(\log n)$ (amort.)    |
| **Binary Search Tree (BST)** | $O(n)$                      | $O(n)$                      | $O(n)$                      | $O(\log n)$             |
| **AVL Tree**                 | $O(\log n)$                 | $O(\log n)$                 | $O(\log n)$                 | $O(\log n)$             |
| **Splay Tree**               | $O(n)$                      | $O(n)$                      | $O(n)$                      | $O(\log n)$ (amortized) |
| **Hash Table**               | $O(n)$                      | $O(n)$                      | $O(n)$                      | $O(1)$                  |
| **Binary Heap**              | $O(n)$                      | $O(\log n)$                 | $O(\log n)$                 | $O(1)$ (`FindMin`)      |
| **Leftist / Skew Heap**      | $O(n)$                      | $O(\log n)$                 | $O(\log n)$                 | $O(\log n)$ (`Merge`)   |
| **Gale-Shapley (Matching)**  | N/A                         | N/A                         | N/A                         | $O(n^2)$ total runtime  |


# CH 3: Sorting Algorithms
## Insertion Sort
- Takes array A[1..n] containing a sequence of length n to be sorted
- Sorts the array in place.
	- Numbers are re-arranged inside A (in place) with at most a constant number of them stored Outside, O(1) extra space.

```
Pseudocode
INSERTION-SORT (A, n) ⊳ A[1 . . n] 
	for j ← 2 to n 
		do key ← A[ j ] 
			i ← j – 1 
			while i > 0 and A[ i ] > key 
				do A[i+1] ← A[ i] 
					i ← i – 1 
			A[i+1] = key
```

#### CORRECTNESS 
**CORRECTNESS OF INSERTION SORT** 
**Loop invariant for Insertion sort**: At the start of each iteration, the subarray `A[1..j-1]` contains the elements originally in `A[1..j-1]` but in sorted (increasing) order.

**Loop Invariant** = a property that stays true before/after every iteration of a loop. To prove an algorithm correct, you show three things about the invariant:
1. **Initialization**: It holds before the first iteration (j = 2, so `A[1..1]` is trivially sorted, one element).
2. **Maintenance**: If it holds at the start of an iteration, it still holds at the end. Insertion sort takes `A[j]` and shifts elements in `A[1..j-1]` right until it finds the correct spot, then inserts, so `A[1..j]` ends sorted. Then `j` increments, restoring the invariant form `A[1..j-1]`.
3. **Termination**: When the loop ends (j = n+1), the invariant says `A[1..n]` is sorted, which is exactly the desired result.

**Key idea**: The invariant is chosen so that, at termination, it *implies* the interesting property (the whole array sorted). The three proof steps are just the standard way to establish that the invariant holds throughout.

#### RUNNING TIME
The running time of insertion sort depends on the input.
Major Simplifying Convention: Parameterize the running time by the size of the input, since short sequences are easier to sort than long ones.
- `TA(n)` = time of A when run with inputs of length n.
	 - n: Number of bits required to encode input
- Ignore machine-dependent constants 
- Look at growth of T(n) as n → ∞, since for small inputs the algorithm is fast anyway.

*Kinds of Analysis* 
1. **Worst case** - T(n) = maximum time of the algorithm on any input of size n. Upper bounds.
2. **Average case** - T(n) = expected time of algorithm over all inputs of size n. **Needs assumption** of statistical distribution of real inputs.
3. **Best case** - T(n) = best possible time over any input of size n.
	- may be useful when proving negative results.

**Running time of Insertion sort**
**Setup:** For each line, `COST` = cost per execution, `TIMES` = how many times it runs. Total cost = COST × TIMES, summed.

**Line-by-line:**

| Line                     | Cost | Times   | Why                                                              |
| ------------------------ | ---- | ------- | ---------------------------------------------------------------- |
| `for j ← 2 to n`         | c₁   | n       | Loop header runs n times (n−1 successful + 1 final failing test) |
| `key ← A[j]`             | c₂   | n−1     | Once per iteration (j=2..n)                                      |
| `i ← j−1`                | c₃   | n−1     | Once per iteration                                               |
| `while i>0 and A[i]>key` | c₄   | Σ tⱼ    | Each iteration j does tⱼ tests; tⱼ depends on input              |
| `A[i+1] ← A[i]`          | c₅   | Σ(tⱼ−1) | Runs one fewer time than the while test (last test fails)        |
| `i ← i−1`                | c₆   | Σ(tⱼ−1) | Same count as the shift                                          |
| `A[i+1] = key`           | c₇   | n−1     | Once per iteration                                               |

$$T(n) = c_1 n + c_2(n-1) + c_3(n-1) + c_4\sum_{j=2}^{n} t_j + c_5\sum_{j=2}^{n}(t_j-1) + c_6\sum_{j=2}^{n}(t_j-1) + c_7(n-1)$$
where $t_j$ is the number of `while` loop tests performed during iteration $j$. 
The running time depends on the values of $t_j$ . This vary according to the input.

*Insertion sort Analysis* 
- **Best case** (already sorted): $tⱼ = 1$ for all $j → T(n) = Θ(n)$.
- **Worst case** (reverse sorted): $tⱼ = j → T(n) = Θ(n²)$.
- **Average case** (All permutations equally likely) $T(n)=Θ(n²)$ 

## Divide and Conquer Algorithms
**Divide and Conquer** 
- Divide into simpler/smaller sub-problems 
- Solve (conquer) sub-problems recursively 
- Combine results of sub-problems

### Exponentiation by Squaring
Computing $a^n$ naively (multiply a, n−1 times) costs Θ(n). Divide and conquer: split the exponent.
- $a^n = (a^{n/2})^2$ if n even
- $a^n = a \cdot (a^{(n-1)/2})^2$ if n odd
Recurse on half the exponent, square the result. Recurrence: $T(n) = T(n/2) + \Theta(1) \Rightarrow T(n) = \Theta(\log n)$. Huge speedup for large n.

**Example: compute 2¹⁰ by squaring**
Naive: 2×2×2×2×2×2×2×2×2×2 = 9 multiplications.
By squaring (divide & conquer):
- 2¹⁰ = (2⁵)²
- 2⁵ = 2 × (2²)² = 2 × 4² = 2 × 16 = 32
- 2¹⁰ = 32² = 1024

Only ~4 multiplications instead of 9. For $2^{1000}$, naive = 999 multiplications; squaring ≈ $10 (\log_2  1000)$.

### Multiplying Large Numbers
Naive multiplication of two n-digit numbers: Θ(n²). Divide and conquer reduces this.

**Karatsuba Algorithm**
Split each number into high/low halves: $x = x_1 \cdot 10^{n/2} + x_0$, $y = y_1 \cdot 10^{n/2} + y_0$.

Naive: 4 multiplications of half-size numbers → $T(n) = 4T(n/2) + \Theta(n) \Rightarrow \Theta(n^2)$ (no improvement).

Karatsuba's trick: compute only 3 products:
- $z_0 = x_0 \cdot y_0$
- $z_2 = x_1 \cdot y_1$
- $z_1 = (x_0+x_1)(y_0+y_1) - z_0 - z_2$

Then $xy = z_2 \cdot 10^n + z_1 \cdot 10^{n/2} + z_0$. Recurrence: $T(n) = 3T(n/2) + \Theta(n) \Rightarrow T(n) = \Theta(n^{\log_2 3}) \approx \Theta(n^{1.585})$.

**Approaching the perfect algorithm**
- **Toom-Cook**: generalizes Karatsuba; splits into more parts, more products → exponent approaches 1 (e.g., Toom-3: 5 multiplications → $Θ(n^{1.465})$).
- **FFT-based (Schönhage-Strassen)**: uses Fast Fourier Transform → $Θ(n \log n \log \log n$).
- **Harvey-Hoeven (2019)**: Θ(n log n) - currently the best known bound, essentially optimal since output has n digits.

### Merge Sort
- **Divide**: split array into two halves.
- **Conquer**: recursively sort each half.
- **Combine**: merge the two sorted halves into one sorted array.

**Pseudocode**:
```
MERGE-SORT(A, p, r):
  if p < r:
    q = floor((p + r) / 2)
    MERGE-SORT(A, p, q)      // left half
    MERGE-SORT(A, q+1, r)    // right half
    MERGE(A, p, q, r)        // combine

MERGE(A, p, q, r):
  n1 = q - p + 1;  n2 = r - q
  L = A[p..q];  R = A[q+1..r]   // copies (with sentinel ∞)
  i = j = 1;  k = p
  while i <= n1 and j <= n2:
    if L[i] <= R[j]: A[k] = L[i]; i++
    else:            A[k] = R[j]; j++
    k++
  copy remaining L[i..] or R[j..] into A[k..]
```

**Merge procedure**: compare front elements of both halves, copy the smaller to output, advance that pointer; repeat until one half empty, then copy the rest. Sentinel values (∞) avoid boundary checks.

**Complexity**:
- Recurrence: T(n) = 2T(n/2) + Θ(n) (two subproblems + linear merge).
- By Master Theorem (case 2): T(n) = Θ(n log n) — **all cases** (best/average/worst ).
- Extra space: Θ(n) for temporary arrays during merge.
- Comparisons: ~ n log₂ n in worst case.

**Properties**:
- **Stable**: equal elements keep original order (because `<=` picks left first).
- Not in-place (needs auxiliary arrays).
- Good for linked lists (no random access needed) and external sorting (disk-based).

**Recursion tree** 
$T(n) = 2T(n/2) + cn$, where c > 0 is constant.
```
Level 0:  [cn]                          cost = c·n
          /   \
Level 1: [cn/2] [cn/2]                   cost = c·(n/2)+c·(n/2) = c·n
         / \   / \
Level 2: [cn/4]×4                       cost = 4·c·(n/4) = c·n
         ...
Level k: 2^k subproblems of size n/2^k  cost = 2^k · c · (n/2^k) = c·n
```

- Every level costs exactly c·n (the constants cancel).
- Number of levels = log₂ n + 1 (halving until size 1).
- Total = c·n·(log₂ n + 1) = Θ(n log n).

**Example** (full trace): 
```
[38, 27, 43, 3, 9, 82, 10]
- Split → [38,27,43,3] | [9,82,10]
- → [38,27] | [43,3]  and  [9,82] | [10]
- → [38]|[27], [43]|[3], [9]|[82], [10]
- Merge up: [27,38], [3,43], [9,82], [10]
- → [3,27,38,43], [9,10,82]
- → [3,9,10,27,38,43,82]
```

CONCLUSIONS
- O(n log n) grows more slowly than O($n^2$). 
- Therefore, merge sort asymptotically beats insertion sort in the worst case. 
- In practice, merge sort beats insertion sort for n > 30 or so.

### Master Theorem //not covered in class
For recurrences of the form $T(n) = aT(n/b) + f(n)$ where $a \ge 1$, $b > 1$, and $f(n)$ asymptotically positive:
- **Case 1**: If $f(n) = O(n^{\log_b a - \epsilon})$ for some $\epsilon > 0$, then $T(n) = \Theta(n^{\log_b a})$.
- **Case 2**: If $f(n) = \Theta(n^{\log_b a})$, then $T(n) = \Theta(n^{\log_b a} \log n)$.
- **Case 3**: If $f(n) = \Omega(n^{\log_b a + \epsilon})$ for some $\epsilon > 0$, and $af(n/b) \le cf(n)$ for some c < 1 and large n (regularity), then $T(n) = \Theta(f(n))$.

**Example (Merge Sort)**: T(n) = 2T(n/2) + Θ(n). Here a=2, b=2, so log_b a = 1. f(n) = Θ(n) = Θ(n^1) → Case 2 → Θ(n log n).


### Quick Sort
(randomized quick sort) - choose the pivot randomly

- **Divide**: pick a pivot; partition array into elements ≤ pivot and ≥ pivot.
- **Conquer**: recursively sort the two partitions.
- **Combine**: nothing — partitioning is in-place, so array is sorted in place.

**Partition**: rearrange so all elements ≤ pivot come before pivot, and ≥ after; returns pivot's final index. O(n) per call.

**Complexity**:
- Worst case (bad pivot, e.g., already sorted with last-element pivot): Θ(n²).
- Best/average (balanced partitions): Θ(n log n).
- Randomized: expected Θ(n log n) for any input (random pivot makes worst case astronomically unlikely).
- Space: Θ(log n) stack (in-place sorting, no extra arrays).

**Properties**:
- **Not stable**: equal elements may change relative order (partitioning swaps them across the pivot).
- **In-place**: sorts within the original array; only Θ(log n) extra stack space for recursion (no auxiliary arrays like merge sort's Θ(n)).
- **Cache-friendly**: accesses memory sequentially during partitioning → good CPU cache utilization.
- **Fastest in practice**: low constant factors and in-place nature usually make it beat merge sort and heapsort on real hardware, despite same Θ(n log n) average.

**Example**: `[3, 7, 8, 5, 2, 1, 9, 5, 4]`, pivot = 4
- Partition → `[3, 2, 1]` `| 4 |` `[7, 8, 5, 9, 5]` 
- Recurse on both sides → sorted.

## Non-Comparison and Special Sort Algorithms

**Non-comparison sorts** do not compare elements against each other; instead they exploit the structure/representation of keys (e.g., integer ranges, digit positions). This lets them beat the Ω(n log n) lower bound that applies to all comparison-based sorts.

Examples:
- **Counting Sort**: counts occurrences of each value; O(n + k) where k is the key range.
- **Radix Sort**: sorts digit by digit (least significant first) using a stable sub-sort (usually counting sort); O(d(n + k)) where d = number of digits.
- **Bucket Sort**: distributes elements into buckets, sorts each bucket, concatenates; O(n) expected if input uniformly distributed.

Trade-off: require integer/radix keys and extra space; not general-purpose like comparison sorts.

### Shell Sort
NOT NON-Comparison, it is a special sorting algorithm

A generalization of insertion sort that allows swapping elements far apart, then progressively reduces the gap.

- Start with a large gap g (e.g., n/2), perform g-insertion sorts (each subsequence of elements g apart is insertion-sorted).
- Reduce g and repeat, until g = 1, the **final pass is ordinary insertion sort**. By then the array is nearly sorted, so insertion sort runs near its best case Θ(n).
- Early passes move elements close to their final position; later (smaller-gap) passes fix local disorder.

**Increment (gap) sequences** — the choice determines complexity:
- **Shell's original**: n/2, n/4, …, 1 → Θ(n²) worst case (same as insertion sort).
- **Knuth**: 1, 4, 13, 40, … (3k+1) → Θ(n^{3/2}).
- **Sedgewick**: 1, 5, 19, 41, 109, … → Θ(n^{4/3} log n) worst case.
- **Ciura**: empirically tuned (1, 4, 10, 23, 57, 132, 301, 701, 1750, …) → best practical performance.

**Complexity**: no single bound — ranges from Θ(n²) (Shell's gaps) to ~Θ(n^{4/3}) (Sedgewick). Never proven to reach Θ(n log n); the optimal gap sequence is still an open problem.

**Comparison to other sorts**:
- vs. Insertion sort: same final pass, but far-apart swaps first → much faster on medium arrays; still O(n²) worst case with poor gaps.
- vs. Merge/Quick sort: slower asymptotically (no Θ(n log n) guarantee) and not stable, but in-place with no extra memory and very low overhead → often beats O(n log n) sorts for small/medium n and nearly-sorted data.
- vs. Heap sort: similar in-place, no extra memory; Shell sort usually faster in practice due to better cache behavior, but heap sort has guaranteed Θ(n log n).

**Properties**: in-place; not stable (gaps break equal-element order); no extra memory; simple to implement. Best for small-to-medium arrays or as a subroutine.

### Heapsort
Heapsort combines the better attributes of Merge sort ($O(n\log n)$) and Insertion sort (in place sorting).
Heapsort also introduces another algorithm design technique: using a data structure, a *heap* to manage information.
A **heap** data structure is an array object that we can view as a nearly complete binary tree.
- The tree is completely filled on all levels except possibly the lowest, which is filled from the left up to a point. 
- given the index i of a node, we can easily compute the indices of its parent, left child, and right child: (1 indexed)
	- $PARENT(i)$ = $\lfloor i/ 2 \rfloor$ 
	- $LEFT(i)$ = $2i$ 
	- $RIGHT(i)$ = $2i + 1$ 

- There are two kinds of binary heaps: max-heaps and min-heaps.

##### Maintaining the Heap property 
- We call the procedure MAX-HEAPIFY (for a max heap), that has inputs an array A and an index i into the array.
-  AX - H EAPIFY assumes that the binary trees rooted at L EFT(i) and R IGHT(i) are max-heaps, but that `A[i]` might be smaller than its children, violating the heap property.
- M AX-H EAPIFY lets the value at `A[i]` "float down" in the max-heap so that the subtree rooted at index i obeys the max-heap property.

```
MAX-HEAPIFY(A, i) // A.heap-size is the size of the heap in a potentially larger array
	l = LEFT(i)
	r = RIGHT(i)
	if l <= A.heap-size and A[l] > A[i]
		largest = l
	else largest = i
	if r <=A.heap-size and A[r] > A[largest]
		largest = r
	if largest != i
		exchange A[i] with A[largest]
		MAX-HEAPIFY(A, largest)
```

The running time for MAX-HEAPIFY recurrence is `T(n) <= T(2n/3)+O(1)`, and by masters theorem $T(n)=O(\log n)$. or we can say the running time for a node of height $h$ as $O(h)$.

##### Building a Heap
We can use the procedure `MAX-HEAPIFY` in a bottom-up manner to convert an array $A[1...n]$ , where $n = A.length$, into a max-heap. 
- The elements in the subarray $A[(\lfloor n/2 \rfloor +1)...n]$ are all leaves of the tree, and so each is  1-element heap to begin with. (no need to call MAX-HEAPIFY on them).
```
BUILD-MAX-HEAP(A)
	A.heap-size = A.length
	for i = ⌊A.length/2⌋ downto 1
		MAX-HEAPIFY(A,i)
```

We can compute a simple upper bound on the running time of BUILD-MAX-HEAP as follows. Each call to MAX-HEAPIFY costs $O(\log n)$ time, and BUILD-MAX-HEAP makes $O(n)$ such calls. Thus, the running time is $O(n \log n)$. This upper bound, though correct, is not asymptotically tight.

To get a tighter bound, account for the fact that MAX-HEAPIFY's cost depends on the height of the node it is called on, not the full height of the heap. A node at height $h$ costs $O(h)$ (the call can sift down at most $h$ levels). At height $h$ there are at most $\lceil n/2^{h+1}\rceil$ nodes. So the total cost is

$$
\sum_{h=0}^{\lfloor \log_2 n \rfloor} \left\lceil \frac{n}{2^{h+1}} \right\rceil O(h)
= O\!\left(n \sum_{h=0}^{\lfloor \log_2 n \rfloor} \frac{h}{2^{h+1}}\right).
$$

The infinite series $\sum_{h=0}^{\infty} h/2^{h+1}$ converges to a constant: using $\sum_{h=0}^{\infty} h x^h = x/(1-x)^2$ with $x=1/2$, we get $\sum h/2^h = (1/2)/(1/2)^2 = 2$, so $\sum h/2^{h+1} = 1$. Hence the sum is bounded by a constant, and the running time is
$$O(n).$$
Hence, we can build a max-heap from an unordered array in linear time.


##### Heapsort Algorithm
Starts by using BUILD-MAX-HEAP to build a max-heap on the array $A[1...n]$, where $n=A.length$.
- since the max element is at the root `A[1]` we can put it into its correct final position by exchanging it with `A[n]`.
	- then we discard node n from the heap, by simply decrementing `A.heap-size`, we observe that the children of the root remain max-heaps, but the the new root element might violate the max-heap property.
	- All we need to do is call `MAX-HEAPIFY(A, 1)`.
	- The heapsort algorithm then repeats this process for the max-heap of size $n-1$, down to a heap size of 2.

```
HEAPSORT(A)
	BUILD-MAX-HEAP(A)
	for i = A.length downto 2
		exchange A[1] with A[i]
		A.heap-size = A.heap-size 1
		MAX-HEAPIFY(A, 1)
```

The HEAPSORT procedure takes time $O(n \log n)$, since the call to BUILD-MAX-HEAP takes time $O(n)$ and each of the $n-1$ calls to MAX-HEAPIFY takes time $O(\log n)$.
$$\text{Total} = O(n) + (n-1) \cdot O(\log n) = O(n) + O(n \log n) = O(n \log n)$$

### Bucket Sort
Stands on an assumption
> It assumes that the input is generated by a random process that distributes elements uniformly and independently over the interval \[0, 1).

It has an average case running time of $O(n)$.

- Bucket sort divides the interval $[0, 1)$ into n equal-sized subintervals, or buckets, and then distributes the n input numbers into the buckets. 
- Since the inputs are uniformly and independently distributed over $[0, 1)$, we do not expect many numbers to fall into each bucket. 
- To produce the output, we simply sort the numbers in each bucket and then go through the buckets in order, listing the elements in each.

Our code for bucket sort assumes that the input is an $n$-element array $A$ and that each element $A[i]$ in the array satisfies $0 \le A[i] < 1$. The code requires an auxiliary array $B[0..n-1]$ of linked lists (buckets) and assumes that there is a mechanism for maintaining such lists.

```text
BUCKET-SORT(A)
	let B[0..n-1] be a new array
	n = A.length
	for i = 0 to n-1
	    make B[i] an empty list
	for i = 1 to n
	    insert A[i] into list B[⌊n · A[i]⌋]
	for i = 0 to n-1
	    sort list B[i] with insertion sort
	concatenate the lists B[0], B[1], ..., B[n-1] together in order
```

To see that this algorithm works, consider two elements $A[i]$ and $A[j]$. Assume without loss of generality that `A[i] <= A[j]`. Since `⌊n A[i]⌋ <= ⌊n A[j]⌋`, either element $A[i]$ goes into the same bucket as $A[j]$ or it goes into a bucket with a lower index. If $A[i]$ and $A[j]$ go into the same bucket, then the for loop of lines 8–9 puts them into the proper order. If $A[i]$ and $A[j]$ go into different buckets, then line 10 puts them into the proper order. Therefore, bucket sort works correctly.

To analyze the running time, observe that all lines except line 8 take $O(n)$ time in the worst case. We need to analyze the total time taken by the $n$ calls to insertion sort in line 8.

**The math (may not be necessary to know)** 
Let $n_i$ be the number of elements that fall into bucket $B[i]$. Insertion sort on bucket $B[i]$ takes $O(n_i^2)$ time in the worst case. Since the input is uniformly distributed, the expected value of $n_i^2$ is
$$E[n_i^2] = \sum_{k=0}^{n} \Pr[n_i = k]\, k^2 = 2 - \frac{1}{n}.$$
- $Pr[𝑛_𝑖 =𝑘]$ stands for probability, specifically, the probability that bucket $𝐵[𝑖]$ contains exactly 𝑘 elements.
- So the sum computes the expected value $𝐸[𝑛^2_𝑖]$ by weighting each possible value $𝑘^2$ by the probability that $𝑛_𝑖 =𝑘$.


Thus the expected total time for all the insertion sorts is
$$\sum_{i=0}^{n-1} O(E[n_i^2]) = n \cdot O\!\left(2 - \frac{1}{n}\right) = O(n).$$

We conclude that the average-case running time for bucket sort is
$$O(n) + n \cdot O\!\left(2 - \frac{1}{n}\right) = O(n).$$

> [!note] Advanced note
> Even if the input is not drawn from a uniform distribution, bucket sort may still run in linear time. As long as the input has the property that the sum of the squares of the bucket sizes is linear in the total number of elements.

### External Sorting
Every sorting algorithm we have studied assumes something it never states: that the whole array fits in memory and any element can be reached instantly. 
- What if that is not true? The comparison counts stop mattering, because the cost is no longer comparisons at all; it is trips to storage.

External sorting is the family of techniques for this case, and in practice it means one algorithm: external merge sort. 

RAM - random access on RAM costs 100ns but 100micro s (1000x) on SSD, and 10ms on HDD.
- So the quantity to minimize is no longer operations but I/O, and specifically random I/O.

On storage: sequential access is dramatically faster than random access. 
- Quick Sort's partition walks two indices toward each other across the whole range — fine in cache, but on a file it means constant seeking. 
- Merge Sort reads its inputs strictly front to back and writes its output front to back. Everything it does is sequential.

External merge sort has exactly two phases. 

A four-tape setup (a "2-way, 2-phase merge sort") alternates data back and forth between the $A$ pair and the $B$ pair until all data ends up sorted on a single tape.

**Phase 1: Run Generation (Pass 0)** (Sorting phase)
The original unsorted data starts on external storage (or $T_{a1}$). The goal of Pass 0 is to read chunks that fit in RAM, sort them, and distribute them evenly across the output tapes.

1. **Read & Sort:** A block of records that fits in memory is loaded and sorted internally.
2. **Alternate Distribution:**
	* The first sorted run is written to tape $T_{b1}$.
	* The second sorted run is written to tape $T_{b2}$.
	* The third sorted run is written to $T_{b1}$.
	* The fourth sorted run is written to $T_{b2}$, and so on.

3. **Outcome:** By the end of Pass 0, all records are organized into sorted runs of size 1 block, split evenly between $T_{b1}$ and $T_{b2}$.

**Phase 2: The Merging Passes (Pass 1, Pass 2, ...)** 
From this point on, the roles of the tapes alternate every pass. One pair acts as the **inputs**, and the other pair acts as the **outputs**.

*Pass 1: Merging from $B$ to $A$*  
* **Input Tapes:** $T_{b1}$ and $T_{b2}$ (both rewound to the beginning).
* **Output Tapes:** $T_{a1}$ and $T_{a2}$ (cleared and ready to receive data).

1. Take the first run from $T_{b1}$ and the first run from $T_{b2}$.
2. Compare their elements in memory and write the merged, sorted run (now size 2) to **$T_{a1}$**.
3. Take the second run from $T_{b1}$ and the second run from $T_{b2}$.
4. Merge them and write this run to **$T_{a2}$**.
5. Repeat this process, alternating the merged runs between $T_{a1}$ and $T_{a2}$ until all runs on $T_{b1}$ and $T_{b2}$ are consumed.

*Pass 2: Merging from $A$ back to $B$*

* **Input Tapes:** $T_{a1}$ and $T_{a2}$ (rewound).
* **Output Tapes:** $T_{b1}$ and $T_{b2}$ (rewound).

1. Take the first run from $T_{a1}$ and the first run from $T_{a2}$.
2. Merge them into a run of size 4 and write it to **$T_{b1}$**.
3. Take the second run from $T_{a1}$ and the second run from $T_{a2}$.
4. Merge them into a run of size 4 and write it to **$T_{b2}$**.
5. Continue alternating between $T_{b1}$ and $T_{b2}$.

*Subsequent Passes* 
The algorithm repeats this ping-pong process between the pairs:
* **$B \rightarrow A$**, then **$A \rightarrow B$**, and so forth.
* With each pass, the number of runs is halved, and the run length doubles.
* The process terminates when a pass produces exactly **one single run**, which contains the entire sorted dataset.

**Cost Analysis of 2-Way Tape Sort** 
For a dataset of $N$ blocks:
* **Pass 0:** Generates $N$ initial runs split across the tapes.
* **Number of Merge Passes:** $\lceil \log_2 N \rceil$ 
* **Total Passes:** $1 + \lceil \log_2 N \rceil$ 
* **Total I/O:** Every record is read once and written once per pass, resulting in $2N \cdot (1 + \lceil \log_2 N \rceil)$ operations.

**Generalizing to $K$-Way Sorting** 
The 2-way model uses 2 input streams and 2 output streams (4 devices in total).
In a **$K$-way tape sort**, you expand this system to use $2K$ tapes:
* $K$ input tapes ($T_{a1}, T_{a2}, \dots, T_{aK}$)
* $K$ output tapes ($T_{b1}, T_{b2}, \dots, T_{bK}$)

Instead of pairing up just 2 runs at a time, each step reads the front of $K$ runs simultaneously (one from each active input tape), compares them in memory, and streams the merged result to one of the output tapes. Once that run is finished, it writes the next merged run to the next output tape.

Because each pass reduces the number of runs by a factor of $K$ instead of 2, the total merge passes drop to $\lceil \log_K N \rceil$, drastically reducing the amount of data shuttling between the tapes.

**Example** 
Assume we want to sort **8 numbers**, and our RAM can only hold and sort **2 numbers at a time** (block size = 2).
**Initial raw data:** `[34, 12, 89, 5, 67, 23, 78, 45]`

**Pass 0: Run Generation (Write to $T_{b1}, T_{b2}$)** 
Read 2 numbers at a time into RAM, sort them, and distribute the runs:
1. Read `[34, 12]` $\rightarrow$ sort `[12, 34]` $\rightarrow$ write to **$T_{b1}$**
2. Read `[89, 5]` $\rightarrow$ sort `[5, 89]` $\rightarrow$ write to **$T_{b2}$**
3. Read `[67, 23]` $\rightarrow$ sort `[23, 67]` $\rightarrow$ write to **$T_{b1}$**
4. Read `[78, 45]` $\rightarrow$ sort `[45, 78]` $\rightarrow$ write to **$T_{b2}$**

**Tape State:** 
* **$T_{b1}$:** `[12, 34]`, `[23, 67]` *(two runs of size 2)*
* **$T_{b2}$:** `[5, 89]`, `[45, 78]` *(two runs of size 2)*
* **$T_{a1}, T_{a2}$:** *(empty)* 

Pass 1: Merge $B \rightarrow A$ (Write to $T_{a1}, T_{a2}$)
Merge pairs of runs from $T_{b1}$ and $T_{b2}$, alternating output:
1. Merge 1st run of $T_{b1}$ `[12, 34]` and 1st run of $T_{b2}$ `[5, 89]`:
	* Result: `[5, 12, 34, 89]` $\rightarrow$ write to **$T_{a1}$**

2. Merge 2nd run of $T_{b1}$ `[23, 67]` and 2nd run of $T_{b2}$ `[45, 78]`:
	* Result: `[23, 45, 67, 78]` $\rightarrow$ write to **$T_{a2}$**

**Tape State:** 
* **$T_{a1}$:** `[5, 12, 34, 89]` *(one run of size 4)*
* **$T_{a2}$:** `[23, 45, 67, 78]` *(one run of size 4)*
* **$T_{b1}, T_{b2}$:** *(empty)*

Pass 2: Merge $A \rightarrow B$ (Write to $T_{b1}$)
Merge the remaining runs from $T_{a1}$ and $T_{a2}$:
1. Merge `[5, 12, 34, 89]` and `[23, 45, 67, 78]`:
* Result: `[5, 12, 23, 34, 45, 67, 78, 89]` $\rightarrow$ write to **$T_{b1}$**

**Final State:**
* **$T_{b1}$:** `[5, 12, 23, 34, 45, 67, 78, 89]` *(one single sorted run — complete)* 


# CH 4: Graph Algorithms
Graph basics
Topological sort
ADTs

## Elementary Graph Algorithms
### Representations of graphs
A **graph** is a non-linear data structure used to represent relationships and connections between pairs of objects. Formally, a graph $G$ is defined as an ordered pair $G = (V, E)$, where **$V$** is a set of vertices (nodes) and **$E$** is a set of edges (links or arcs connecting pairs of vertices).

$G = (V, E)$ 
- V - vertices
- E - edges

Degree of a Vertex:
- In an undirected graph: The number of edges incident to the vertex.
- In a directed graph: Split into In-degree (number of incoming edges) and Out-degree (number of outgoing edges).

**Path**: A sequence of alternating vertices and edges connecting a source vertex to a destination vertex.
**Cycle**: A closed path where the starting and ending vertex are the same, with no other vertices repeated.

**Common Types of Graphs** 
* **Undirected vs. Directed (Digraph):**
	* *Undirected:* Edges are bidirectional; $(u, v)$ is identical to $(v, u)$ (e.g., two-way streets, mutual friends).
	* *Directed:* Edges have a specific direction from a source to a target; $(u, v) \ne (v, u)$ (e.g., Twitter followers, web hyperlinks).

* **Weighted vs. Unweighted:**
	* *Weighted:* Each edge carries a numerical cost, weight, or distance (e.g., road lengths, transit costs).
	* *Unweighted:* All edges are considered equal in cost.

* **Connected vs. Disconnected:** A graph is connected if there is at least one path between every pair of vertices; otherwise, it is disconnected.
* **Cyclic vs. Acyclic (DAG):** A Directed Acyclic Graph (DAG) contains directed edges and no cycles, widely used to model dependencies, build pipelines, and task schedules.

**Standard Representations** 
1. **Adjacency Matrix:**
	* A 2D array of size $\vert{}V\vert{} \times \vert{}V\vert{}$, where entry `matrix[i][j]` indicates whether an edge exists between vertex $i$ and vertex $j$ (or stores the edge weight).
	* **Space:** $O(V^2)$
	* **Lookup:** $O(1)$ to check if an edge exists.
	* **Best for:** Dense graphs where $\vert{}E\vert{} \approx \vert{}V\vert{}^2$.

2. **Adjacency List:**
	* An array or hash map of $\vert{}V\vert{}$ lists, where entry `list[i]` contains all neighbor vertices adjacent to vertex $i$.
	* **Space:** $O(V + E)$
	* **Lookup:** $O(\text{degree}(i))$ to check if an edge exists.
	* **Best for:** Sparse graphs where $\vert{}E\vert{} \ll \vert{}V\vert{}^2$ (most real-world scenarios).

**Fundamental Traversal Techniques** 
* **Breadth-First Search (BFS):** Explores vertices level-by-level using a **Queue** (FIFO). Ideal for finding the shortest path in unweighted graphs.
* **Depth-First Search (DFS):** Explores as deep as possible along each branch before backtracking, implemented via a **Stack** (or recursion). Ideal for cycle detection, topological sorting, and finding connected components.


### Topological sort
A topological sort of a DAG $G =(V, E)$ is a linear ordering of all its vertices such that if G contains an edge $(u,v)$ then $u$ appears before $v$ in the ordering. 
- We can view a topological sort of a graph as an ordering of its vertices along a horizontal line so that all directed edges go from left to right. 
- If a graph contains even a single cycle, a valid topological ordering is impossible because mutual dependencies cannot be linearized.
- A DAG can have multiple valid topological orderings.

TOPOLOGICAL -S ORT(G)
1. call DFS(G) to compute ﬁnishing times $v.f$ for each vertex $v$.
2. as each vertex is ﬁnished, insert it onto the front of a linked list
3. `return` the linked list of vertices

We can perform a topological sort in time $O(V+E)$, since depth-first search takes ‚$O(V+E)$ time and it takes $O(1)$ time to insert each of the $|V|$ vertices onto the front of the linked list.

**Topological Sort** is a linear ordering of all vertices in a **Directed Acyclic Graph (DAG)** such that for every directed edge $(u, v)$, vertex $u$ appears before vertex $v$ in the sequence.

If a graph contains even a single cycle, a valid topological ordering is impossible because mutual dependencies cannot be linearized. A DAG can have multiple valid topological orderings.

**Core Applications** 
Topological sorting models scenarios governed by prerequisite or dependency constraints:
* **Task and Build Scheduling:** Compiling code modules with dependencies (e.g., `make`, Webpack).
* **Course Prerequisite Planning:** Determining which academic classes to take first.
* **Data Pipelines & CI/CD:** Ensuring upstream data transforms finish before downstream analytics run.
* **Deadlock & Cycle Detection:** Verifying that resource allocation chains contain no loops.

#### Standard Algorithms
Both standard approaches run in **$O(V + E)$** time and **$O(V)$** auxiliary space:
##### 1. Kahn’s Algorithm (In-Degree / BFS Approach)
Operates by iteratively stripping away nodes that have zero incoming dependencies.
1. **Compute In-Degrees:** Calculate the in-degree (number of incoming edges) for every vertex.
2. **Initialize Queue:** Enqueue all vertices with an in-degree of $0$.
3. **Process Vertices:**
	* Dequeue a node $u$ and append it to the topological order list.
	* For each outgoing edge $(u, v)$, decrement the in-degree of neighbor $v$.
	* If the in-degree of $v$ drops to $0$, add $v$ to the queue.
4. **Cycle Detection Check:** If the final topological list contains fewer than $\vert{}V\vert{}$ vertices, the graph contains a cycle.

##### 2. DFS Post-Order Approach
Leverages standard depth-first traversal and the property of completion order.
1. Maintain a visited tracker (often with three states: *unvisited*, *visiting/in-progress*, and *visited* to detect back-edges/cycles).
2. For each unvisited vertex, run DFS recursively until a node with no unvisited outgoing edges is reached.
3. Once all descendants of a node $u$ have finished processing, push $u$ onto a **Stack** (or prepend it to the ordering).
4. After traversing all nodes, popping all elements off the stack produces the valid topological order.