---
title: Formal Language and Automata Theory
---
# CH-1: INTRO TO THEORY OF COMPUTATION
### Functions and Relations
**Relations**
Let A and B be the sets. A relation $R$ from A to B is a subset of $A\times B$.
If $(  a, b ) \in R$ , we say $a$ has a relation with $b$, denoted as $aRb$. Or not ($aR'b$)

*Properties of Relations* - A relation R in S is, -
1. **Reflexive** if $xRx$ for every $x$ in $S$.
2. **Symmetric** if for x, y in S, $yRx$, whenever $xRy$.
3. **Transitive** if for x, y and z in S. $xRz$ whenever $xRy$ and $yRz$.
- A relation R in a set S is called an *equivalence* relation if it is reflexive, symmetric and transitive. indicated by $(\equiv)$.


**Functions**
Let A and B be sets. A function f from A to B is an assignment of exactly one element of B(*range*) to each element of A(*domain*). We write $f(a)=b$ if b is the unique element of B assigned by the function $f$ to the element a of A. If f is a function from A to B, we write $f : A→B$.
If the domain of f is all of A, we say that f is a *total function* on A; otherwise, f is said to be a *partial function*.

*Definition* 1: $f: S_1→S_2$ is said to be one-to-one function (**injection**), if different elements in $S_1$ have different images. i.e., $f(x_l) ≠ f(x_2)$ when $x_l ≠ x_2$
*Definition* 2: $f: S_1→S_2$ is onto (**surjective**), if every element y in $S_2$ is the image of some element x in $S_1$. (range is fully mapped)
*Definition* 3: $f: S_1→S_2$ is said to be a one-to-one correspondence (**bijection**), if f is both one-to-one and onto. (no duplicate elements and fully mapped)

Math functions are like pure functions in programming, only one output possible for a given input. but multiple inputs can give the same outputs.

### Graphs and Trees 
**Graph** 
A graph is a construct consisting of two finite sets, the set $V = \{υ_1, υ_2,…, υ_n\}$ of vertices and the set $E = \{e_1, e_2,…, e_m\}$ of edges. Edges are pairs of vertices $(v_i, v_j)$.
A sequence of edges $(v_i , v_j ), (v_j , v_k ),…, (v_m, v_n )$ is said to be a **walk** from $υ_i$ to $υ_n$. The length of a walk = |edges|.
A walk in which *no edge* is repeated is said to be a **path**; a path is *simple* if no *vertex* is repeated.
A walk from $υ_i$ to itself with no repeated edges is called a **cycle** with **base** $υ_i$.
An edge from a vertex to itself is called a **loop**.

**Tree** 
A **tree** is a directed(edges have directions) graph that has no cycles, and that has one distinct vertex, called the **root**, such that there is exactly one path from the root to every other vertex.
**Leaves** - vertices without outgoing edges (no children).
The **level** associated with each vertex is the number of edges in the path from the root to the vertex. at root level=0 (no edges).
The **height** of the tree is the length of the longest path from the *root node* to *a leaf node*.
At times, we want to associate an ordering with the nodes at each level; in such cases we talk about **ordered trees**.

### Introduction to Informal Proofs 
**Deduction Proof** 
It consists of a sequence of statements whose truth leads us from some initial statement, called the *hypothesis/ given statements*, to a *conclusion*, statements.
Each step must be followed by some accepted logical principle from given facts or previous statements, or combination.
The *hypothesis* may be true or false, typically depending on values of its parameters.

The theorem that is proved when we go from hypothesis *H* to a conclusion *C* is the statement “*if H then C.*” We say that C is the deducted from H.

**Contradiction Proof** 
Another way of to prove a statement of the form ”*if H then C*” is to prove the statement “*H and not C implies falsehood*”.
That is, start by assuming both the hypothesis H and the negation of the conclusion C. Complete the proof by showing that something known to be false follows logically from H not C.
e.g. *Theorem*: Let S be a finite subset of some infinite set U. Let T be the complement of S with respect to U, Then T is infinite.

**Inductive Proof** 
It is a technique by which the truth of a number of statements can be inferred from the truth of a few specific instances. It is like recursion in programing given some thing make everything, (:
Suppose we have a sequence of statements $P1 , P2 ,…$ we want to prove to be true. Furthermore, suppose also that the following holds: 
1. For some k ≥ 1, we know that $P1 , P2 ,…, Pk$ are true. 
2. The problem is such that for any $n ≥ k$, the truths of $P_1 , P_2 ,…, P_n$ imply the truth of $P_n+1$.
We can then use induction to show that every statement in this sequence is true. 
In a proof by induction, we argue as follows: From Condition 1 we know that the first k statements are true. Then Condition 2 tells us that $P_k+1$ also must be true. But now that we know that the first $k + 1$ statements are true, we can apply Condition 2 again to claim that $P_k+2$ must be true, and so on.
The starting statements $P_1 , P_2 ,…P_k$ are called the **basis of the induction**. The step connecting $Pn$ with $Pn+1$ is called the **inductive step**. The inductive step is generally made easier by the **inductive assumption** that $P_1 , P_2 ,…, P_n$ are true, then argue that the truth of these statements guarantees the truth of $P_n + 1$.

*Example*: A binary tree is a tree in which no parent can have more than two children. Prove that a binary tree of height $n$ has at most $2^n$ leaves.

**Proof**: If we denote the maximum number of leaves of a binary tree of height $n$ by $l (n)$, then we want to show that $l (n) ≤ 2^n$.
**Basis**: Clearly $l (0) = 1 = 2^0$ since a tree of height 0 can have no nodes other than the root, that is, it has at most one leaf. 
**Inductive Assumption**: $l(i) ≤ 2^i , for i=0,1,...,n$ 
**Inductive Step**: To get a binary tree of height $n + 1$ from one of height n, we can create, at most, two leaves in place of each previous one. Therefore, $l(n+1)=2l(n)$
Now Using the inductive assumption we get: $l(n+1)≤2×2^n=2^{n+1}$
Thus if our claim is true for n, it must also be true for n+1. Since n can be any number, the statement must be true for all n.

### Languages & Grammars
**Languages** 
*Alphabet* - a finite, nonempty set (∑) of symbols.
*Strings* - are finite sequences of symbols from the alphabet.
- Length of a string w, denoted by |w|.
*Language* - the set of strings.
*Empty string* ($\lambda$) - $|\lambda=0|$.  $\lambda w = w\lambda = w$ for all $w$. a string with no symbols at all.

If $w$ is a string, then $w^n$ stands for the string obtained by repeating $w$, $n$ times. 
As a special case, we define $w^0=\lambda$, for all $w$.
If ∑ is an alphabet, then we use ∑* to denote the set of strings obtained by concatenating zero or more symbols from ∑. 
The set ∑* always contains λ. if we don't want λ we say $∑^+=∑^*-\{λ\}$.
- unlike $∑$,  $∑^*$ and $∑^+$ are always infinite since there is no limit on the length of the strings in these sets.
A **language** is defined very generally as a subset of ∑*. 
Any subset L of Σ* is a language over Σ.
The complement of a language is defined with respect to ∑*. $(𝐿'= ∑^*- L)$

$L^n$ - $L$ concatenated to itself n times. $L^0$ = {$\lambda$} and $L^1= L$ 
Star closure => $L^* = L^0 \cup L^1 \cup L^2 ...$ 
Positive closure => $L^+=L^1 \cup L^2 ...$ 

The reverse of a language is the set of all string reversals, that is, L
$R=\{w^R: w∈ L\}$.
e.g. If $L=\{a^nb^n:n≥0\}$ then the reverse of language $L$ is $L^R=\{b^na^n:n≥0\}$ 
The concatenation of two languages L1 and L2 is the set of all strings obtained by
concatenating any element of L1 with any element of L2; specifically,
$$L_1L_2 = \{xy :x∈L_1,y∈L_2\}$$


### Grammars
A mechanism to describe languages.
It is defined as a quadruple:
		$G=(V, T, S, P)$ 
	V - finite set of objects called **variables**.
	T - finite set of objects called **terminal symbols**.
	S $\in$ V - is a special symbol called the **start variable**.
	P - is a finite set of **productions**.
It is assumed sets V and T are nonempty and disjoint.
The production rules specify how the grammar transforms one string to another. they define a language associated with the grammar.
We will assume that all production rules are of the form: $x → y$, where $x \in (V\cup T)^+$  and $y\in(V\cup T)^*$. 
The productions are applied in the f/f manner: Given the string w of the form -  $w=vxu,$ we say the production $x→y$ is applicable to this string and we may use it to replace x with y, thereby obtaining a new string, $z=uyv$. Written as $w⇒z$ .
we say that w drives z or z is derived from w. 

A production can be used whenever it is applicable, and it can be applied as often as desired. If $w_1⇒w_2⇒ ... ⇒ w_n,$ we say that $w_1$ derives $w_2$ and we write $w_1 \overset * ⇒ w_n$. the star * on top of arrow indicates an unspecified number of steps can be taken to derive $w_n$ form $w_1$.

By applying the production rules in a different order, a given grammar can normally generate many strings. The set of all such terminal strings is the language defined or generated by the grammar.

Let G = (V, T, S, P) be a grammar. Then the set
$$L(G)=\{w\in T^*: S\overset*⇒w \}$$
is the **language generated by G**.
If w ∈ L (G), then the sequence
$$S⇒w_1⇒w_2⇒...⇒w_n⇒w$$
is a derivation of the sentence w. The strings $S, w_1 , w_2 ,…, w_n$ , which contain variables as well as terminals, are called *sentential forms* of the derivation.

Ex: $G = (\{S\},~ \{a,b\}, ~S,~ P)$ with P given by $S→aSb$, $S→\lambda$.
Then $S⇒aSb⇒aaSbb⇒aabb$ , so we can write $S\overset*⇒aabb$ .
The language of G is $L(G)=\{a^nb^n:n≥0\}$. we say G can derive strings of the form $a^nb^n$.

Ex:2 find G that generates $L(G)=\{a^nb^{n+1}:n≥0\}$, 1 extra b is needed. this can be done with the production $S→Ab$, with other productions chosen so that A can derive $a^nb^{n}$, 
$G = (\{S, A\}, \{a,b\},S,P)$ with P:
$$S→Ab,~~A→aAb, ~~A→\lambda $$

We say that two grammars G1 and G2 are equivalent if they generate the same language, that is, if $L(G_1)=L(G_2)$ . 

##### Types of Grammars
There are d/t categories of grammar, for now let's see the 2: both context free
- Linear Grammar
- Nonlinear Grammar

**Linear Grammars** - have at most one variable at the right side of the production.  ^linear-g
- as Left-linear and Right linear as children.
**Nonlinear grammars** - are grammars that have more than one variable at the right
side of the production. 
Example of linear grammar: $G=(\{S\},\{a,b\},S,P)$ where P is given by
$S→aSb$ 
$S→λ$ 
Example of nonlinear grammar $G=(\{S\},\{a,b\},S,P)$ where P is given by
$S→SS$ 
$S→λ$ 
$S→aSb$ 

##### Regular Grammars
Right-Linear and Left-Linear Grammars
**Definition**: A grammar $G =(V, T, S, P)$ is said to be right-linear if all productions are of the form
$A → xB$,
$A → x$,  where $A, B ∈ V$, and $x∈ T^*$.
**Definition**: A grammar is said to be left-linear if all productions are of the form
A → Bx,  or
A → x.

A **regular grammar** is one that is either right-linear or left-linear. Note that in a regular grammar, at most one variable appears on the right side of any production. Furthermore, that variable must consistently be either the rightmost or leftmost symbol of the right side of any production


##### Context Free Grammars
The productions in a regular grammar are restricted in two ways: The left side must be a single variable, while the right side has a special form. To create grammars that are more powerful, we must relax some of these restrictions. 
By retaining the restriction on the left side, but permitting anything on the right, we get context-free grammars.
**Definition**: A grammar G = (V, T, S, P) is said to be context-free if all productions in P have the form 
$A → x$, where $A ∈ V$ and $x ∈ (V∪T)^*$.
A language L is said to be context-free if and only if there is a context free grammar G such that $L= L (G)$.


### Automata
Formal language is an abstract of programming language, and automaton is an abstract model of a digital computer. 
therefore has features of a digital computer:
- a mechanism for reading **Input**. w/c is assumed to be a read-only string of a given alphabet. written to file, w/c is divided to cells each holding 1 symbol.
- can produce **output** of some form. may have a temporary storage with unlimited cells. w/c the automation can read and modify.
- a **control unit**, w/c can be in any one of a finite number of internal states, w/c can change state in some defined manner.
An automaton is assumed to operate in a discrete timeframe. At any given time, the control unit is in some internal state, and the input mechanism is scanning a particular symbol on the input file.

The internal state of the control unit at the next time step is determined by the `transition/ next-state` **function**.
This **transition function** gives the next state in terms of the current state, the current input symbol, and the information currently in the temporary storage.
- during transition an output may be produced or the info in temp storage may be changed.
The term **configuration** will be used to refer to a particular state of the control unit, input file, and temporary storage.
The transition of the automaton from one configuration to the next will be called a **move**.

##### TYPES OF AUTOMATA
Automata are distinguished by the temporary memory 
- **Finite Automata**: no temporary memory 
- **Pushdown Automata**: stack
- **Turing Machines**: random access memory

Power of Automata: Finite < Pushdown < Turing

# CH 2: Finite Automata and Regular Languages

## Finite Automata
Models for computers with an extremely limited amount of memory. e.g. controller for an automatic door.
The controller is in either of two states: “OPEN” or “CLOSED,” representing the corresponding condition of the door.
There are four possible input conditions: “FRONT” (meaning that a person is standing on the pad in front of the doorway), “REAR” (meaning that a person is standing on the pad to the rear of the doorway), “BOTH” (meaning that people are standing on both pads), and “NEITHER” (meaning that no one is standing on either pad).
State Diagram:
![[Pasted image 20250305130446.png]]

|        | Neither | Front | Rear   | Both   |
| ------ | ------- | ----- | ------ | ------ |
| Closed | Closed  | Open  | Closed | Closed |
| Open   | Closed  | Open  | Open   | Open   |
The controller moves from state to state, depending on the input it receives.
if the input BOTH is received, it stays CLOSED because opening the door risks knocking someone over on the rear pad.
This controller is a computer that has just a single bit of memory, capable of recording which of the two states the controller is in.

**Strings**, by definition are finite (have only a finite number of symbols).
Most languages of interest are infinite (contain an infinite number of strings) However, in order to work with these languages, we must be able to specify or describe them in ways that are finite.

**Finite automata** is used to describe these infinite languages. 
Finite automata are finite collections of states with transition rules that take you from one state to another.
There are two types of finite automata 
- Deterministic Finite Automata (DFA). 
- Nondeterministic Finite Automata (NFA).
A deterministic automaton is one in which each move is uniquely determined by the current configuration. If we know the internal state, the input, and the contents of the temporary storage, we can predict the future behavior of the automaton exactly.
In a nondeterministic automaton, this is not so. At each point, a nondeterministic automaton may have several possible moves, so we can only predict a set of possible actions.

##### DETERMINISTIC FINITE AUTOMATA (DFA)
A Deterministic Finite Automata (DFA) is defined by the quintuples
- M = $(Q, \sum , \delta, q_0, F)$, Where:
	- Q : is a finite set of internal states
	- $\sum$ : is a finite set of symbols called the input alphabet
	- $\delta$ : $Q ~X ~E ~ \rightarrow Q$ is a total function called the transition function.
	- $q_0 \in Q$ : is the initial state
	- $F \subseteq Q$: is a set of final states.

A deterministic finite automaton operates in the following manner.
1. Initially it is at $q_0$ and its input is at the leftmost symbol of the input string, and goes right.
2. When the end of the string is reached, the string is accepted if the automaton is in one of its final states. Otherwise, the string is rejected.
3. The input mechanism can move only from left to right and reads exactly one symbol on each step.
4. The transitions from one internal state to another are governed by the transition function $δ$.
For example, if $δ (q_0 , a) = q_1$, then if the DFA is in state $q_0$ and the current input symbol is $a$, the DFA will go into state $q_1$.

To visualize finite automata, we use transition graphs (State diagram), in which the vertices represent states and the edges represent transitions.

The ***Initial state*** will be identified by an incoming unlabeled arrow not originating at any vertex.
***Final* states** (labeled with $q_f ∈F$) are drawn with a double circle.

More formally, if $M = (Q, Σ, δ, q_0, F)$ is a deterministic finite automaton, then its associated transition graph (state diagram) has exactly $|Q|$ vertices, each one labeled with a different $q_i∈Q$.
For every transition rule $δ(q_i,a) = q_j$, the graph has an edge ($q_i, q_j$) labeled $a$.

The deterministic Finite Automat will be present in three features; these representations are: 
1. **Instantaneous description**, which is test based English like explanation
2. **Transition graph** (state diagram), which is represent by graph (sent of vertices and edges) 
3. **Transition table**, by making the states of the machine as rows and the input as columns

Example: 
Consider a machine given by $M_1= (\{q_0, q_1, q_2\}, \{0, 1\},\delta, q_0,\{q_1\})$, Where the transition function ($δ$) (movement) is described below.
$δ(q_0,0) = q_0,$ $δ(q_0,1) = q_1,$ 
$δ(q_1,0) = q_0,$ $δ(q_1,1) = q_2,$ 
$δ(q_2,0) = q_2$, $δ(q_2,1) = q_1,$ 

| $δ$   | 0     | 1     |
| ----- | ----- | ----- |
| $q_0$ | $q_0$ | $q_1$ |
| $q_1$ | $q_0$ | $q_2$ |
| $q_2$ | $q_2$ | $q_1$ |
![[Pasted image 20250305162309.png]]
- if we take the string "1001"
- After reading first symbol, 1-------$δ(q_0,1) = q_1$, -> $δ(q_1,0) = q_0$ ->  $δ(q_0,0) = q_0$ -> $δ(q_0,1) = q_1$
When the string ended the transition graph terminates at $q_1$. The state q1 is sated as final state, so we can say the string $1001$ is accepted by the machine $M_1$. we write $δ^*(q_0,1001) = q_1$.
- After trying a few more examples, you would see that M1 accepts all strings that end in odd number of 1’s.
- Thus, the language accepted by $M_2$ is $L(M_2) = \{w~ |w \text{ ends in odd number of 1’s}\}$.

**Extended transition function** 
In order to discuss about the relationship between languages and machines, it is convenient to introduce the extended transition function δ* : Q × Σ* → Q.
The second argument of δ* is a string, rather than a single symbol, and its value gives the state the automaton will be in after reading that string. For example, if
$δ(q_0,a) = q_1$ and $δ(q_1,b) = q_2,$ 
then 
$δ ^* (q_0,ab) = q_2$
Formally, we can define δ* recursively by 
$δ^ * (q,\lambda) = q$,…………………………….…….(2.1) 
$δ ^* (q,wa) = δ(δ ^* (q,w),a)$,……………………(2.2)
for all $q ∈ Q$, $w ∈ Σ^*$, $a ∈ Σ$. To see why this is appropriate, let us apply these definitions to the simple case above. First, we use (2.2) to get
$δ^ * (q,ab) = δ(δ^* (q,a), b)$ ……………………………………..(2.3)
But $δ^* (q_0,a) = δ(δ ^* (q_0, \lambda), a)$ 
	=$δ(q_0, a)$ 
	=$q_1$ 
Substituting this into (2.3), we get 
$δ^ * (q_0,ab) = δ(q_1, b)=q_2$


**Languages and DFA's**
**Definition 2.2**: The language accepted by a machine $M = (Q, Σ,δ, q_0,F)$ is the set of all strings on $Σ$ accepted by M. Informal notation, $L(M)=\{w ∈ Σ^* : δ^* (q_0,w) ∈ F\}$ 
- *Note*: we require that δ, and consequently δ*, be total functions.
- At each step, a unique move is defined, so that we are justified in calling such an automaton deterministic.

Every finite automaton accepts some language.
The family of languages that is accepted by deterministic finite accepters is called **regular language**.

**Definition 2.3**: A language L is called *regular* if and only if there exists some deterministic finite accepter M such that $L= L(M)$.
If a language L is regular, so are $L^2 ,L^3 ,…$ 

**Trap State** - a state we can get into but can never escape.

**Strings and Languages** 
Let $X = \{a,b,c\}$ and $Y = \{abb, ba\}$. 
Then – $XY = \{aabb, babb, cabb, aba, bba, cba\}$ 
$X0 = \{e\}$ 
$X1 = X = \{a,b,c\}$ 
$X2 = XX = \{aa,ab,ac,ba,bb,bc,ca,cb,cc\}$ 


### NON-DETERMINISTIC FINITE AUTOMATA (NFA)
A transition is nondeterministic if there are several (possibly zero) next states from a state on an input symbol or without any input.
A transition without input is called as *𝝀-transition*.
**Formal Definition** 
Formally, a nondeterministic finite automaton (NFA) is a quintuple
$M = (Q, \sum, δ, q_0 , F)$ 
- Q = a finite set of states
- $\sum$ = a finite set alphabet
- $δ$ = transition function
	total function $δ: Q×(Σ∪{λ}) → 2^Q$ - power set of Q (Pot(Q))
- $q_0$ - initial/ starting state $q_0 \in Q$ 
- $F$ = final or accepting states $F\subseteq Q$ - subset of Q ✓ - same as DFA

3 major differences from DFA
1. the range of $δ$ is the powerset of Q, $2^Q$, it is not a single value but a subset of Q.
2. We allow $\lambda$ as the second argument of $δ$, NFA can make transitions without consuming an input symbol.
3. in NFA, the set $δ(q_i,a)$ might be empty, no transition is defined of this specific situation.

**Example**:
$Q =  \set {0, 1, 2, 3}$,   $q_0 = 0$,      $F = \set{ 3 }$ ,      $\sum = \set{ a, b }$

![[Pasted image 20250318164043.png]]

| Q   | a             | b        |
| --- | ------------- | -------- |
| 0   | { 0, 1 }      | { 0 }    |
| 1   | $\varnothing$ | $\set 2$ |
| 2   | $\varnothing$ | $\set 3$ |
- This machine excepts all strings that end with `abb`.

Change in $\delta$ for NFA:
- For an DFA M, $\delta(q, a)$ results in one and only one state for all states q and alphabet a. 
- For an NFA M, $\delta(q, a)$ can result in a **set of states**, zero, one, or more states:

![[Screenshot 2025-03-18 165934.png]]

##### Computing with NFA’s
- We always start from start state. Call it the root of the computation.
- Then we might go to different states on one symbol.
- Then from those states to new sets of states, creating a ***tree-like*** computation
- If one of the paths ends up in a final state, then ACCEPT, else REJECT.
We Might have multiple paths for a given input string.

*Extended transition function* $\delta^*$  of a NFA with transition function $\delta$ is 
$$
\delta^*: Q \times \Sigma^* \to \mathcal{P}(Q)
$$
which maps a state and an input string to a **set of states**, as follows:
**Basis (Empty string):** 
For any state $q_i \in Q$,
$$
\delta^*(q_i, \lambda) = \{q_i\}
$$

That is, processing the empty string $\lambda$ leaves the automaton in its starting state

**Recursive Step:** 
Let $w = av$, where $a \in \Sigma$ and $v \in \Sigma^*$, and suppose $|w| \geq 1$. Then for any $q_i \in Q$,

$$
\delta^*(q_i, av) = \bigcup ~_{p \in \delta(q_i, a)}~ \delta^*(p, v)
$$
> That is:
> First, process symbol $a$ from state $q_i$, yielding a set of states $\delta(q_i, a)$.
> Then, recursively process the remaining string $v$ from each of those states.
> The final result is the union of all those outcomes.

**Domain Conditions:** 
This holds for all:
* $q_i \in Q$: initial state
* $q_j \in Q$: reachable states
* $v \in \Sigma^*$: strings over the input alphabet
---
A NFA M accepts a word (strings) w if $δ*(q_0, w) ∩ F \not =  \varnothing$. The language L(M) of a NFA is the set of all words(strings) accepted by M.
*The language of a NFA* M is
- $L(M) = \{w \in \sum^*~ |~ \delta^ * (q_0 , w) \cap F ≠ \varnothing\}$  
- The language consists of all strings w for which there is a walk labeled w from the initial vertex of the transition graph to some final vertex.

**Example**: Consider the transition graph for the machine M1 in figure 2.18 and determine the language accepted by the NFA $M_1$?
![[Pasted image 20250527075722.png]]
1. From the initial state $q_0$ one can reach back to $q_0$ via strings from $a^*$ (any number of a) or from $a\lambda b^*b$, i.e., $ab^+$ (a followed by at least one b), or via a string which is a mixture of strings from the above two sets. That is, the strings of $(a + ab^*b)^*$ will lead us from $q_0$ to $q_0$.
2. Also, note that the strings of $ab^*$ will lead us from the initial state $q_0$ to the final state $q_2$.
3. Thus, any string accepted by the NFA can be of the form a string from the set $(a + abb^*)^*$ followed by a string from the set $ab^*$.
Hence, the language accepted by the NFA can be represented by $(\{a\} \cup \{a\}\{b\}^+)^* \{a\}\{b\}^*$ or with the help of regular expression we can represent $(a + abb^*)^*ab^*$.

*Dead configuration* - no outputs from a state.
Nondeterministic machines can serve as models of *search-and-backtrack* algorithms.

---
### Equivalence of DFA & NFA
NFAs are convenient for humans to design languages, but their non-deterministic nature makes them difficult for computers to directly implement. Fortunately, any NFA can be automatically converted into an equivalent DFA, which is suitable for computer execution.


**Proposition 2.1: The languages accepted by DFAs are precisely the languages accepted by NFAs.**

**Proof:**
To prove that DFAs and NFAs accept the same class of languages (known as regular languages), we must demonstrate two things:

1.  **Every language accepted by a DFA is also accepted by an NFA.**
    * Consider any given DFA. We can transform this DFA into an NFA that accepts the exact same language.
    * The conversion is straightforward: If the DFA has a transition $δ_D(q, a) = p$ (meaning from state $q$ on input $a$, it deterministically goes to state $p$), then for the NFA, we simply define its transition function as $δ_N(q, a) = \{p\}$.
    * Since a DFA, by definition, always has at most one next state for any given input, this constructed NFA will also behave deterministically, always being in a set containing exactly one state at any point – the same state the original DFA would be in. Therefore, any language accepted by a DFA is also accepted by such a constructed NFA.

2.  **Every language accepted by an NFA is also accepted by a DFA.**
    * This direction is proven by a fundamental algorithm called **Subset Construction**.
    * The core idea of Subset Construction is that for any NFA, we can build an equivalent DFA whose states correspond to the *sets of states* that the NFA could possibly be in at any given moment.
    * For example, if an NFA could be in states $\{q_1, q_3\}$ after reading a certain part of the input, the equivalent DFA would have a single state representing this set $\{q_1, q_3\}$. The transitions for this new DFA state are then determined by considering all possible transitions from all states within that set in the original NFA.
    * While the DFA constructed via Subset Construction will accept precisely the same language as the original NFA, it's important to note that the number of states in the resulting DFA can be exponentially larger than the number of states in the original NFA. This exponential increase in states is a trade-off for converting non-determinism into determinism.

**Conclusion:**

Since every language accepted by a DFA can also be accepted by an NFA, and every language accepted by an NFA can be converted into a DFA, it follows that DFAs and NFAs accept exactly the same class of languages, which are known as the regular languages.

Two finite accepters (automata), $M_1$ and $M_2$, are said to be **equivalent**, if they both accept the same language. $L(M_1) = L(M_2)$,
There are generally many accepters for a given language, so any DFA or NFA has many equivalent accepters.

e.g. The state diagram DFA M1 and NFA M2 accepts $(a|b) ^*~abba(a|b) ^*$.
![[Pasted image 20250318173155.png]]

#### Subset Construction
Given an NFA with states $Q,$ inputs $Σ$, transition function $δ_N$ , state state $q_0$ , and final states $F$, construct equivalent DFA with:
- States $2^Q$.
- Inputs $Σ$.
- Initial state $\set{q_0 }$.
- Final states = all those with a member of $F$.

The DFA states have names that are sets of NFA states.
But as a DFA state, an expression like $\set{p,q}$ must be read as a single symbol, not as a set.
The transition function $δ_D$ is defined by: $δ_D (\set{q_1 ,…,q_k }, a)$ is the union over all $i = 1,…,k$ of $δ_N (q_i , a)$.

**Example**:
Determine DFA from the given NFA.
$M=(\set{q_0, q_1, q_2}, \set{a, b}, \delta, q_0, \set{q_1})$ %% NOT A SET %% 

| $\delta$ |        a        |        b         |
| :------: | :-------------: | :--------------: |
|  $q_0$   | $\set{q_1,q_2}$ |  $\varnothing$   |
|  $q_1$   |      $q_1$      | $\set{q_1, q_1}$ |
|  $q_2$   |  $\varnothing$  |      $q_0$       |

![[Pasted image 20250318174918.png]]

DFA:
$\delta(\set{q_0}, a) = \set{q_1, q_2}$ -> $\delta(\set{q_0}, a)$ can go to $q_1$ and there is a chance to go to $q_2$   --- 1
$\delta(\set{q_0}, b) = \varnothing$ 
$\delta(\set{q_1, q_2}, a) = \set{q_1, q_2}$  -> we got $\set{q_1, q_2}$ from $\{1\}$ and this is the union of $\delta(\set{q_1}, a)$ & $\delta(\set{q_2}, a)$ 
$\delta(\set{q_1, q_2}, b) = \set{q_0}$ 
$\delta(\varnothing, a) = \varnothing$ 
$\delta(\varnothing, b) = \varnothing$ 

now we have calculated all the paths we can draw the DFA.
	![[Screenshot 2025-03-18 175727.png]]

**Conversion from NFA to DFA**
1. Create a graph $G(D)$ with vertex $\set{q_0}$. Identify this vertex as the initial vertex. 
2. Repeat the following steps until no more edges are missing. take any vertex $\set{q_i,q_j,…,q_k}$ of $G(D)$ that has no outgoing edge for some $a \in \sum$.  Compute $\delta^*(q_i,a), ~\delta^*(q_j, a),...,\delta^*(q_k, a)$.
	If $\delta^*_N(q_i, a) ~\cup ~\delta^*_N(q_j, a)~\cup~ .... ~\cup ~\delta^*_N(q_k, a)=\set{q_l, q_m, .... , q_n}$,
	create a vertex for $G(D)$ labeled $\set{q_l,q_m,…,q_n}$ if it is not already exist. Add to G(D) an edge from $\set{qi,qj,…,qk}$ to $\set{q_l,q_m,…,q_n}$ and label it with a.
3. Every state of $G(D)$ whose label contains any $q_f \in F_N$ is identified as a final vertex. // if it includes any of the initially final states
4. If $M_N$ accepts $\lambda$, the vertex $\set{q_0}$ in $G(D)$ is also made a final vertex.

**Final Note**:
These “sets of states” are just **labels** for DFA states.
So:
- `{A, B}` is just a name. (even though we know it was used for conversion)
- DFA sees it as a single place, even though it _means_ multiple possible NFA locations.

### Minimization of DFA

```YTcomment
We start with 0-equivalence. Basically create 2 subsets, one with final states and the other with non-final states.
Now within each subset, try to find if constituent states are 1 equivalent. The way to do that is to pick two states at a time. If the two states transition to the same 0-equivalence subset on each input, then they are 1-equivalent.
If A,B and B,C are 1-equivalent, then A,C are also 1-equivalent.
If A,B are not 1-equivalent and B,C are, then A,C cannot be 1-equivalent
Repeat this process recursively till the output of n-equivalent and (n-1) equivalent is the same.
From that point, the subsets won’t change
All states within the same subset are equivalent
```
**Definition**: Two states $q_0$ and $q_1$ of a DFA are called **indistinguishable/ Equivalent** if
- $\delta^*(q_0,w) \in F$ implies $\delta^*(q_1, w) \in F$, and 
- $\delta^*(q_0, w) \notin F$ implies $\delta^*(q_1, w) \notin F$, for all $w \in \Sigma^*$.
- If $|w| = n$, A and B are said to be n equivalent.
If, on the other hand, there exists some string $w \in \Sigma^*$ such that $\delta^*(q_0,w) \in F$ implies $\delta^*(q_1,w) \notin F$, or vice versa, then the states $q_0$ and $q_1$ are said to be *distinguishable* by a string $w$.

Minimization of DFA means reducing the number of states from given FA. Thus, we get the FSM(finite state machine) without redundant states after minimizing the FSM.

**Step 1:** Remove all the states that are unreachable from the initial state via any set of the transition of DFA.
Step 2: Partition the States - Group 1: **Final states**  Group 2: **Non-final states**
**Step 3:** Now we start checking
> If two states in the same group behave **differently** under some input (they transition to states in **different groups**), then they must be split into separate group

Keep doing this **over and over** until no more splitting is needed.

**Step 4:** MERGE: After the partitioning is stable:
- States in the same group are **equivalent**, and we can **merge them**.
- Build a **new DFA** where each group becomes a **single state**.

**Example**:
![[Pasted image 20250412161205.png]]
Step 1: No Unreachable States
Step 2: Partition: $\set{q_0, q_1, q_3}$ and $\set{q_2, q_4}$ 
Step 3: when we compute $\delta(q_0, 0)=q_1$ and $\delta(q_1, 0)=q_2$ we see that they results in states from different groups (final and non-final) so they are distinguishable.
	so we put them in different sets, $\set{q_0 ,q_1 ,q_3}$ is split into $\set{q_0}$ and $\set{q_1 ,q_3}$.
	Also, since $δ(q_2 ,0) = q_3$ and $δ(q_4 , 0) =q_4$ , the class $\set{q_2 ,q_4}$ is split into $\set{q_2}$ and $\set{q_4}$.
	The states $q_1$ and $q_3$ goes to the same state $q_2$ on every character so they remain grouped.
	The rest of the computations show that no further splitting is needed.
Final minimal DFA
![[Pasted image 20250412162626.png]]
1 and 3 are combined to 13

**Example:**
![[Pasted image 20250318181918.png]]

**Solution:** 
**Step 1:** In the given DFA, q2 and q4 are the unreachable states so remove them.
**Step 2:** Draw the transition table for the rest of the states.

| State  | 0     | 1     |
| ------ | ----- | ----- |
| →$q_0$ | $q_1$ | $q_3$ |
| $q_1$  | $q_0$ | $q_3$ |
| *$q_3$ | $q_5$ | $q_5$ |
| *$q_5$ | $q_5$ | $q_5$ |
**Step 3:** Now divide rows of transition table into two sets as: 
1. One set contains those rows, which start from non-final states:

| State | 0     | 1     |
| ----- | ----- | ----- |
| $q_0$ | $q_1$ | $q_3$ |
| $q_1$ | $q_0$ | $q_3$ |
2. Another set contains those rows, which starts from final states.

| State | 0     | 1     |
| ----- | ----- | ----- |
| $q_3$ | $q_5$ | $q_5$ |
| $q_5$ | $q_5$ | $q_5$ |

**Step 4:** Set 1 has no similar rows so set 1 will be the same.
**Step 5:** In set 2, row 1 and row 2 are similar since $q_3$ and $q_5$ transit to the same state on 0 and 1. So skip $q_5$ and then replace $q_5$ by $q_3$ in the rest.

| State | 0     | 1     |
| ----- | ----- | ----- |
| $q_3$ | $q_3$ | $q_3$ |
**Step 6:** Now combine set 1 and set 2 as:

| State  | 0     | 1     |
| ------ | ----- | ----- |
| →$q_0$ | $q_1$ | $q_3$ |
| $q_1$  | $q_0$ | $q_3$ |
| $*q_3$ | $q_3$ | $q_3$ |
![[Pasted image 20250318182717.png]]

Ex:
![](https://www.youtube.com/watch?v=0XaGAkY09Wc)
! [] (https://www.youtube.com/watch?v=ex9sPLq5CRg) -- example 2

# CH-3 : Regular Language and Grammars
> [!info] Know
> $\lambda \text{ is the same as } \large\epsilon$ , both represent empty string

### Regular Expression
Regular languages can be written using **regular expressions**, which are made from letters (like `a`, `b`), **parentheses**, and three symbols:
- `+` means **or** (choice),
- `·` means **then** (concatenation),
- `*` means **repeat any number of times** (including zero). Star closure (Kleene star)

For example:
- `a` means the language with just the string "a".
- `a + b + c` means **"a or b or c"**.
- `(a + (b·c))*` means you can have **any number** of "`a`"s or "`bc`"s in any order
	It includes things like: `λ` (empty string), `a`, `bc`, `aa`, `abc`, `bcbc`, `bca` etc.

**Definition**:
We construct regular expressions from **primitive constituents/regular expressions** by repeatedly applying certain recursive rules. like arithmetic expressions.

Let $\sum$ be a given alphabet, then.
1. $\emptyset$,$λ$ and $a$ ∈ Σ are all regular expressions. called **primitive regular expressions**.
2. If $r_1$ and $r_2$ are regular expressions, so are $(r_1+r_2)$, $(r_1 . r_2)$  $(r_1^*)$. (closed under the 3)
3. A String is a regular expression IFF it can be derived from the primitive **regular expressions** by a finite number of applications of the rules in (2).
with $L((r^*)) = (L(r))^*$.

*Example*: For $Σ = \set{a, b, c}$, the string $(a+b+c)^* .(c+\emptyset)$ is a regular expression, since it is constructed by application of the above rules.

**Languages Associated with Regular Expressions** 
If $r$ is a regular expression, we will let $L(r)$ denote the language associated with $r$.
Generally, there are an unlimited number of regular expressions for any given language

***Definition***:
1. **\emptyset** is a regular expression that represents the **empty set** — it matches nothing.  
    → $L(\varnothing)=\set{\varnothing}$ 
2. **λ** is a regular expression that represents the set containing the **empty string**.  
    → $L(λ)=\{λ\}$ 
3. For any symbol **a** in the alphabet $Σ$, the expression **a** represents the set containing just "a".
    → $L(a) = \{a\}$ 
4. If **r₁** and **r₂** are regular expressions, then:
    - **r₁ + r₂** means the **union** of their languages:  
        → $L(r1+r2)=L(r1)∪L(r2)$ 
    - **r₁ · r₂** (or just **$r₁r₂$**) means **concatenation** of the two languages:  
        → $L(r1⋅r2)=L(r1)⋅L(r2)$ 
    - **(r₁)** is just grouping — doesn’t change the meaning:
        → $L((r1))=L(r1)$ 
    - **(r₁)*** means the **Star Closure** — zero or more repetitions of strings from $L(r_1)$:  
        → $L(r₁^*) = (L(r₁))^*$ 
For Grouping - We establish a set of precedence rules for evaluation in which star-closure precedes concatenation and concatenation precedes union.

Example: 
For $Σ = \{a,b\}$, the expression $r=(a+b)^*(a+bb)$ is regular. It denotes the language?
- $(a + b)^*$ 
    → This part means:  
    **“Any number of a’s and b’s in any order — including none.”**  
    So it can match strings like: `""`, `a`, `b`, `ab`, `ba`, `ababbb`, etc.
- $(a + bb)$ 
    → This part means:  
    **“Either a single 'a' or the string 'bb'.**
So the full expression: $(a+b)^∗(a+bb)$ ...means
> All strings over {a, b} that **end with either 'a' or 'bb'**.
> $L (r)= \{a, bb, aa, abb, ba, bbb,…\}$ 

Example:
The expression $r =(aa)^* (bb)^* b$ denotes the set of all strings with an even number of a’s followed by an odd number of b’s; that is, $L (r) = \{a^{2n}b^{2m+1} : n ≥ 0, m ≥ 0\}$
Ex:
Express with regular expression the set of all strings over $\{a,b\}$ which do not contain $(ab)$ as a substring.
- By analyzing the language one can observe that precisely the language is as follows. $\{b^n a^m  : n,m>=0\}$ 
- Thus, the regular expression of the language is $(b^*a^*)$.
Ex: Express the language L over $\{0,1\}$ that contains 01 or 10 as sub-string with regular expression?
-  L = {x| 01 is substring of x} ∪ { x| 10 is substring of x} = $\{y01z | y,z∈Σ*\} ∪ \{u10v | u,v∈Σ*\}$ = $Σ*{01} Σ*∪ Σ*{10} Σ*$ 
- = $(0+1)*01(0+1)* + (0+1)*10(0+1)*$ 

Examples: 
- $L1= \{ a^nb^m: n ≥ 4,m ≤ 3\}$ -> $a^4 a^* (b|bb|bbb|\lambda)$ 
- $L2= { a^nb^m: n < 4,m ≤ 3}$ -> $(a|aa|aaa|\lambda) (b|bb|bbb|\lambda)$ 

What languages do the expressions $(\emptyset^*)^*$ and $a\emptyset$ denote?
- $(\emptyset^∗)^∗={\LARGE\epsilon}$:
    - $\emptyset^∗$ means "zero or more repetitions of nothing". The only way to do that is to have nothing, which is represented by the empty string, ϵ. So, $\emptyset^∗=\{ϵ\}$.
    - $(\{ϵ\})^∗$ means "zero or more repetitions of the empty string". Any number of empty strings concatenated together is still the empty string. So, $(\{ϵ\})^∗=\{ϵ\}$.
- $a\emptyset=\emptyset$: 
    - $a\emptyset$ means taking a string from the first part ("a") and concatenating it with a string from the second part (nothing). Since there are no strings in the second part, you can't form any resulting strings. Therefore, the language is empty.

#### Identities for Regular Expressions
Two regular expressions P and Q are equivalent (we write P ≡Q) if P and Q represent the same set of strings. 
I. $\emptyset+R = R$ 
II. $\emptysetR = R\emptyset = \emptyset$ 
III. $\lambdaR = R \lambda = R$ 
IV. $\lambda^* = \lambda$ and $\large \emptyset^* = \lambda$ 
V. $R + R = R$ 
VI. $R^*R^* = R^*$ 
VII. $RR^* = R^*R$ 
VIII. $(R^*) = R^*$ 
IX. $\lambda + RR^* = R^* = \lambda + R^*R$ 
X. $(PQ)^*P = P(QP)^*$ 
XI. $(P + Q)^* = (P^*Q^*)^* = (P^* + Q^*)^*$ 
XII. $(P + Q)R = PR + QR and R(P + Q) = RP + RQ$ 

###### Arden’s theorem
***Theorem 3.1***:  Let P and Q be two regular expressions over Σ. If P does not contain \lambda, then the following equation in R, namely
$R = Q + RP$ 
has a unique solution (i.e. one and only one solution) given by $R = QP^*$.
! [] (https://www.youtube.com/watch?v=Idl_0mPzZjE) PROOF

#### EQUIVALENCE WITH FINITE AUTOMATA
*Regular Expressions and Regular Languages*,
For every regular language there is a regular expression, and for every regular expression there is a regular language.

**Regular Expressions Denote Regular Languages** 
***Theorem 3.2***: A language is regular if and only if some regular expression describes it. This theorem has two directions. We state and prove each direction as a separate lemma.
**Lemma 1**: If a language is described by a regular expression, then it is regular.
>*Theorem*: Let r be a regular expression. Then there exists some nondeterministic finite
>accepter that accepts L(r). Consequently, L(r) is a regular language.

**Proof:** We begin with automata that accept the languages for the simple regular expressions 
$\emptyset$, $λ$, and $a ∈ Σ$.
![[Pasted image 20250412181504.png]]
Assume now that we have automata $M (r_1 )$ and $M (r_2 )$ that accept languages denoted by regular expressions $r_1$ and $r_2$ , respectively.
We need not explicitly construct these automata, but may represent them schematically
![[Pasted image 20250412181757.png]]
we then construct automata for the regular expressions $r_1$ + $r_2$ , $r_1r_2$ , and $r_1^*$.
![[Pasted image 20250412181941.png]] $L(r_1+r_2)$ 
![[Pasted image 20250412182015.png]] $L(r_1r_2)$ 
![[Pasted image 20250412182037.png]] $L(r_1^*)$ 
As indicated in the drawings, the initial and final states of the constituent machines lose their status and are replaced by new initial and final states. By stringing together several such steps, we can build automata for arbitrary complex regular expressions.

Example 3.7 Find an $NFA$ that accepts $L(r)$, where $r=(a + bb)^* (ba^* + λ)$ 

![[Pasted image 20250412183147.png]]
M1 accepts $L(a + bb)$. 
M2 accepts $L (ba^* + λ)$.
$another example on page 62 & 63

**Lemma 3**: If a language is regular, then it is described by a regular expression.
**Key Idea**  
If a language $( L )$ is regular, then it is accepted by a DFA. We convert the DFA into a regular expression via:  
1. **DFA → GNFA** (Generalized NFA with regex-labeled transitions).  
2. **GNFA → Regex** by state elimination.  

**Step 1: Convert the DFA to a GNFA**  
A **GNFA** (Generalized Nondeterministic Finite Automaton) differs from a DFA in that:  
- Transitions are labeled with **regular expressions** (not just symbols).  
- It reads **blocks of symbols** (not just one at a time).
- Formally it is a 5-tuple,$(Q, Σ, δ, q_{start}, q_{accept})$, where
	1. $Q$, $Σ$, $q_{start}$ & $q_{accept}$ the same and 
	2. $δ: (Q − {q_{accept}}) × (Q − {q_{start}}) →r$ is the transition function,
		- no arrows leaving $q_{accept}$ and no entering $q_{start}$ 
		- $δ(q_i,q_j)=r$ means transition from $q_i$ to $q_j$ is labeled with regex $r$ 

**Special Form GNFA Requirements**  
For uniformity, we structure the GNFA as follows:  
1. **Single start state** with $( \lambda )$-transitions to all others (no incoming arrows). 
2. **Single accept state** with $( \lambda )$-transitions from all others (no outgoing arrows).  
3. **All other states** have transitions to every other state (including themselves), labeled with regexes.  

**Conversion Steps** 
1. Add a new **start state** with a $( \lambda )$-transition to the original start state.  
2. Add a new **accept state** with $( \lambda )$-transitions from all original accept states.  
3. Replace multi-label transitions with **union regexes** (e.g., $( a, b )$ becomes $( a \cup b ))$.  
4. Add $( \emptyset )$-transitions where no transition existed (these are non-matching).  

**Step 2: Reduce the GNFA to a Regex**  
We iteratively **eliminate states** until only the start and accept states remain.  
**State Elimination Rule**  
Suppose we remove state $( q )$. For every pair of states $( q_i )$ $(incoming)$ and $( q_j )$ $(outgoing)$:  
1. Let:  | $(CONVERT(G) \text{ procedure on book})$ 
   - $( R_1 )$ = transition from $( q_i )$ to $( q )$,  
   - $( R_2 )$ = transition from $( q )$ to itself $(loop)$,  
   - $( R_3 )$ = transition from $( q )$ to $( q_j )$,  
   - $( R_4 )$ = existing transition from $( q_i )$ to $( q_j )$.  
The new transition from $( q_i )$ to $( q_j )$ becomes:  
$$
R_4 \cup (R_1 R_2^* R_3)
$$
(This accounts for all paths that used to go through $( q )$ 
e.g.	
![[Pasted image 20250523102658.png]]
**Repeat Until Only 2 States Remain** 
- After eliminating all intermediate states, the GNFA will have:  
  - The **start state** → **accept state** with a single transition labeled **the final regex**.  

- For a 3 state DFA steps are - `3 state DFA -> 5 state GNFA -> 4 state GNFA -> 3 state GNFA -> 2 state GNFA -> (REGEX)`

**Example**:
Consider a DFA for the language $( L = \{ w \mid w \text{ ends with } 01 \} )$: 
1. **Original DFA**:
	- States: $q_0, q_1, q_2~ (accepting)$. 
	- Transitions: 
		- $( q_0 \xrightarrow{0} q_1 )$, $( q_0 \xrightarrow{1} q_0 )$,  
		- $( q_1 \xrightarrow{0} q_1 )$, $( q_1 \xrightarrow{1} q_2 )$,  
		- $( q_2 \xrightarrow{\hspace{1mm}0,1\hspace{1mm}} q_2 )$.
2. **Convert to GNFA**:
	 - Add new start $( q_s )$ and accept $( q_a )$.  
	 - Connect $( q_s \xrightarrow{\lambda} q_0 )$, $( q_2 \xrightarrow{\lambda} q_a )$.  
3. **Eliminate $( q_1 )$**:
	 - New transition $( q_0 \to q_2 )$: $( 0(0^*1) )$.  
4. **Eliminate $( q_0 )$**:
	 - New transition $( q_s \to q_2 )$: $( 1^*0(0^*1) )$.  
5. **Final Regex**:
   $1^*0(0^*1) \quad \text{(simplifies to }1^*00^*1\text{)}$

- If we have 2 or more final states we converge them all to a single new final state all with a $\lambda$ transition.
	- see Example 3.6 on page 70.


#### ALGEBRAIC METHOD USING ARDEN’S THEOREM
This is another way to find regex from DFA/NFA.
The following assumptions are made regarding the transition system:
1. The transition graph does not have $\lambda$-moves.
2. It has only one initial state, say $V_1$.
3. Its vertices are $V_1, \dots, V_n$. (they are also regexes)
4. $V_i$ the regular expression represents the set of strings accepted by the system. And if $V_i$  happens to be a final state, then the regular expression $V_i$ also represents a set of strings that are accepted by the system when they end in that final state..
5. $\alpha_{ij}$ denotes the regular representing the set of labels of edges from $V_i$ to $V_j$. When there is no such edge, $\alpha_{ij} = \emptyset$. Consequently, we can get the following set of equations in $V_1, \dots, V_n$:
	$V_1 = V_1 \alpha_{11} + V_2 \alpha_{21} + \dots + V_n \alpha_{n1} + \lambda$ 
	$V_2 = V_1 \alpha_{12} + V_2 \alpha_{22} + \dots + V_n \alpha_{n2}$ 
	$\dots$ 
	$V_n = V_1 \alpha_{1n} + V_2 \alpha_{2n} + \dots + V_n \alpha_{nn}$ 
By repeatedly applying substitutions and Theorem 3.1 (Arden's theorem), we can express $V_i$ in terms of $\alpha_{ij}$'s.
For getting the set of strings recognized by the transition system, we have to take the "union" of all $V_i$'s corresponding to final states.

**Example** More on page 72&+
Let’s consider a simple DFA:
*DFA Description:* 
* $M = (\{V_1, V_2\}, \{a, b\}, \delta, V_1, \{V_2\})$ 
* $\delta$ given by: 
	* $V_1 \xrightarrow{a} V_1$ 
	* $V_1 \xrightarrow{b} V_2$ 
	* $V_2 \xrightarrow{a} V_2$ 

*Step 1: Define Regular Expression Equations* 
* $V_1 = V_1a + V_2\emptyset + \lambda$ (initial state gets $\lambda$)
* $V_2 = V_1 b + V_2 a$  
Simplify:
* $V_1 = V_1  a + \lambda$, $(V_2 \varnothing = \varnothing)$ 
* $V_2 = V_1  b + V_2  a$ 
*Step 2: Solve Using Arden’s Theorem* 
Solve for $V_1$:
$$
V_1 = \lambda + V_1  a \Rightarrow V_1 = a^* \quad \text{(by Arden’s Theorem)}
$$

Substitute $V_1 = a^*$ into $V_2$:
$$
V_2 = a^*  b + V_2  a
\Rightarrow V_2 = a^* b + V_2 a
\Rightarrow V_2 = a^* b a^* \quad \text{(by Arden’s Theorem)}
$$

*Final Step: Expression for the DFA* 
Since **final state is** $V_2$, the DFA accepts strings represented by:
$$
\boxed{a^* b a^*}
$$
Summary:
* You write equations based on transitions using regular expressions.
* Use **Arden’s theorem** to solve them.
* Final answer is the union of the expressions for **final states**.
* The goal is to structure the elements in a way to achieve Adrian's theorem.

---
### REGULAR GRAMMARS 
A third way of describing regular languages is by means of certain grammars.

Linear-Grammars
##### RIGHT- LINEAR AND LEFT-LINEAR GRAMMARS
**Definition**: A grammar $G =(V, T, S, P)$ is said to be right-linear if all productions are of the form
- $A → xB$,
- $A → x$,
- where $A, B ∈ V$, and $x ∈ T^*$. 

**Definition**: A grammar is said to be left-linear if all productions are of the form
- $A → Bx$, or
- $A → x$ 

A regular grammar is one that is either right-linear or left-linear.
*In a regular grammar*: ^rules
- Only one non-terminal (variable) is allowed on the right-hand side of a production.
- That non-terminal must be in a consistent position (always at the beginning or the end).

*Example* 
1. The grammar $G_1 = ({S}, {a,b},S,P_1)$, with $P_1$ given as
	- $S →abS|a$ 
	- is right-linear.
2. The grammar $G_2 = (\{S, S_1, S_2\}, \{a, b\}, S, P_2)$, with productions
	- S →$S_1ab$,
	- $S_1→ S_1ab|S_2$,
	- $S_2→a$,
	- is left-linear.
- Both G1 and G2 are regular grammars.

*Example*
The grammar G =({S, A, B}, {a, b}, S, P) with productions
- S →A
- A→aB|λ,
- B →Ab, is not regular. 
b/c it has both $aB$ (right) and $Ab$(left) grammars in it. breaks the [[#^rules|Rules]]. 
Instead The grammar is an example of a **[Linear grammar](#^linear-g)**.

##### EQUIVALENCE OF FINITE AUTOMATA AND REGULAR GRAMMARS
// way easier with examples the theorems just complicate it way too much.
 In order to establish this equivalence, we first prove that given a DFA we can construct an equivalent regular grammar. 
 Then for converse, given a regular grammar, we construct an equivalent generalized finite automaton (GFA).

**Theorem**: If M is a DFA, then L(M) can be generated by a regular grammar G.
*Proof*: Suppose $M = (Q, Σ, δ, q0, F)$ is a DFA. Construct a grammar $G = (V, Σ, S, P)$ by setting $V = Q$ and $S = q_0$ and $P = \{A → aB : B ∈ δ(A, a)\} ∪ \{A → a : δ(A, a) ∈ F\}$. F- final
In addition, if the initial state $q_0∈ F$, then we include S → \lambda in P.
Clearly G is a regular grammar. We claim that L(G) = L(M).

To show $L(G) = L(M)$:
From the construction of G, it is clear that $\lambda∈ L(M)$ if and only if $\lambda∈ L(G)$. Now, for $n \geq 1$,
* If $x = a_1a_2...a_n \in L(M)$, then $\delta(q_0, x) \in F$, meaning there’s a sequence of transitions $q_0 \xrightarrow{a_1} q_1 \xrightarrow{a_2} \dots \xrightarrow{a_n} q_n$, $q_n \in F$. 
  The grammar derives this using:
  $q_0 \Rightarrow a_1 q_1 \Rightarrow a_1a_2 q_2 \Rightarrow \dots \Rightarrow a_1a_2...a_n$,  (describes how the string $x = a_1a_2\dots a_n$ is **derived step-by-step in the regular grammar** $G$ constructed from the DFA.)
  so $x \in L(G)$.

* Conversely, if $y = b_1b_2...b_m \in L(G)$, the derivation uses rules of the form $A \to aB$ followed by $A \to a$.
  This corresponds to transitions in $M$ ending in a final state, so $y \in L(M)$.

Also, $\lambda \in L(G)$ if and only if $q_0 \in F$, which matches $\lambda \in L(M)$.

Thus, $L(G) = L(M)$. // BOOK


We show that the constructed grammar $G = (V, \Sigma, S, P)$ generates exactly the language $L(M)$ accepted by the DFA $M$.
* **Soundness**: Any string generated by $G$ corresponds to a sequence of transitions in $M$ from the start state $q_0$ to some accepting state in $F$, because each production $A \rightarrow aB$ mirrors a transition $\delta(A, a) = B$, and productions $A \rightarrow a$ handle transitions into accepting states.

* **Completeness**: Conversely, for any string accepted by $M$, there exists a sequence of transitions from $q_0$ to an accepting state. Each transition can be simulated by a corresponding production in $G$, producing the same string.

Thus, $G$ generates exactly $L(M)$, and since $G$ is a regular grammar, $L(M)$ is regular.

**Example**:
The regular grammar $G = (V, Σ, P, S)$, where $V = {q_1, q_2, q_3}$, $Σ = \{a, b\}$, $S = q_1$ and P has the following rules
- $q_1 → aq_2 | bq1 | a | b | \lambda$ 
- $q_2 → aq_3 | bq_1 | b$ 
- $q_3 → aq_3 | bq_3$ (trap state)
is equivalent to the DFA:
![[Pasted image 20250523145518.png]]

**Example**:
Consider the DFA given below in figure, Set $V =\{q_0, q_1\}$, $Σ = \{a, b\}$, $S = q_0$ and P has the following production rules:
- $q_0 → aq_1 | bq_0 | a$ 
- $q_1 → aq_0 | bq_1 | b$ 
Now $G = (V, Σ, S, P)$ is a regular grammar that is equivalent to the given DFA. DRAW


**Construction of a Finite Automata M accepting L(G) for a given regular grammar G** 
Let $G = (\{A_0, A_1, .... , A_n\},Σ ,A_0, P)$. We construct a transition system M whose
1. States correspond to variables
2. Initial state corresponds to A0. And
3. Transitions in M correspond to productions in P. As the last production applied in any derivation is of the form $A_i⟶ a$, the corresponding transition terminates at a new state, and this is the unique final state.

We define M as $(\{ q_0,….. ,q_n, q_f\}, Σ, q_0,\{q_f\})$ where \delta is defined as follows:
1. Each production $A_i⟶aA_j$ induces a transition from $q_i$ to $q_j$ with label a,
2. Each production $A_k⟶a$ induces a transition from $q_k$ to $q_f$ with label a.
From the construction, it is clear that the derivation

$$
A_0 \Rightarrow a_1 A_1 \Rightarrow a_1 a_2 A_2 \Rightarrow \dots \Rightarrow a_1 a_2 \dots a_{n-1} A_{n-1} \Rightarrow a_1 a_2 \dots a_n
$$

exists in the grammar $G$ **if and only if** there is a corresponding path in the DFA $M$, starting at the initial state $q_0$ and ending in an accepting state $q_f$, with input string $a_1 a_2 \dots a_n$.
Therefore, we conclude that $L(G) = L(M)$.

EX:
The grammar $G$ has productions: $V_0 \rightarrow aV_1$ and $V_1 \rightarrow abV_0 | b$. 
- $V_0$ is the start variable.

To construct the automaton:
1.  Start with states $V_0$, $V_1$, and a final state $V_f$.
2.  $V_0 \rightarrow aV_1$ creates an edge $V_0 \xrightarrow{a} V_1$.
3.  $V_1 \rightarrow abV_0$ requires an intermediate state (e.g., $V_2$) to create a path $V_1 \xrightarrow{a} V_2 \xrightarrow{b} V_0$.
4.  $V_1 \rightarrow b$ creates an edge $V_1 \xrightarrow{b} V_f$.

The resulting automaton accepts the regular language $L = (aab)^* ab$.
	![[Pasted image 20250527142804.png]]


### PROPERTIES OF REGULAR LANGUAGES

##### CLOSURE PROPERTIES
**Set Theoretic Properties** 
***Complement*** 
*Theorem*: The class of regular languages is closed with respect to complement.
**Proof**:
Let $L$ be a regular language. Then there exists a DFA $M = (Q, \Sigma, \delta, q_0, F)$ such that $L = L(M)$.
Define a new DFA $M' = (Q, \Sigma, \delta, q_0, Q - F)$ - same structure as $M$, but with accepting and non-accepting states swapped.
Then $L(M') = \Sigma^* \setminus L(M) = \overline{L}$, so the complement of a regular language is regular.

***Intersection*** 
*Corollary*: The class of regular languages is closed with respect to intersection.
**Proof**:
Let $L_1$ and $L_2$ be regular. Then $\overline{L_1}$ and $\overline{L_2}$ are regular by the theorem above.
Since regular languages are closed under union, $\overline{L_1} \cup \overline{L_2}$ is regular.
Taking the complement again: (De Morgan's law)
$$
L_1 \cap L_2 = \overline{\overline{L_1} \cup \overline{L_2}}
$$
So $L_1 \cap L_2$ is regular.

***Difference*** 
*Corollary*: The class of regular languages is closed under set difference.
**Proof**:
Let $L_1$ and $L_2$ be regular. Then $\overline{L_2}$ is regular, and by closure under intersection:
$$
L_1 - L_2 = L_1 \cap \overline{L_2}
$$
is also regular.

##### THE PUMPING LEMMA FOR REGULAR LANGUAGES
**Theorem (Pumping Lemma)**:
If $L$ is a regular language, then there exists a constant $n$ such that for every string $w \in L$ with $|w| \geq n$, 
$w$ can be split into $w = xyz$, satisfying:
1. $y \neq \lambda$ (i.e., $y$ is not empty),
2. $|xy| \leq n$,
3. $x y^k z \in L$ for all $k \geq 0$ (i.e., you can "pump" $y$ any number of times and stay in the language).

**Proof (Sketch)**:
Since $L$ is regular, there is a DFA with $n$ states that accepts $L$.
If $w \in L$ and $|w| \geq n$, then by the pigeonhole principle, some state is visited more than once while processing the first $n$ symbols.
This creates a loop that can be repeated any number of times.
We write $w = xyz$, where $y$ is the part that causes the loop.
Pumping $y$ any number of times keeps the string in $L$.
Thus, the lemma holds. 

**Example**:
Prove that the language
$$
L = \{ a^n b^n \mid n \geq 0 \}
$$
is **not** regular.

**Intuition**:
This language contains strings with equal numbers of $a$'s followed by equal numbers of $b$'s (like `aabb`, `aaabbb`). Regular languages can't "count" or enforce such a relationship.

**Proof using the Pumping Lemma**:
Assume, for contradiction, that $L$ is regular.
Then by the **pumping lemma**, there exists a constant $n$ such that for all strings $w \in L$ with $|w| \geq n$, $w$ can be written as $w = xyz$, satisfying:
1. $y \neq \lambda$
2. $|xy| \leq n$
3. $x y^k z \in L$ for all $k \geq 0$ 

**Choose a string**:
Let $w = a^n b^n \in L$. This string has $n$ a's followed by $n$ b's. Since $|w| = 2n \geq n$, the lemma applies.

**Now split** $w = xyz$, with:
* $|xy| \leq n$ ⟹ $xy$ consists **only of a's** (since the first $n$ characters are all a's).
* $y \neq \lambda$ ⟹ $y$ consists of at least one $a$.

**Pump $y$**:
Try $k = 2$:
$$
w' = xyyz = a^{n + |y|} b^n
$$
This string has **more a's than b's**, so $w' \notin L$.

**Contradiction!** The pumped string is not in $L$, so our assumption that $L$ is regular must be false.

**Conclusion**: $L = \{ a^n b^n \mid n \geq 0 \}$ is **not regular**.


# CH-4: Context-Free Languages
Limitations of Regular Descriptions:
- Some simple languages, like $L=\{0_n1_n∣n≥0\}$, cannot be described using regular methods.

**Context-Free Grammars (CFGs)**: are a more powerful way to describe languages, capable of representing recursive structures.
In Programming Language Design CFGs are used to define syntax.
**Context-Free Languages (CFLs)**: The set of languages that can be described by CFGs.
- CFLs include all regular languages and more complex ones.
**Pushdown Automata (PDA)**: Machines that recognize CFLs.

### CONTEXT-FREE GRAMMARS
A context-free grammar is a 4-tuple (V, T, S, P), where
1. V is a finite set called the variables,
2. T is a finite set, disjoint from V, called the terminals,
3. S ∈ V, is the start variable.
4. P is a finite set of rules, with each rule being a variable and a string of variables and terminals, 
Alternatively:
A grammar $G = (V, T, S, P)$ is said to be context-free if all productions in P have the form
$A →x$,
where $A ∈ V$ and $x ∈ (V ∪T)^*$.

A language L is said to be context-free language if and only if there is a context free grammar G such that: $L= L (G)$.

**Example**: consider grammar G1=({A,B},{0,1},A,P),the production P is given by
- A → 0A1
- A → B
- B → 0
We use a grammar to describe a language by generating each string of that language in the following manner: (basic)
1. Write down the start variable. (top-left)
2. Find a variable that is written down and a rule that starts with that variable. Replace the written down variable with the right-hand side of that rule.
3. Repeat step 2 until no variables remain

For example, grammar G1 generates the string 0000111. The sequence of substitutions to obtain a string is called a **derivation**. A derivation of string 0000111 in grammar G1 is 
$A⇒0A1⇒00A11⇒000A111⇒000B111⇒0000111$.
Some experimentation with the grammar G1 shows us that $L(G_1)$ is $\{0^{n+1}1^n| n≥ 0\}$.

***Terminology***:
- "$uAv ⇒ uwv$": One-step derivation by replacing A with w in the context of u and v. we say that $uAv$ yields $uwv$, 
- "$u \xrightarrow{*} v$": Derivation of v from u through zero or more steps. `u derives v`
- Language of a grammar: All strings of terminals derivable from the start symbol:
	- $L(G) = \{w ∈ Σ* | S \xrightarrow{*} w\}$ 

**Example**:
Consider the grammar $G_2 = (\{S\}, \{a, b\}, S, P)$, with productions P
$S →aSa$, $S→bSb$, $S→λ$, is context-free.

A typical derivation in this grammar is `S ⇒aSa⇒aaSaa⇒ aabSbaa ⇒ aabbaa`

This, and similar derivations, make it clear that $L(G2)= \{ww^R: w ∈\{a,b\}^*\}$ is a context free language generated by the grammar.

**Example**:
Consider grammar $G_3 = (\{S\}, \{a, b\}, S, P)$. The set of rules, P is given by $S → aSb | SS | \lambda$.
This grammar generates strings such as $abab$, $aaabbb$, and $aababb$.
- $L(G_3) = \{ w∈ \{a,b\}* : na(w) = nb(w) \}$ 

##### Types of Derivations
**Leftmost and Rightmost Derivations** 
In a grammar that is not linear, a derivation may involve sentential forms with more than one variable. In such cases, we have a choice in the order in which variables are replaced. 
e.g. $G = (\{A, B, S\}, \{a, b\}, S, P)$ with productions
1. $S → AB$,
2. $A →aaA$,
3. $A → \lambda$,
4. $B → Bb$,
5. $B → \lambda$.

This grammar generates the language $L(G) = {a²ⁿbᵐ : n ≥ 0, m ≥ 0}$. That is, any string that consists of an even number of a’s followed by any number of b’s.

Let’s look at two different derivations for the string "$aab$". Even though they use the same set of productions, the order of applying the rules differs.

**First derivation**:
$S\xrightarrow{1}AB\xrightarrow{2}aaAB\xrightarrow{3}aaB\xrightarrow{4}aaBb\xrightarrow{5}aab$.

**Second derivation**:
$S\xrightarrow{1}AB\xrightarrow{4}ABb\xrightarrow{2}aaABb\xrightarrow{5}aaAb\xrightarrow{3}aab$.

Both derivations produce the same final string, "$aab$", and use the same sequence of productions. The difference lies in the order in which the non-terminals A and B are replaced.

To standardize derivations and remove such differences, we can require that variables be replaced in a specific order. If we always replace the **leftmost** variable in each step, the derivation is called a **leftmost derivation**. If we always replace the **rightmost** variable, the derivation is called a **rightmost derivation**.

**Example**:
Consider the grammar with productions $G=(\{A,B,S\},\{a,b\},S,P)$ where P is given by
- $S → aAB$,
- $A →bBb$,
- $B→ A| \lambda$.
Then, the leftmost and rightmost derivations are:
`S ⟹ aAB⟹ abBbB⟹ abAbB ⟹ abbBbbB ⟹ abbbbB ⟹ abbbb`, is a leftmost derivation of the string `abbbb`. 
`S ⟹aAB⟹ aA ⟹abBb⟹ abAb ⟹abbBbb⟹abbbb` is rightmost derivation of the same string `abbbb`. 

**Definition**: A derivation $S\xrightarrow{*}w$ is called a **leftmost derivation** if we apply a production only to the leftmost variable at every step.
**Definition**: A derivation $S\xrightarrow{*}w$ is a **rightmost derivation** if we apply production to the rightmost variable at every step.

##### Derivation Trees
A second way of showing derivations, independent of the order in which productions are used, is by a **derivation(parse) tree**.
A derivation tree is an *ordered tree* in which nodes are labeled with the left sides of productions and in which the children of a node represent its corresponding right sides.
Beginning with the root, labeled with the start symbol and ending in leaves that are terminals, a derivation tree shows how each variable is replaced in the derivation.

**Definition**: Let a grammar $G = (V, T, S, P )$ be a context-free grammar. An ordered tree is a derivation tree for G if and only if it has the following properties.
1. The root is labeled S.
2. Every leaf has a label from $T ∪ \{λ\}$.
3. Every interior vertex (a vertex that is not a leaf) has a label from V. (variable)
4. If a vertex has label A ∈ V, and its children are labeled (from left to right) $a_1, a_2,…, a_n$, then P must contain a production of the form. $A →a_1a_2…..a_n$.
5. A leaf labeled λ has no siblings, that is, a vertex with a child labeled λ can have no other children.

A tree that has properties 3, 4, and 5, but in which 1 does not necessarily hold and in which property 2 is replaced by $V ∪ T ∪ {λ}$, is said to be a **partial derivation tree**.

The string of symbols obtained by reading the leaves of the tree from left to right(depth-first), omitting any λ’s encountered, is said to be the **yield of the tree**.

The yield of a derivation tree is the concatenation of the labels of the leaves without
repetition in the left-to-right ordering.
! [Watch a vid on derivation trees](https://www.youtube.com/watch?v=u4-rpIlV9NI) 

##### DESIGNING CONTEXT-FREE GRAMMARS
CFG's are even trickier to construct than finite automata because we are more accustomed to programming a machine for specific tasks than we are to describing languages with grammars. 

**1. Union of Simpler Languages** 
If a language is a union of simpler CFLs, create CFGs for each and combine them:

Example:
Language: ${0^n1^n| n ≥ 0}∪{1^n0^n| n ≥ 0}$
CFGs:
* $S_1 → 0S_11\ |\ \lambda$ generates ${0^n1^n}$
* $S_2 → 1S_20\ |\ \lambda$ generates ${1^n0^n}$
  Combine:
* $S → S_1\ |\ S_2$

**2. Converting DFA to CFG** 
Regular languages (via DFA) can be converted to CFGs:
* Create variable $P_i$ for each DFA state $q_i$
* If $\delta(q_i, a) = q_j$, add $P_i → aP_j$
* If $q_i$ is accepting, add $P_i → \lambda$
* Use $P_0$ as start variable (where $q_0$ is DFA’s start state)
This ensures the CFG generates the same language.

**3. Matching Linked Substrings** 
Languages like $\{0^n1^n\}$ require remembering counts. Use recursive rules like:
$P → 0P1\ |\ \lambda$ 
This links the number of 0s and 1s correctly.

**4. Recursive Structure** 
Some languages are naturally recursive. Example: **Palindromes over {a, b}**
Properties:
* $\lambda$, $a$, $b$ are palindromes
* If $x$ is a palindrome, then so are $axa$, $bxb$
CFG:
* $S → \lambda\ |\ a\ |\ b\ |\ aSa\ |\ bSb$ 

This grammar handles both even- and odd-length palindromes using recursive construction.

**Example Derivations**
**Example 1: `abba`**
```
S ⇒ aSa         (using S → aSa)
⇒ a bSb a     (inner S → bSb)
  ⇒ a b b a     (inner S → λ)
```
So, `abba ∈ L(G)` 

**Why It Works** 
* Even-length palindromes: built using matching outer symbols (`aSa`, `bSb`) until reaching λ.
* Odd-length palindromes: stop recursion with a single `a` or `b` in the center.

This proves **L = L(G)** — the grammar generates exactly all palindromes over $\{a, b\}$.


##### AMBIGUITY
A grammar is ambiguous if it generates the same string in multiple ways, resulting in different parse trees and interpretations/meanings. This ambiguity can be undesirable in applications like programming languages, where a unique interpretation is needed.

**Example**:
If G is the grammar $S →SbS|a$, show that G is ambiguous?
To prove that G is ambiguous, we have to find a w∈ L(G), which is ambiguous. Consider a string	$w = abababa∈L(G)$. Then we get two derivation trees for w. Thus, G is ambiguous.
	![[Pasted image 20250524104459.png]]
	![[Pasted image 20250524104509.png]]

**Example 2**:
Consider, a grammar $G = ({S}, {a, b, +, *}$, S. P), where P consists of $S→ S+S | S*S | b | a$. show that the grammar is ambiguous?
[Click here to see the answer](# "`a+a*b` has multiple graphs..") 



### SIMPLIFICATION OF CONTEXT-FREE GRAMMARS
In studying Context-Free Grammars (CFGs), we often simplify them by eliminating "useless" symbols and productions that don't contribute to deriving sentences.

For grammar $G = (\{S, A, B, C, E\}, \{a, b, c\}, S, P)$ with $P = \{S \rightarrow AB, A \rightarrow a, B \rightarrow b, B \rightarrow C, E \rightarrow c | \lambda\}$, its language is simply $L(G) = \{ab\}$.

We can create a smaller, equivalent grammar $\hat{G} = (\{S, A, B\}, \{a, b\}, S, \hat{P})$, where $\hat{P} = \{S \rightarrow AB, A \rightarrow a, B \rightarrow b\}$. This $\hat{G}$ still accepts $L(G) = \{ab\}$.

The eliminated symbols and productions were removed because:
* **C** does not derive any terminal string.
* **E** and **c** do not appear in any sentential form derived from S.
* **E → $\lambda$** is a null production (but useless here because E is useless).
* **B → C** is a unit production (replacing one non-terminal with another) where C is useless.

In this section, we outline the construction to eliminate:
1.  Variables not deriving terminal strings.
2.  Symbols not appearing in any sentential form.
3.  Null productions (productions of the form $A \rightarrow \lambda$).
4.  Productions of the form $A \rightarrow B$ (unit productions).

##### CONSTRUCTION OF REDUCED GRAMMARS
If you have a grammar $G$ with a production rule like $A \rightarrow x_1 B x_2$ (where $A$ and $B$ are different variables, and $x_1, x_2$ are strings of symbols), and ($B \rightarrow y_1 | y_2 | \dots | y_n$), then you can simplify the grammar.
**How**:
1.  Remove the production $A \rightarrow x_1 B x_2$.
2.  Add new productions: $A \rightarrow x_1 y_1 x_2 | x_1 y_2 x_2, |..., | x_1 y_n x_2$.

The new grammar, $\hat{G}$, will accept the exact same language as the original grammar $G$. Basically, you're substituting out the intermediate variable $B$ directly into the rules where it's used.

***Example 4.9***:
Consider $G = (\{A, B\} , \{a,b,c\} , A, P)$ with productions
$A \rightarrow a|aaA|abBc$ 
$B \rightarrow abbA|b$ 
*Solution*:
Using the suggested substitution for the variable $B$, we get the new grammar $\hat{G}$ with productions
$A \rightarrow a|aaA|ababbAc|abbc$ 
$B \rightarrow abbA|b$ 
The new grammar $\hat{G}$ is equivalent to $G$. 
The string $aaabbc$ has the derivation
$A \Rightarrow aaA \Rightarrow aaabBc \Rightarrow aaabbc$ in $G$, and the corresponding derivation
$A \Rightarrow aaA \Rightarrow aaabbc$ in $\hat{G}$ 
Notice that, in this case, the variable $B$ and its associated productions are still in the grammar even though they can no longer play a part in any derivation. We will next show how such unnecessary productions can be removed from a grammar.


##### REMOVING USELESS PRODUCTIONS
One invariably wants to remove productions from a grammar that can never take part in any derivation.
For example, in the grammar whose entire production set is
$S \rightarrow aSb| \lambda |A$ 
$A \rightarrow aA$ 
the production $S \rightarrow A$ clearly plays no role, as $A$ cannot be transformed into a terminal string. While $A$ can occur in a string derived from $S$, this can never lead to a sentence. Removing this production leaves the language unaffected and is a simplification by any definition.

***Definition***: Let $G = (V, T, S, P)$ be a context-free grammar. A variable $B \in V$ is said to be useful if and only if there is at least one $w \in L(G)$ such that
$S \xrightarrow* xBy \xrightarrow* w$ 
with $x, y$ in $(V \cup T)^*$. 
In words, a variable is useful if and only if it occurs in at least one derivation. A variable that is not useful is called useless. A production is useless if it involves any useless variable.

**Example**:
A variable can be useless if it cannot derive a terminal string, or if it cannot be reached from the start symbol.
Consider $G=(\{S,A\},\{a,b\},S,P)$ with productions:
$S \rightarrow A$ 
$A \rightarrow aA | \lambda$ 
$B \rightarrow bA$ 
*Solution*:
Variable $B$ is useless because, despite deriving terminal strings, it is unreachable from the start symbol $S$ (i.e., no derivation $S \Rightarrow^* xBy$ exists).
Therefore, $B$ and its production $B \rightarrow bA$ are eliminated.
The new grammar is $\hat{G}=(\{S,A\},\{a\},S,\hat{P})$ with productions:
$S \rightarrow A$ 
$A \rightarrow aA | \lambda$ 

***Theorem***: Let $G = (V, T, S, P)$ be a context-free grammar. Then there exists an equivalent grammar$\hat G = ( \hat V , \hat T,S, \hat P)$ that does not contain any useless variables or productions.
**Proof**: The grammar $\hat G$ can be generated from G by an algorithm consisting of two parts.
Step 1: Eliminate variables that cannot derive terminal strings.
Step 2: Eliminate symbols not appearing in any sentential form (unreachable from the start symbol).

##### REMOVING $\lambda$-PRODUCTIONS
***Definition***: Any production of a context-free grammar of the form  
$A → λ$ 
is called a λ-production. & Any variable A for which the derivation 
$A \xrightarrow{*} λ$ 
is possible is called **nullable**.

A grammar may generate a language not containing λ, yet have some λ-productions or nullable variables. In such cases, the λ-productions can be removed.

**Example**: Consider the grammar
$S \rightarrow aS_1b$ 
$S_1 \rightarrow aS_1b | \lambda$ 
with start variable $S$. 
This grammar generates the $\lambda$-free language $\{a^n b^n : n \geq 1\}$. The $\lambda$-production $S_1 \rightarrow \lambda$ can be removed after adding new productions obtained by substituting $\lambda$ for $S_1$ where it occurs on the right. Doing this we get the grammar
$S \rightarrow aS_1b | ab$ 
$S_1 \rightarrow aS_1b | ab$ 
This new grammar generates the same language as the original one.

**Theorem**: Let G be any context-free grammar with λ not in $L(G)$. Then there exists an equivalent grammar $\hat G$ having no λ-productions.

**Here's how to construct $\hat{G}$**:
1.  **Find all "nullable" variables ($V_N$)**:
    * Start by including any variable $A$ where $A \rightarrow \lambda$ is a production.
    * Repeatedly add any variable $B$ to $V_N$ if all symbols on the right-hand side of a production $B \rightarrow A_1 A_2 \dots A_n$ are already in $V_N$.

2.  **Construct new productions ($\hat{P}$)**:
    * For every existing production $A \rightarrow x_1 x_2 \dots x_m$ (where $m \geq 1$ and each $x_i$ is a variable or terminal): 
        * Add this original production to $\hat{P}$.
        * Also add all possible new productions formed by removing one or more nullable variables (from $V_N$) from the right-hand side.
        * **Exception:** Do NOT add $A \rightarrow \lambda$ if *all* $x_i$ were nullable.

The resulting grammar $\hat{G}$ will generate the exact same language as $G$, but without any $\lambda$-productions.

**Example**:
Find a context-free grammar without $\lambda$-productions equivalent to the grammar defined by
$S \rightarrow ABaC$ 
$A \rightarrow BC$ 
$B \rightarrow b | \lambda$ 
$C \rightarrow D | \lambda$ 
$D \rightarrow d$ 
Solution:
From the first step of the construction in Theorem 4.3, we find that the nullable variables are $A, B, C$. (A b/c both B and C are nullable)
Then, following the second step of the construction, we get
$S \rightarrow ABaC | BaC | AaC | ABa | aC | Aa | Ba | a$ 
$A \rightarrow B | C | BC$ 
$B \rightarrow b$ 
$C \rightarrow D$ 
$D \rightarrow d$ 

##### REMOVING UNIT-PRODUCTIONS
**Definition**: Any production of a context-free grammar of the form 
$A → B$, where 
$A, B ∈ V$, is called a unit-production. To remove unit-productions, we use the substitution rule.

**Theorem**: states that any context-free grammar (CFG) $G$ without $\lambda$-productions can be converted into an equivalent CFG $\hat{G}$ that has **no unit-productions** (rules of the form $A \rightarrow B$).

**Proof Sketch:** 
1.  **Identify Unit-Production Paths:** For each variable $A$, find all variables $B$ such that $A$ can derive $B$ solely through a sequence of unit-productions ($A \Rightarrow^* B$). This can be visualized as finding all reachable variables in a graph where edges exist for each unit-production (e.g., an edge $C \rightarrow D$ if $C \rightarrow D$ is a production).

2.  **Construct $\hat{G}$'s Productions ($\hat{P}$):**
    * Include all original non-unit productions from $G$ into $\hat{P}$.
    * For every pair of variables $A$ and $B$ where $A \xrightarrow{*} B$ (from step 1), add new productions to $\hat{P}$. For each production $B \rightarrow y_1 | y_2 | \dots | y_n$ (where $y_i$ is a string of terminals and/or non-terminals, and $y_i$ is **not** a single variable), add $A \rightarrow y_1 | y_2 | \dots | y_n$ to $\hat{P}$.

This process ensures that if $A$ could derive a string via $B$ (e.g., $A \Rightarrow^* B \Rightarrow \text{string}$), it can now derive that string directly from $A$ without an intermediate unit-production. Since the $y_i$ strings are from non-unit productions of $B$, no new unit-productions are created. The resulting grammar $\hat{G}$ is equivalent to $G$.

**Example**:
Remove all unit-productions from
$S \rightarrow Aa | B$
$B \rightarrow A | bb$
$A \rightarrow b | bc | B$

**Solution:** 
First, we identify all unit-production paths ($A \Rightarrow^* B$) for each variable.
From the dependency graph (or by tracing derivations):
* $S \Rightarrow^* A$ (since $S \rightarrow B \rightarrow A$)
* $S \Rightarrow^* B$ (since $S \rightarrow B$)
* $B \Rightarrow^* A$ (since $B \rightarrow A$)
* $A \Rightarrow^* B$ (since $A \rightarrow B$)

**1. Start with original non-unit productions:**
* $S \rightarrow Aa$
* $B \rightarrow bb$
* $A \rightarrow b$
* $A \rightarrow bc$

**2. Add new rules for each $A \Rightarrow^* B$ path:**
* **For $S \Rightarrow^* A$:**
    Since $A \rightarrow b$ and $A \rightarrow bc$ are non-unit productions with $A$ on the left, add these to $S$:
    $S \rightarrow b$
    $S \rightarrow bc$

* **For $S \Rightarrow^* B$:**
    Since $B \rightarrow bb$ is a non-unit production with $B$ on the left, add this to $S$:
    $S \rightarrow bb$

* **For $B \Rightarrow^* A$:**
    Since $A \rightarrow b$ and $A \rightarrow bc$ are non-unit productions with $A$ on the left, add these to $B$:
    $B \rightarrow b$
    $B \rightarrow bc$

* **For $A \Rightarrow^* B$:**
    Since $B \rightarrow bb$ is a non-unit production with $B$ on the left, add this to $A$:
    $A \rightarrow bb$

**Resulting Grammar (after collecting and removing duplicates):**
$S \rightarrow Aa | b | bc | bb$ 
$A \rightarrow b | bc | bb$ 
$B \rightarrow bb | b | bc$ 

**Note:** After removing unit-productions, some variables (like $B$ in this case, if the grammar started from $S$) and their associated productions might become useless because they can no longer be reached from the start symbol or cannot derive terminal strings. These can be removed in a subsequent simplification step.


### CHOMSKY’S HIERARCHY OF GRAMMARS
According to Chomsky hierarchy, grammars are divided of 4 types:
Type 0 known as unrestricted grammar. - `turing machine` 
Type 1 known as context sensitive grammar. - `linear bound automata` 
Type 2 known as context free grammar. - `pushdown automata` 
Type 3 Regular Grammar - `fininte automata` 

- Type 0 includes all the below ones and so on.


### IMPORTANT NORMAL FORMS
When working with context-free grammars, it is often convenient to have them in simplified form.
##### CHOMSKY NORMAL FORM
Chomsky normal form is useful in giving algorithms for working with context-free grammars.

***Definition***: A context-free grammar is in Chomsky normal form if every rule is of the form
$A → BC$ 
$A → a$ 
where a is any terminal and A, B, and C are any variables.

**Theorem:** Any context-free language is generated by a context-free grammar in Chomsky normal form.

**Proof:** 
We can convert any CFG $G$ into Chomsky Normal Form through several stages, replacing rules that don't fit the form with equivalent ones.

1.  **Add a new start variable:** Introduce a new start variable $S_0$ and the rule $S_0 \rightarrow S$, where $S$ was the original start variable. This ensures the start variable doesn't appear on the right-hand side of any rule.

2.  **Eliminate $\lambda$-rules:** Remove all $\lambda$-rules (e.g., $A \rightarrow \lambda$) where $A$ is not the start variable. For every occurrence of such an $A$ on the right side of a rule (e.g., $R \rightarrow uAv$), add a new rule with that $A$ deleted ($R \rightarrow uv$). This process is repeated until all such $\lambda$-rules are gone.

3.  **Eliminate unit rules:** Remove all unit rules (e.g., $A \rightarrow B$). For every rule $B \rightarrow u$, add the rule $A \rightarrow u$ (unless $A \rightarrow u$ was itself a unit rule just removed). This step is repeated until all unit rules are eliminated.

4.  **Convert remaining rules to proper form:**
    * For rules $A \rightarrow u_1 u_2 \dots u_k$ where $k \geq 3$ and each $u_i$ is a variable or terminal, replace them with a series of rules like $A \rightarrow u_1 A_1$, $A_1 \rightarrow u_2 A_2$, ..., $A_{k-2} \rightarrow u_{k-1}u_k$. The $A_i$'s are new variables.
    * If any $u_i$ in these new rules is a terminal (e.g., $A \rightarrow u_1 A_1$ where $u_1$ is a terminal), replace it with a new variable $U_i$ and add a rule $U_i \rightarrow u_i$.

This process ensures the resulting grammar $\hat{G}$ is equivalent to $G$ and is in Chomsky Normal Form.

Got it! Here's the same content using inline LaTeX format (`$$` for single-line equations):

**Example**:
Let $G$ be the following CFG and convert it to Chomsky normal form by using the conversion procedure just given. The series of grammars presented illustrates the steps in the conversion. 

1. The original CFG $G_6$ is shown on the left. The result of applying the first step to make a new start variable appears on the right.
	$S \rightarrow ASA \mid aB$      $S_0 → S$ 
	                         $S → ASA|aB$ 
	$A \rightarrow B \mid S$              $A→B|S$ 
	$B \rightarrow b \mid \lambda$              $B→b|\lambda$ 
	
2. Remove $\lambda$-rules $B \rightarrow \lambda$,  shown on the right.
	$S_0 \rightarrow S$                          $S_0 \rightarrow S$ 
	$S \rightarrow ASA \mid aB \mid a$         $S→ASA|aB|a|SA|AS|S$ 
	$A \rightarrow B \mid S \mid \lambda$ (added b/c of A→B)              $A→B|S$ 
	$B \rightarrow b$                          $B→b$ 
	
3a. Remove unit rules $S \rightarrow S$, shown on the left, and $S_0 \rightarrow S$, shown on the right.
	$S_0 \rightarrow S$                                            $S_0→ASA|aB|a|SA|AS$ 
	$S \rightarrow ASA \mid aB \mid a \mid SA \mid AS$           $S→ASA|aB|a|SA|AS$
	$A \rightarrow B \mid S$                                       $A→B|S$ 
	$B \rightarrow b$                                              $B→b$ 

3b. Remove unit rules $A \rightarrow B$ and $A \rightarrow S$.
	$S_0 \rightarrow ASA \mid aB \mid a \mid SA \mid AS$           $S_0 → ASA | aB | a | SA | AS$ 
	$S \rightarrow ASA \mid aB \mid a \mid SA \mid AS$            $S → ASA | aB | a | SA | AS$ 
	$A \rightarrow b \mid ASA \mid aB \mid a \mid SA \mid AS$       $A → b | ASA | aB | a | SA | AS$ 
	$B \rightarrow b$                                                $B→b$ 

4. Convert the remaining rules into the proper form by adding additional variables and rules. The final grammar in Chomsky normal form is equivalent to $G$.
   (Actually, the procedure given in Theorem 4.95 produces several variables $U_i$ and several rules $U_i \rightarrow a$. We simplified the resulting grammar by using a single variable $U$ and rule $U \rightarrow a$.)
	$S_0 \rightarrow AA_1 \mid UB \mid a \mid SA \mid AS$ 
	$S \rightarrow AA_1 \mid UB \mid a \mid SA \mid AS$ 
	$A \rightarrow b \mid AA_1 \mid UB \mid a \mid SA \mid AS$ 
	$A_1 \rightarrow SA$ 
	$U \rightarrow a$ 
	$B \rightarrow b$ 
---


##### GREIBACH NORMAL FORM
Here we put restrictions not on the length of the right sides of a production, but on the positions in which terminals and variables can appear.
Arguments justifying `Greibach` normal form are a little complicated and not very transparent.

**Definition**: A context-free grammar is said to be in `Greibach` normal form if all productions have the form
$A \rightarrow ax$,
where $a \in T$ and $x \in V^*$.

**Example**:
Convert the grammar
$S \rightarrow abSb|aa$ into `Greibach` normal form.
*Solution*:
Here we can use a device similar to the one introduced in the construction of Chomsky normal form. We introduce new variables $A$ and $B$ that are essentially synonyms for $a$ and $b$, respectively. Substituting for the terminals with their associated variables leads to the equivalent grammar
$S \rightarrow ABSB| AA$,
$A \rightarrow a$,
$B \rightarrow b$,
which is in `Greibach` normal form.


