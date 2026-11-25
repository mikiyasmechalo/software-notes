---
title: Compiler Design
---
# CH1: Overview
A **Compiler** is a translator that converts the high-level language into the machine language.
- it shows errors to the programmer

A high level language goes through 2 steps
1. it is compiled and translated to *Object program* (low level language)
2. OP is translated to *target program* through the assembler

An **Interpreter** is another common kind of language processor that instead of producing a target program as a translation, an interpreter appears to directly execute the operations specified in the source program on input supplied by the user.

Compiler is much faster than an Interpreter but an Interpreter gives better error diagnostic b/c it executes the source program statement by statement.

Java's **just-in-time compilers**, translate the bytecodes into machine language immediately before they run the intermediate program to process the input.

Other programs than a compiler may be required to create an executable target program.
- **Preprocessor** - finds external modules and expands micros.
- **Linker** - resolves external memory addresses. The code in one file may refer to a location in another file.
- **Loader** - puts together all executable object files into memory for execution.

Compiler is fed the modified source code and usually produces *assembly language* program because it is easier to produce and easier to debug.

### Structure of a Compiler
Two Major Parts: Analysis and Synthesis

1. **Analysis Part**:- breaks up the source code into constituent pieces and imposes grammatical structure on them.
	- then uses this structure to create an intermediate representation of the source program.
	- If the source is either syntactically ill formed or semantically unsound, it provides messages for the user to correct.
	- It also collects information about the source program and stores it in a **Symbol Table**, w/c is passed along with the intermediate to the synthesis part. and is used in all phases.
	
	- *Lexical Analyzer*, *Syntax Analyzer* and *Semantic Analyzer* are Phases in this part.
	
2. **Synthesis Part**:- constructs the desired target program from the intermediate representation and the information in the symbol table.
	- *Intermediate Code Generator*, *Code Generator* and *Code Optimizer* are phases in this part.

### Phases of a Compiler
a compiler operates in phases, each transforms the source code from one representation to another.
- 3 first phases from the analysis operation and the last 3 from the synthesis operation.

The other activities: **Symbol table management** and **error handling** are shown interacting with all 6 phases.
![[Pasted image 20251014115019.png]]

#### Lexical Analysis (Scanning)
- reads the stream of characters making up the source code and groups them into meaningful sequences called **Lexemes**.
- A **Token** describes a pattern of characters having some meaning in the source program. (identifiers, operators, keywords ...)
- For each **lexeme** the lexical analyzer produces as output, a token of the form `<token-name, attribute-value>` is passed on to the subsequent phase: syntax analysis. 
	- Token-name is an abstract symbol (id, op, const, keyword, ...) and attribute-value points to an entry in the symbol table for this token. 
	- Information from the symbol table is needed for semantic analysis and code generation.
	- it puts information about tokens into the symbol table.
- Regular expressions are used to describe tokens.
- A Finite State Automation (DFA) can be used in the implementation of a lexical analyzer.
- `position = initial + rate * 60`. position,=, initial, +, rate, * and 60 are tokens.

#### Syntax Analysis (Parsing)
- creates the syntactic structure (generally a parse tree) of the given program.
- A parse tree describes a syntactic structure.
- The syntax of a language is specified by a *context free grammar (CFG)*.
- A syntax analyzer checks whether a given program satisfies the rules implied by a CFG or not. If it satisfies, it then creates a parse tree for the program.
- Generate CFG for the given parse tree:
	![[Pasted image 20251014124640.png]]

Depending on how the parse tree is created, there are different parsing techniques. These parsing techniques are categorized into two groups:
- Top-Down Parsing,
- Bottom-Up Parsing

**Top-Down Parsing**:
- Construction of the parse tree starts at the root, and proceeds towards the leaves.
- Efficient top-down parsers can be easily constructed by hand.
- e.g. Recursive Predictive Parsing, Non-Recursive Predictive Parsing (LL Parsing).

**Bottom-Up Parsing**:
- Construction of the parse tree starts at the leaves, and proceeds towards the root.
- Normally efficient bottom-up parsers are created with the help of some software tools.
- Bottom-up parsing is also known as *shift-reduce parsing*.

#### Semantic Analysis
- Checks the source program for semantic errors and collects the *type* information (Type Checking) for the code generation. is saved in the syntax tree and symbol table. 
- Semantic analyzer uses the syntax tree and the information in the symbol table to check the source program for semantic consistency with the language definition.
- Normally semantic information cannot be represented by a context-free language used in syntax analyzers.
- Context-free grammars used in the syntax analysis are integrated with attributes (semantic rules).
- The result is a syntax-directed translation and Attribute grammars.

#### Intermediate Code Generation
These intermediate codes are generally machine architecture independent. But the level of intermediate codes is close to the level of machine codes.
```
newval := oldval * fact + 1
->
id1 := id2 * id3 + 1
->
MULT       id2, id3, temp1
ADD temp1, #1, temp2
MOV        temp2, id1
```

#### Code Optimization
The code optimizer optimizes the code produced by the intermediate code generator in the terms of time and space.
```
MULT id2, id3, temp1
ADD temp1, #1, id1
```

#### Code Generation
If the target language is machine code, registers Or memory locations are selected for each of the variables used by the program.
Then, the intermediate instructions are translated into sequences of machine instructions that perform the same task. 
A crucial aspect of code generation is the judicious assignment of registers to hold variables.
- An essential function of a compiler is **Symbol Table Management**. (name, type, scope & number of parameters, method of passing, and return types for functions)

Compiler Construction Tools
- **Parser generators** that automatically produce syntax analyzers from a grammatical description of a programming language
- **Scanner generators** that produce lexical analyzers from a regular-expression description of the tokens of the language
- **Syntax-directed translation engines** that produce collections of routines for walking a parse tree and generating intermediate code
- **Code generator generators** that produce a code a generator form a collection of rules for translating each operation of the intermediate language into the machine language for a target machine
- **Data-flow analysis engines** that facilitate the gathering of information about how values are transmitted from one part of the program to each other part. Data flow analysis is key part of code optimization
- **Compiler-construction** toolkits that provide an integrated set of routines for constructing various phases of a compiler
![[Pasted image 20251014115854.png]]

# CH2: Lexical Analysis
The first phase of a compiler.
It reads a sequence of characters from the source program and produce tokens to be used by the parser.
- Produces tokens by removing whitespace and comments.
- The stream of tokens are sent to the parser for syntax analysis.
- it interacts with the symbol table e.g. when it comes to a lexeme with an identifier.

#### Role of the Lexical Analyzer
- Stripping out *comments* and *whitespaces*
- Correlating *error messages* generated by the compiler with the source program by keeping track of line numbers.
- Expanding macros in some lexical analyzers.
- helps to identify the tokens.


**Tokens, Patterns, and Lexemes**
**A token**:
- Is a pair consisting of a token name and an optional attribute value.
- The token name is an abstract symbol representing a kind of lexical unit, e.g., Keywords, operators, identifiers, constants, literals, punctuation symbols 
- The token names are input symbols that the parser processes.

**Lexemes**:
-  sequence of characters (alphanumeric) in a token.
- There are some predefined rules for every lexeme to be identified as a valid token.
- These rules are defined by grammar rules, by means of a pattern.

**A pattern**:
- a description of the form that lexemes of a token may take.
	- e.g. In case of a keyword as a token, the pattern is the sequence of characters that forms the keyword. and it is more complex for others like identifiers.
- In programming languages, keywords, constants, identifiers, strings, numbers, operators and punctuations symbols can be considered as tokens.
- For example:
```
int value = 10;

int (keyword), value (identifier), = (operator), 100 (constant) and ; (symbol)
```


**Attributes of tokens** 
- a lexeme might match more than one pattern. In that case, the scanner(lexical analyzer) must collect and provide additional info about the lexeme to the rest of the phases.
- Ex. both 0 and 1 match the pattern for 'num', but the code generator needs to know w/c number.

Practically, *a token has one attribute*: *a pointer to the symbol table entry* in which the information about the token is kept.
The *symbol table* entry has info about the token like the *lexeme* and the line number in w/c it was first seen.
ex. consider x = y + 2
```
<id, pointer to symbol-table entry for x>
<assign_op, >
<id, pointer to symbol-table entry for y>
<plus_op, >
<num, integer value 2>

// "pointer to s.t" can also be sometimes replaced by the actual value
```


#### Errors
Very few errors are detected by the lexical analyzer.
- a mis-spelling like `wihle` for while *will not* be detected by lexical analyzer.
- but if a certain sequence of characters follows non of the specified patterns the lexical analyzer can detect the error.

Here are examples of common lexical-level error recovery techniques:

| Error Recovery Technique                                                                                                      | Example (Input $\rightarrow$ Corrected Lexeme)                                                                                        |
| :---------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| *skipping* (deleting) successive characters from the remaining input until it finds a well formed token (panic mode recovery) | `int x = 5 @ ^ 10;` $\rightarrow$ Scanner deletes `@ ^` and continues at `10;` (assuming `int`, `=`, `5`, `10`, `;` are tokens).      |
| *deleting* extraneous (unimportant) characters                                                                                | `float x &;` $\rightarrow$ Scanner recognizes `float` then deletes the extraneous `&`. Corrected lexeme: **`float`**                  |
| *inserting* missing characters                                                                                                | `if (x > y {` $\rightarrow$ Scanner inserts a closing parenthesis `)` after `y`. Corrected lexeme: **`if`** followed by **`(x > y)`** |
| *replacing* an incorrect character with a correct one.                                                                        | `int num = 1a;` $\rightarrow$ Scanner replaces the incorrect character `a` with a digit, perhaps **`1`**. Corrected lexeme: **`11`**  |
| *transposing* two adjacent characters                                                                                         | `folat x;` $\rightarrow$ Scanner swaps `o` and `l` to form **`float`**. Corrected lexeme: **`float`**                                 |

#### Specifying and Recognizing Tokens

**Specifying Tokens**
Regular expressions are used to specify the patters of tokens.

*Example*:
letter `-> A|B|C|…|Z|a|b|c|…|z`
digit `-> 0|1|…|9`
identifier `-> letter (letter|digit)*`

**Recognizing tokens**
Done using Transition Diagrams.
- as an intermediate step in the construction of a lexical analysis, we first convert patterns into *transition diagrams*. these have nodes (states) representing a condition during the scanning.


#### Input Buffering
The lexical analyzer scans the input from left to right one character at a time.
It uses two pointers: `begin (bp)` and `forward (fp)` to keep track of the pointer of the input scanned.
- initially both are on the first character of the input string.
- the forward pointer moves ahead to search for the end of the lexeme, a blank space.
- the `fp` will be moved ahead at white space along with `bp` to the next token.

**One Buffer Scheme**:
- only one buffer is used to store the input string.
- The problem with this scheme is that if the lexeme is longer than the buffer, to scan the rest of the lexeme the buffer has to be refilled overwriting the first of the lexeme.

**Two Buffer Scheme**:
- The first and second buffer are scanned alternately.
- When end of the current buffer is reached the other buffer is filled.
- This fixes the problem where the lexeme is longer than length of the buffer then scanning input cannot be scanned completely.
- it is faster in I/O latency b/c it doesn't wait for a refill like the one buffer has to.

- when a space is reached in the scan the lexeme between the begin pointer and the forward pointer is recognized as one token.
- To identify the boundary of the first buffer and 'end of buffer' (`eof`) should be placed at the end of the first buffer. same for the second buffer.
- This `eof` character introduced at the end is called **Sentinel** which is used to identify the end of buffer.


**Revision On Basic Formal Language Theory** 
- Language: Any set of strings over an alphabet $\sum$, and the set of all strings is denoted as $\sum ^*$ 
 
*Grammar*: a mechanism to describe languages. defined by a quadruple 
- $G = (V, T, S, P)$, V- variables, T- Terminals, S-start variables, P-Productions
- Productions are of the form: $x \rightarrow y$ 
	`S => w_1 => w_2 ...... => w_n => w` is the **derivation** of sentence `w`. 
	`S, w_1, .... w_n`, w/c contain variables and terminals are called "**Sentential Forms** of the derivation"

**Deterministic Automata**: $M = (Q, \sum, \delta, q_0, F)$ 
- Q - internal States, $\sum$ - Input alphabet, $\delta$ : $Q \times \sum \rightarrow Q$ - transition function, $q_0 \in \sum$ - Initial states, $F \subset Q$ - Final States

**Regular Expression**
designed to represent regular languages with a mathematical tool, a tool built from a set of primitives and operations.
This representation involves a combination of strings of symbols from some alphabet S, parentheses and the operators +, ×, and * . 
regular expression guide:
- *Zero or more*: `a*` → any number of a’s; `(ab)*` → any number of ab's
- *One or more*: `aa*` → at least one a; `ab(ab)*` → at least one "ab" 
- *Zero or one*: `(a + λ)` → optional a 
- *Any string*: `(a + b + c)*` → any combo of a, b, c
- *Nonempty string*: `(a + b + c)(a + b + c)*` 
- *No 'a' allowed*: `(b + c)*` 
- *Exactly one 'a'*: `(b + c)*a(b + c)*`




# CH3: Syntax Analysis

**Syntax Analyzer (Parser)**
Syntax Analyzer creates the syntactic structure of the given source program.
Syntax is described using a context free grammar (CFG). we will use Backus-Naur Form (BNF) or Chomsky's Normal Form (CNF) notations in the description of CFGs.
- if the program satisfies the grammars, the parser creates the parse tree. otherwise it gives error.

Parser works on a stream of tokens passed from the lexical analysis. it outputs parse tree.

Two groups of parsers:
- *Top-Down Parser*: parse tree created top to bottom, starting from root.
- *Bottom-Up Parser*: parse tree created bottom to top, starting from leaves.

both scan the input left to right one token at a time.

Efficient top-down and bottom-up parsers can be implemented only for sub-classes of context-free grammars.
- LL for top-down parsing
- RL for bottom-up parsing
Why Only Sub-Classes? this is because general CFGs may:
- Be ambiguous (multiple parse trees for the same string)
- Require backtracking or lookahead beyond one symbol
- Contain left recursion or complex nesting
The notation:
- LL = Left-to-right scan, Leftmost derivation (used in top-down parsing)
- RL = Rightmost derivation in reverse (used in bottom-up parsing)

**The Role of a Parser**
It takes tokens and verifies that the string of token names can be generated by the source programming language.
The Parser should report any syntax errors and recover from common errors.
It constructs a parse tree and passes it to the rest of program.

**Syntax Error Handling**
Goals of the error handler:
- reports should be clear and accurate
- compiler should recover and detect other errors
- it shouldn't slow down the entire compilation process significantly

a report should include:
- the place where the error is detected (line number)
- type of error (if possible)

Four main strategies in error handling:
- *Panic mode recovery*: discard all tokens until a synchronization token (';', '}') is found.
-  *Phrase level recovery*: the parser makes a local correction so that it can continue to parse the rest of the input. (inserting, deleting, or replacing a small number of tokens)
- *Error productions*: augment the grammar to capture the most common errors that programmers make. (Helps provide more meaningful error messages.)
- *Global correction*: makes as few changes as possible in the program so that a globally *least cost* correction program is obtained.


## Parser
![[Pasted image 20251028110830.png]]

### Top-Down Parsing
- Generates PT by expanding the non-terminals. (from start symbol - terminals)
- We create the nodes of the parse tree in preorder or depth-first.
- Equivalently it can be seen as finding a *leftmost derivation* for an input string.

At each step we determine the production to be applied for a non-terminal, A. and we "match" the terminal symbols in the production body with the input string.

Is classified into 2 types: *full backtracking parser* and *Non-backtracking parser*.

*Example TDP*
The sequence of parse trees for the input **id + id * id** 
With productions:
$E \rightarrow TE'$ 
$E'\rightarrow +TE' ~|~ \epsilon$ 
$T\rightarrow FT'$ 
$T'\rightarrow *FT' ~|~ \epsilon$ 
$F\rightarrow(~E~)~ | ~id$ 

![[Pasted image 20260103090103.png]]
*id + id \* id* 

**Recursive Descent Parsing** 
- an attempt to find leftmost derivation for an input string.
- may require backtracking to find the correct A-production to be applied.
- also known as *Brute force parser* or *with backtracking parser*.
```
void A() {
	// choose an A-production, A-> X1, X2, ... Xk;
	for (i=1 to k) {
		if (Xi is non-terminal)
			call procedure Xi();
		else if (Xi equals the current input symbol a)
			advance the input to the next symbol
		else if
			/* an error has occured */;
	}
}
```

*Recursive Descent Parsing Steps:*
1. Start from the grammar's start symbol. 
2. Use recursive functions for each non-terminal.  (expand)
3. Match terminals with input tokens. 
4. Backtrack if needed. (if no match) 
5. Build the parse tree. 
6. Accept if input is fully parsed; else reject.


**Non-Recursive Descent Parsing** (LL(1))
- aka *predictive* parser, without backtracking parser or dynamic parser.
- uses a parsing table to generate the parse tree instead instead of backtracking.
- chooses the correct A-production by *looking ahead* at the fixed number of symbols.
- L (left->right scanning) L (left-most derivation) 1 (1 character lookahead) 


**FIRST and FOLLOW** 
During top-down and bottom-up parsing, FIRST and FOLLOW allow us to choose which production to apply, based on the next input symbol.

*FIRST*
`FIRST(X)` for a grammar symbol X is the *set* of terminals that begin the strings derivable from X.
Rules:
1. if x is a terminal then `FIRST(X) = {'x'}` 
2. if $X \rightarrow \epsilon$, is a production rule then add $\epsilon$ to `FIRST(X)`
3. If $X \rightarrow Y1, Y2, Y3 ... Yn$, is a production,
	1. `FIRST(X) = FIRST(Y1)` 
	2. If `FIRST(Y1)` contains $\epsilon$ then `FIRST(X) = { FIRST(Y1) - \epsilon} U { FIRST(Y2)}`
	3. If `FIRST(Yi)` contains $\epsilon$ for all i=1 to n, then add $\epsilon$ to `FIRST(X)`.

Example:
```
E -> TE'
E' -> +TE' | ϵ
T -> FT'
T' -> *FT' | ϵ
F -> (E) | id

we start evaluation for FIRST from the bottom productions
FIRST(F) = { (, id }
FIRST(T') = { *, ϵ }
FIRST(T) = { (, id }
FIRST(E') = { +, ϵ }
FIRST(E) = { (, id }
```


Example 2:
```
S -> ACB | Cbb | Ba 
A -> da | BC 
B -> g | Є 
C -> h | Є

we start evaluation for FIRST from the bottom productions
FIRST(C) = { h, Є }
FIRST(B) = { g, Є }
FIRST(A) = { d, g, h, Є }
FIRST(S) = { d, g, h, Є }
```


*FOLLOW*
`Follow(X)` to be the set of terminals that can appear immediately to the right of Non-Terminal X in some sentential form.
Rules:
1. `FOLLOW(S) = { $ }`   Where `S` is the start symbol.
2. If `A → pBq` is a production:  
   Then everything in `FIRST(q)` except `ε` is in `FOLLOW(B)`.
3. If `A → pB` is a production:
   Then everything in `FOLLOW(A)` is in `FOLLOW(B)`.
4. If `A → pBq` is a production and `FIRST(q)` contains `ε`:
   Then `FOLLOW(B)` contains `\{ FIRST(q) – ε } ∪ FOLLOW(A)`.

> [!note]
>Before calculating the FIRST and FOLLOW functions eliminate Left Recursion from the grammar if present.

Example:
```
E -> TE'
E' -> +T E'|Є 
T -> F T' 
T' -> *F T' | Є 
F -> (E) | id
-----------------------
we start from the first production
FOLLOW(E) = FIRST(')')) from (E), = { $, ) }
FOLLOW(E') = FOLLOW(E) from TE' = { $, ) }
FOLLOW(T) = {FIRST(E) - Є } U (FIRST(E)) from 1 and 2, = { +, $, ) }
FOLLOW(T') = FOLLOW(T) from FT' = { +, $, ) }
FOLLOW(F) = {FIRST(T') - Є} U FOLLOW(T) from FT' = { *, +, $, ) }
```

Example 2:
```
S -> Bb | Cd
A -> Ba | Є
C -> cC | Є


FOLLOW(S) =	{ $ }
FOLLOW(B) =	{ b, a }
FOLLOW(C) =	{ d }
FOLLOW(A) =	∅
```

**Predictive Parsing Table (LL(1))**
A non-recursive predictive parser can be built by maintaining a stack explicitly, rather implicitly via recursive calls(inputs).
- *Buffer* contains string to be parsed followed by $ (the right end marker)
- *Stack* contains a sequence of grammar symbols with $ at the bottom.
The parsing table is a two dimensional array $M[X, a]$ where X is a nonterminal of the grammar and a is a terminal or $
**Steps to construct the table:**
- For each production $(A \to \alpha)$:  
  - Put $(A \to \alpha)$ in $(M[A, a])$ for all $(a \in \text {FIRST}(\alpha))$.  
  - If $( \varepsilon \in FIRST(\alpha))$, then for all $(b \in FOLLOW(A))$, put $(A \to \varepsilon)$ in $(M[A, b])$.  
  - If no rule applies, mark the entry as **error**.

**Example Grammar:**
```
E  → T E'
E' → + T E' | ε
T  → F T'
T' → * F T' | ε
F  → (E) | id
```

**FIRST sets:**  
- FIRST(E) = { (, id }  
- FIRST(E') = { +, ε }  
- FIRST(T) = { (, id }  
- FIRST(T') = { \*, ε }  
- FIRST(F) = { (, id }

**FOLLOW sets:**  
- FOLLOW(E) = { ), $ }  
- FOLLOW(E') = { ), $ }  
- FOLLOW(T) = { +, ), $ }  
- FOLLOW(T') = { +, ), $ }  
- FOLLOW(F) = { \*, +, ), $ }

**Predictive Parsing Table:**

| Non-Terminal | id        | (         | )        | +            | *            | $        |
|--------------|-----------|-----------|----------|--------------|--------------|----------|
| **E**        | E → T E'  | E → T E'  |          |              |              |          |
| **E'**       |           |           | E' → ε   | E' → + T E'  |              | E' → ε   |
| **T**        | T → F T'  | T → F T'  |          |              |              |          |
| **T'**       |           |           | T' → ε   | T' → ε       | T' → * F T'  | T' → ε   |
| **F**        | F → id    | F → (E)   |          |              |              |          |
Parsing trace for `id + id * id`

| Matched            | Stack | Input | Action |
|--------------------|-------|-------|--------|
|                    | <div align="right">E$</div> | <div align="right">id + id * id$</div> | output E → T E' |
| id                 | <div align="right">T E'$</div> | <div align="right">id + id * id$</div> | output T → F T' |
| id                 | <div align="right">F T' E'$</div> | <div align="right">id + id * id$</div> | output F → id |
| id                 | <div align="right">id T' E'$</div> | <div align="right">+ id * id$</div> | match id |
| id                 | <div align="right">T' E'$</div> | <div align="right">+ id * id$</div> | output T' → ε |
| id                 | <div align="right">E'$</div> | <div align="right">+ id * id$</div> | output E' → + T E' |
| id +               | <div align="right">T E'$</div> | <div align="right">id * id$</div> | match + |
| id + id            | <div align="right">F T' E'$</div> | <div align="right">* id$</div> | output T → F T' |
| id + id            | <div align="right">id T' E'$</div> | <div align="right">* id$</div> | output F → id |
| id + id id         | <div align="right">T' E'$</div> | <div align="right">* id$</div> | match id |
| id + id id *       | <div align="right">* F T' E'$</div> | <div align="right">id$</div> | output T' → * F T' |
| id + id id *       | <div align="right">F T' E'$</div> | <div align="right">id$</div> | match * |
| id + id id * id    | <div align="right">id T' E'$</div> | <div align="right">$</div> | match id |
| id + id id * id    | <div align="right">T' E'$</div> | <div align="right">$</div> | output F → id |
| id + id id * id    | <div align="right">E'$</div> | <div align="right">$</div> | output T' → ε |
| id + id id * id    | <div align="right">$</div> | <div align="right">$</div> | output E' → ε |


### Bottom-Up Parsing
Construction of a parse tree begins at the leaves and works up towards the root.
We reduce the input string w to the start symbol of grammar by tracing out the rightmost derivations of w in reverse.
We start from a sentence and then apply production rules in reverse manner in order to reach the start symbol.

Also known as **Shift-reduce parsing**.
They don't need left factored grammars (can have left-recursion)

BUP has 2 kinds of main actions: **Shift** and **Reduce**
2 non-main actions: *Accept* and *Reject*

2 Data structures are used:  a *stack* to hold the grammar and an *input (buffer)* to hold the string.
- **shift** pushes an the current symbol from the buffer to the stack.
- **reduce** replaces symbols with non-terminals. 

**Example**
Construct a parsing table for the input string `a1-(a2+a3)$` using the grammar:
- S → S + S 
- S → S - S 
- S → (S) 
- S → a 

*Parsing Table*:

| **Step** | **Stack**  | **Input**                            | **Action**       |
| -------- | ---------- | ------------------------------------ | ---------------- |
| 1        | `$`        | <div align="right">a1-(a2+a3)$</div> | Shift `a1`       |
| 2        | `$a1`      | <div align="right">-(a2+a3)$</div>   | Reduce `a1 → S`  |
| 3        | `$S`       | <div align="right">-(a2+a3)$</div>   | Shift `-`        |
| 4        | `$S-`      | <div align="right">(a2+a3)$</div>    | Shift `(`        |
| 5        | `$S-(`     | <div align="right">a2+a3)$</div>     | Shift `a2`       |
| 6        | `$S-(a2`   | <div align="right">+a3)$</div>       | Reduce `a2 → S`  |
| 7        | `$S-(S`    | <div align="right">+a3)$</div>       | Shift `+`        |
| 8        | `$S-(S+`   | <div align="right">a3)$</div>        | Shift `a3`       |
| 9        | `$S-(S+a3` | <div align="right">)$</div>          | Reduce `a3 → S`  |
| 10       | `$S-(S+S`  | <div align="right">)$</div>          | Shift `)`        |
| 11       | `$S-(S+S)` | <div align="right">$</div>           | Reduce `S+S → S` |
| 12       | `$S-(S)`   | <div align="right">$</div>           | Reduce `(S) → S` |
| 13       | `$S-S`     | <div align="right">$</div>           | Reduce `S-S → S` |
| 14       | `$S`       | <div align="right">$</div>           | Accept           |


#### LR(K) Parser
LR parsing is one type of bottom up parsing. It is used to parse the large class of grammars.

- L : left-to-right scanning of inputs.
- R : constructing right most derivation in reverse
- K : number of input symbols in the look ahead.

LR is divided into 4 parts: LR(0), SLR(1), LALR(1), CLR(1)

**LR Algorithm** 
- use 4 things: stack, input, output and parsing table. Parsing table is d/t in d/t LR parsers.

Parsing table is a 2D array containing 2 parts: *Action part* and *Go To Part* 
- An LR parser makes shift-reduce decisions by maintaining states to keep track of where we are in a parse.
- We need two functions: `Closure()` and `Goto()` 

Steps in LR parsing 
1. For the given input write context free grammar
2. Check the ambiguity of the grammar
3. Add augment production of the given grammar
	- adding a new start rule to the grammar so the parser knows when to stop.
4. Create canonical collection of LR(0) items.
5. Draw the data flow diagram (DFD)
6. Contract LR parsing table
7. Simulate the LR Parsing Algorithm using stack, input and parsing table.


##### LR(0) Parsers
**Canonical Collection of LR(0) items** 
An *LR(0) item* is a production `G` with dot at some position on the right side of the production.
- useful to indicate how much of the input has been processed until a given point.
- in LR(0), we place the reduce node in the entire row.

e.g. for $A \rightarrow XY$, we have the LR(0) items
- $A \rightarrow .XY$ 
- $A \rightarrow X.Y$ 
- $A \rightarrow XY.$ 

The production $A \rightarrow \epsilon$ generates only one item $A \rightarrow ~.\epsilon$ 

E.g. 
- $S\rightarrow AA$ 
- $A\rightarrow aA\ |\ b$ 

1. **Augment Production**
	- $S' \rightarrow S$ 
	- $S \rightarrow AA\ (r1)$ 
	- $A \rightarrow aA\ \text{(r2)}\ |\ b\text{ (r3)}$ 
2. **DFD diagram,** 
	![[Pasted image 20251202140044.png]]

3. **LR(0) Table** 
If a state is going to some other state on a terminal then it correspond to a `shift move`.
If a state is going to some other state on a variable(non-terminal) then it correspond to `go to` move.
If a state contain the final item in the particular row then write the reduce node completely.

| States |     | Action |        | Go to |     |
| ------ | --- | ------ | ------ | ----- | --- |
|        | a   | b      | $      | A     | S   |
| I₀     | S3  | S4     |        | 2     | 1   |
| I₁     |     |        | accept |       |     |
| I₂     | S3  | S4     |        |       | 5   |
| I₃     | S3  | S4     |        |       | 6   |
| I₄     | r3  | r3     | r3     |       |     |
| I₅     | r1  | r1     | r1     |       |     |
| I₆     | r2  | r2     | r2     |       |     |

The table has two main parts:
- **Action** (for terminals: `a`, `b`, `$`)
- **Go to** (for non-terminals: `A`, `S`)

*Row-by-Row Breakdown*

| State  | Meaning                                                                                                                                                                                                     |
| :----- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **I₀** | Initial state. <br> - **Shift 'a'**: Go to state I₃. <br> - **Shift 'b'**: Go to state I₄. <br> - **After reducing to 'A'**: Go to state I₂. <br> - **After reducing to 'S'**: Go to state I₁.              |
| **I₁** | Contains the item `S' → S•`. This is the **accept state**, indicating the input has been successfully parsed.                                                                                               |
| **I₂** | After parsing one `A`, the parser expects another `A`. <br> - **Shift 'a'**: Go to state I₃. <br> - **Shift 'b'**: Go to state I₄. <br> - **After reducing to 'S' (likely from `AA → S`)**: Go to state I₅. |
| **I₃** | After seeing 'a', the parser expects an `A`. <br> - **Shift 'a'**: Go to state I₃. <br> - **Shift 'b'**: Go to state I₄. <br> - **After reducing to 'S' (likely from `aA → A`)**: Go to state I₆.           |
| **I₄** | Contains the item `A → b•`. The parser has recognized `b` and is ready to **reduce** it to `A` using Rule 3 (`A → b`) for all lookahead terminals.                                                          |
| **I₅** | Contains the item `S → AA•`. The parser has recognized `AA` and is ready to **reduce** it to `S` using Rule 1 (`S → AA`) for all lookahead terminals.                                                       |
| **I₆** | Contains the item `A → aA•`. The parser has recognized `aA` and is ready to **reduce** it to `A` using Rule 2 (`A → aA`) for all lookahead terminals.                                                       |


| Symbol           | Meaning                                      |
| ---------------- | -------------------------------------------- |
| `S3`, `S4`       | **Shift** and go to state 3 or 4             |
| `r1`, `r2`, `r3` | **Reduce** using rule 1, 2, or 3             |
| `accept`         | Parsing is complete                          |
| Numbers in Go to | **Transition** to next state after reduction |

4. **Simulate the LR Parsing** 
assume the input is "`aabb`"

| **Stack** | **Symbols** | **Input** | **Action**             |
| --------- | ----------- | --------- | ---------------------- |
| `0`       | `$`         | `aabb$`   | Shift → state 3        |
| `0 3`     | `$a`        | `abb$`    | Shift → state 3        |
| `0 3 3`   | `$aa`       | `bb$`     | Shift → state 3        |
| `0 3 3 4` | `$aab`      | `b$`      | Reduce by `A → b`      |
| `0 3 3`   | `$aaA`      | `b$`      | Go to → state 6 on `A` |
| `0 3 3 6` | `$aaA`      | `b$`      | Reduce by `A → aA`     |
| `0 3`     | `$aA`       | `b$`      | Go to → state 6 on `A` |
| `0 3 6`   | `$aA`       | `b$`      | Reduce by `A → aA`     |
| `0`       | `$A`        | `b$`      | Go to → state 2 on `A` |
| `0 2`     | `$A`        | `b$`      | Shift → state 4        |
| `0 2 4`   | `$Ab`       | `$`       | Reduce by `A → b`      |
| `0 2`     | `$AA`       | `$`       | Go to → state 5 on `A` |
| `0 2 5`   | `$AA`       | `$`       | Reduce by `S → AA`     |
| `0`       | `$S`        | `$`       | Go to → state 1 on `S` |
| `0 1`     | `$S`        | `$`       | **Accept**             |


Example 2:
1. Grammar and augmentation

- **Productions:**
  - S → (L) | b
  - L → L, S | S
- **Augmented grammar:**
  - S' → S
  - S → (L)
  - S → b
  - L → L, S
  - L → S


2. Canonical LR(0) items

I0 — closure(S' → •S)
- **Core items:**
  - S' → •S
  - S → •(L)
  - S → •b
- **Transitions:**
  - **On S:** I1
  - **On ‘(’:** I2
  - **On ‘b’:** I3

I1 — closure(S' → S•)
- **Items:**
  - S' → S•
- **Meaning:** Accept when input is fully consumed.

I3 — closure(S → b•)
- **Items:**
  - S → b•
- **Meaning:** Reduce by S → b.

I2 — closure(S → (•L))
- **Core items:**
  - S → (•L)
- **Closure on L:**
  - L → •L, S
  - L → •S
- **Closure on S (from L → •S):**
  - S → •(L)
  - S → •b
- **Transitions:**
  - **On L:** I4
  - **On S:** I7
  - **On ‘(’:** I2 (left-recursive loop via S → •(L))
  - **On ‘b’:** I3

I7 — closure(L → S•)
- **Items:**
  - L → S•
- **Meaning:** Reduce by L → S.

I4 — closure(S → (L•))
- **Items:**
  - S → (L•)
- **Transitions:**
  - **On ‘)’:** I5

I5 — closure(S → (L)•)
- **Items:**
  - S → (L)•
- **Meaning:** Reduce by S → (L).

I8 — closure(L → L•, S)
- **Items:**
  - L → L•, S
- **Transitions:**
  - **On ‘,’:** I9

I9 — closure(L → L, •S)
- **Core items:**
  - L → L, •S
- **Closure on S:**
  - S → •(L)
  - S → •b
- **Transitions:**
  - **On ‘(’:** I2
  - **On ‘b’:** I3
  - **On S:** I10

I10 — closure(L → L, S•)
- **Items:**
  - L → L, S•
- **Meaning:** Reduce by L → L, S.

> [!Note]
> I8 is reached from I2 on L (besides I4), due to L → •L, S creating a core with dot after L; many texts merge these via GOTO(I2, L) to a single state containing both L → L•, S and S → (L•). Shown separated here for clarity; depending on construction, I4 may also include L → L•, S.

Data flow diagram (state transitions) (draft)

- **I0**
  - **‘(’ → I2**
  - **‘b’ → I3**
  - **S → I1**
- **I2**
  - **L → I4 (and/or I8)** 
  - **S → I7**
  - **‘(’ → I2**
  - **‘b’ → I3**
- **I4**
  - **‘)’ → I5**
- **I9**
  - **‘(’ → I2**
  - **‘b’ → I3**
  - **S → I10**

> **Accept:** I1 on input ‘$’.  
> **Reductions:** I3: S → b; I7: L → S; I10: L → L, S; I5: S → (L).

---
LR(0) parsing table

| State | Action: ( | Action: ) | Action: , | Action: b | Action: $ | GOTO L | GOTO S |
| ----: | --------- | --------- | --------- | --------- | --------- | ------ | ------ |
|    I0 | S2        |           |           | S3        |           |        | 1      |
|    I1 |           |           |           |           | accept    |        |        |
|    I2 | S2        |           |           | S3        |           | 4      | 7      |
|    I3 | r(S→b)    | r(S→b)    | r(S→b)    | r(S→b)    | r(S→b)    |        |        |
|    I4 |           | S5        |           |           |           |        |        |
|    I5 | r(S→(L))  | r(S→(L))  | r(S→(L))  | r(S→(L))  | r(S→(L))  |        |        |
|    I7 | r(L→S)    | r(L→S)    | r(L→S)    | r(L→S)    | r(L→S)    |        |        |
|    I8 |           |           | S9        |           |           |        |        |
|    I9 | S2        |           |           | S3        |           |        | 10     |
|   I10 | r(L→L,S)  | r(L→L,S)  | r(L→L,S)  | r(L→L,S)  | r(L→L,S)  |        |        |

*Example* parse for input `(b, b)$` 

| **Step** | **Stack (states)** | **Symbols** | **Input** | **Action**       |
| -------: | ------------------ | ----------- | --------- | ---------------- |
|        1 | 0                  | $           | (b,b)$    | Shift ‘(’ → S2   |
|        2 | 0 2                | $(          | b,b)$     | Shift ‘b’ → S3   |
|        3 | 0 2 3              | $(b         | ,b)$      | Reduce S → b     |
|        4 | 0 2                | $(S         | ,b)$      | GOTO(I2, S) = 7  |
|        5 | 0 2 7              | $(S         | ,b)$      | Reduce L → S     |
|        6 | 0 2                | $(L         | ,b)$      | GOTO(I2, L) = 4  |
|        7 | 0 2 4              | $(L         | ,b)$      | Shift ‘,’ → S9   |
|        8 | 0 2 4 9            | $(L,        | b)$       | Shift ‘b’ → S3   |
|        9 | 0 2 4 9 3          | $(L,b       | )$        | Reduce S → b     |
|       10 | 0 2 4 9            | $(L,S       | )$        | GOTO(I9, S) = 10 |
|       11 | 0 2 4 9 10         | $(L,S       | )$        | Reduce L → L, S  |
|       12 | 0 2 4              | $(L         | )$        | Shift ‘)’ → S5   |
|       13 | 0 2 4 5            | $(L)        | $         | Reduce S → (L)   |
|       14 | 0                  | $S          | $         | GOTO(I0, S) = 1  |
|       15 | 0 1                | $S          | $         | Accept           |

Quick notes
- **Augmentation:** S' → S gives a clean accept condition in I1.
- **Items:** LR(0) items use only dots; no lookahead. Closures introduce all productions of any nonterminal immediately after a dot.
- **DFD:** Transitions are GOTO(I, X) for grammar symbol X.
- **Table:** ACTION handles terminals via shift/reduce; GOTO handles non-terminals. Reductions in LR(0) appear under all terminals.
- **Parse:** Lists grow by reducing S → b, then L → L, S; wrapping with parentheses reduces via S → (L).


#### SLR(1) 
- refers to "Simple LR" Parsing. same as LR(0) with the only difference in the parsing table.
- In SLR(1) we place reduce move only in the *FOLLLOW of the left hand side*.
- everything else the same as LR(0)

E.g. 
```
S → E
E → E + T | T
T → T * F | F
F → id

step 1 and 2
S` → •E
E → •E + T
E → •T
T → •T * F
T → •F
F → •id
```
step 3.
![[Pasted image 20251223141443.png]]

- I1 contains the final item which drives S → E• and follow (S) = {$}, so action {I1, $} = Accept
- I2 contains the final item which drives E → T• and follow (E) = {+, $}, so action {I2, +} = R2, action {I2, $} = R2
- I3 contains the final item which drives T → F• and follow (T) = {+, \*, $}, so action {I3, +} = R4, action {I3, \*} = R4, action {I3, $} = R4
- I4 contains the final item which drives F → id• and follow (F) = {+, \*, $}, so action {I4, +} = R5, action {I4, \*} = R5, action {I4, $} = R5
- I7 contains the final item which drives E → E + T• and follow (E) = {+, $}, so action {I7, +} = R1,  action {I7, $} = R1
- I8 contains the final item which drives T → T * F• and follow (T) = {+, \*, $}, so action {I8, +} = R3, action {I8, \*} = R3, action {I8, $} = R3.

step 4.

| State |       | AC    | TION      |           | GO  | TO  |     |
| ----: | ----- | ----- | --------- | --------- | --- | --- | --- |
|       | id    | +     | *         | $         | E   | T   | F   |
| $I_0$ | $S_4$ |       |           |           | 1   | 2   | 3   |
| $I_1$ |       | $S_5$ |           | acc       |     |     |     |
| $I_2$ |       | $R_2$ | $S_6$     | $R_2$     |     |     |     |
| $I_3$ |       | $R_4$ | $R_4$<br> | $R_4$<br> |     |     |     |
| $I_4$ |       | $R_5$ | $R_5$<br> | $R_5$<br> |     |     |     |
| $I_5$ | $S_4$ |       |           |           |     | 7   | 3   |
| $I_6$ | $S_4$ |       |           |           |     |     | 8   |
| $I_7$ |       | $R_1$ | $S_6$     | $R_1$     |     |     |     |
| $I_8$ |       | $R_3$ | $R_3$     | $R_3$     |     |     |     |

#### CLR(1) Parsing
CLR refers to canonical look-ahead.
Uses LR(1) items to build the CLR(1) parsing table.
CLR(1) parsing table Produces more number of states compared to SLR(1).
- We place the reduce nodes *only in the look-ahead symbols*.

LR(1) item is a collection of LR(0) items with a lookahead symbol.
- LR(1) = LR(0) + look ahead

The look ahead is used to determine that where we place the final item. The look ahead always add $ symbol for the argument production.

**Example**: 
```
S →AA
A→aA
A→b

step 1
```

![[Pasted image 20251223144156.png]]

Step 4

| State |       | AC    | TION  | GO  | TO  |
| ----: | ----- | ----- | ----- | --- | --- |
|       | a     | b     | $     | S   | A   |
| $I_0$ | $S_3$ | $S_4$ |       |     | 2   |
| $I_1$ |       |       | acc   |     |     |
| $I_2$ | $S_6$ | $S_7$ |       |     | 5   |
| $I_3$ | $S_3$ | $S_4$ |       |     | 8   |
| $I_4$ | $R_3$ | $R_3$ |       |     |     |
| $I_5$ |       |       | $R_1$ |     |     |
| $I_6$ | $S_6$ | $S_7$ |       |     | 9   |
| $I_7$ |       |       | $R_3$ |     |     |
| $I_8$ | $R_2$ | $R_2$ |       |     |     |
| $I_9$ |       |       | $R_2$ |     |     |


#### LALR (1) Parsing
LA - look ahead. - we use LR(1) items.
In LALR(1) parsing, the LR(1) items w/c have same productions but different look ahead are combined to form a single set of items.
LALR (1) parsing is same as the CLR (1) parsing, only difference in the parsing table.

e.g. from the previous example we would just combine same states with d/t lookaheads I8 and I9  `B->bB., $` and `B->bB., b/d` to `B->bB., $/b/d`.

---

# CH4: Semantic Analysis

The plain parse-tree constructed during the syntax analysis phase is not sufficient for a compiler. It describes the structure of the code but lacks the information needed to **evaluate** or **translate** it.

**Semantic Analysis** provides meaning to language constructs. It ensures that the program is not just grammatically correct, but logically sound.

#### 1. Key Tasks in Semantic Analysis

* **Scope Resolution:** Ensuring variables are declared before use and determining which "x" is being referred to in nested blocks.
* **Type Checking:** Verifying that operators are applied to compatible types (e.g., you can't multiply a "string" by a "float").
* **Array-bound Checking:** Ensuring indices are within the declared range of an array.

#### 2. Attribute Grammars

An **Attribute Grammar** is a formal way to provide context-sensitive information to a Context-Free Grammar (CFG). We "decorate" the grammar symbols with **attributes** (variables that hold values).

Attributes are divided into two categories based on how they receive their values:

##### A. Synthesized Attributes

The value of a synthesized attribute at a node is computed from the values of its **children nodes**. It flows **bottom-up**.

* **Example Production:** $S→ABC$ 
* **Semantic Rule:** $S.val=f(A.val,B.val,C.val)$ 
* **Visual:** If  takes values from A, B, and C, the information is "synthesized" upward.

##### B. Inherited Attributes

The value of an inherited attribute at a node is computed from its **parent** and/or **siblings**. It flows **top-down** or **sideways**.

* **Example Production:** $S→ABC$
* **Visual:**  can get values from its parent S or its sibling A.


### 3. SDD vs. SDT

While these terms are often used together, they represent the "what" versus the "how."

| Component          | **Syntax-Directed Definition (SDD)**                | **Syntax-Directed Translation (SDT)**                                  |
| ------------------ | --------------------------------------------------- | ---------------------------------------------------------------------- |
| **Definition**     | A high-level mathematical specification.            | A procedural implementation.                                           |
| **Logic**          | Uses **Semantic Rules** to define attribute values. | Uses **Semantic Actions** (code snippets) inside the grammar.          |
| **Representation** | Generates an **Annotated Parse Tree**.              | Embeds code directly into the production rules.                        |
| **Flexibility**    | Easier to read; hides implementation details.       | More efficient; allows tasks to be done *during* parsing. (ICG, CG...) |
SDT =  Grammar + Semantic rule (Informal Notation)

### 4. Types of SDD/SDT Definitions

Compilers classify these definitions based on how they allow attributes to flow through the tree.

##### 1. S-Attributed Definition

* **Rule:** Uses **only synthesized attributes**.
* **Evaluation:** Bottom-up (from children to parent).
* **Placement:** Semantic actions are always placed at the **very end** of the right-hand side of a production.
* **Example:** $A→BC ~\{A.val=B.val+C.val\}$ 

##### 2. L-Attributed Definition

* **Rule:** Uses both synthesized and inherited attributes, but with a **restriction**.
* **The Restriction:** An inherited attribute at a node can only take values from its **parent** or its **left siblings**. (It cannot look at siblings to its right).
* **Evaluation:** Can be evaluated in a single **Depth-First, Left-to-Right** traversal.
* **Example:** $A→XYZ$
* Y can inherit from A (parent) or X (left sibling).
*  **cannot** inherit from Z (right sibling).

> **Note:** Every **S-attributed** definition is automatically **L-attributed**, but an L-attributed definition is not necessarily S-attributed.


##### 5. Practical Example: Expression Evaluation

Using an SDD to calculate the value of a simple addition:

| Production | Semantic Rule (SDD)    |
| ---------- | ---------------------- |
| $S→E$      | `print(E.val)`         |
| $E→E_1+T$ | $E.val=E_1.val+T.val$ |
| $E→T$      | $E.val=T.val$          |
| $T→T_1∗F$ | $T.val=T_1.val∗F.val$ |
| $T→F$      | $T.val=F.val$          |
| $F→digit$  | $F.val=digit.lexval$   |

**Process:**
1. Construct the **Parse Tree** for an input like `4 * 5 + 6`.
2. Assign **lexical values** to the leaves (digits).
3. Perform a **Bottom-Up** traversal, applying the math at each node to create an **Annotated Parse Tree**.


# CH 5: Symbol Tables and Type Checking
**Symbol Tables** are used by all phases of the compiling process:
- Lexical A. - creates table entries, about tokens.
- Syntax A- adds info like type, scope, dimension, line of ref., use, etc..
- Semantic A. - uses S. table to check for semantic errors (type check, scope resolution, function signatures).
- ICG - Refers to the symbol table for storage allocation (size, type). Adds temporary variables and their attributes.
- Code Optimization - uses S. table for machine dependent optimization.
- Target CG - generates code using address and storage info from the table.

A symbol table is simply a table which can be either linear or a hash table. It maintains an entry for each name in the following format:
`<symbol name,  type,  attribute>` 

**Operations of Symbol Table** 
- *Allocate* - new empty space in the ST.
- *Free* - remove all entries and free storage.
- *Lookup* - search for a name and return pointer to entry.
- *Insert* - insert a name in a ST and return a pointer to entry.
- *Set Attribute* - associate an attribute with a given entry.
- *Get Attribute* - to get an attribute associated with a given entry.

### Implementation of Symbol Table
The symbol table is a data structure used by the compiler to keep track of semantics, variable names, and their attributes.

| Method                 | Data Structure    | Search Time     | Insertion Time  | Pros/Cons                                          |
| ---------------------- | ----------------- | --------------- | --------------- | -------------------------------------------------- |
| **List**               | Array             | $O(n)$          | $O(1)$<br>      | Simple; minimum space; slow lookup.                |
| **Linked List**        | Linked Nodes      | $O(n)$<br>      | $O(1)$<br>      | Easy to expand; slow lookup.                       |
| **Hash Table**         | Array of Pointers | $O(1)$<br>      | $O(1)$<br>      | **Most common**; very fast; complex to implement.  |
| **Binary Search Tree** | Hierarchical Tree | $O(\log n)$<br> | $O(\log n)$<br> | Balanced efficiency for both search and insertion. |


### Type Checking
Type checking is the process of ensuring that the program follows the **semantic rules** of the language (e.g., you can't add a string to an integer).

**1. Static Type Checking (Compile-Time)**
* **When:** Happens during compilation (before the program runs).
* **Key Checks:** * **Type mismatch:** Using an array where a function is expected.
	* **Flow of control:** Ensuring `break` statements are inside loops.
	* **Uniqueness:** Ensuring identifiers/labels are only defined once.
* **Benefit:** Catches errors early; improves runtime performance; determines memory needs.

**2. Dynamic Type Checking (Run-Time)**
* **When:** Happens while the program is executing.
* **Mechanism:** Types are associated with **values** (using type tags), not variables.
* **Benefit:** More flexible and results in shorter code; easier to design but slower at runtime.
**Summary Comparison** 
* **Static (C, Pascal):** Safer, faster execution, rigid.
* **Dynamic (Python, JavaScript):** Flexible, slower execution, easier to write.



# CH 6: Intermediate Code Generation

Intermediate code is generated because the compiler can’t generate machine code directly in one pass.
The intermediate code can be represented in the form of postfix notation, syntax tree, directed acyclic graph, three address codes, Quadruples, and triples.

##### Directed Acyclic Graph
a tool that depicts the structure of basic blocks, helps to see the flow of values flowing among the basic blocks, and offers optimization.
Can be understood:
- Leaf nodes represent identifiers, names or constants.
- Interior nodes represent operators.
- Interior nodes also represent the results of expressions or the identifiers/name where the values are to be stored or assigned.
```
e.g.
t0 = a + b
t1 = t0 + c
d = t0 + t1
```
![[Pasted image 20260103131601.png]] [t0 = a + b]![[Pasted image 20260103131549.png]][t1 = t0 + c]![[Pasted image 20260103131611.png]][d = t0 + t1]


##### Postfix Notation
The operands are found just before the operator.
The postfix notation is a linearized representation of a syntax tree.
Ex. Input: `A+B*C+D` Output: `ABC*+D+` 
	Input: `((A+B) - C * (D/E)) + F`  Output: `AB+CDE/*-F+` 

##### Syntax Notation
- a syntax tree is a condensed form of a parse tree.
- The operator and keyword nodes of the parse tree are moved to their parents and a chain of single productions is replaced by the single link in the syntax tree the internal nodes are operators and child nodes are operands.

To form a syntax tree put parentheses in the expression, this way it’s easy to recognize which operand should come first.

e.g. `X=(a+b*c) / (a-b*c)` ->`X=(a+(b*c)) / (a-(b*c))` 
![[Pasted image 20260101201502.png]]

##### Three address Code
The three address code is a sequence of statements of the form:  `X := Y op Z` 
Where: X, Y, and Z are names, constants or compiler-generated temporaries.

- **Linearized**: It flattens complex syntax trees into a simple sequence.
- **One Operator Limit**: An expression like a = b + c * d must be broken down:$t_1 := c * d$$a := b + t_1$
- **Addresses**: It is named "three-address" because it typically involves three locations: two for operands and one for the result.

**Type of Three-Address Statements** 
- Assignment (binary op) - `a:=b op c` 
- Assignment (unary op) - `x:= op y` Single operand (e.g., minus, logical NOT).
- Copy - `x:=y` 
- Unconditional Jump - `Goto X` 
- Conditional Jump - `if x relop y goto L` 
- Function call
	- Parameter specification - `param x1`
	- Calling the function - `call P, N { P : function & N : no. of parameters }` 
- Indexed Arguments - `x:=y[I]` , `y[I]:=x` 
- Address and Pointer Assignment - `x:=&y` `x:=*y` `*x:=y` 

Examples Represent address three statement-(a * b) + (c + d) – (a + b + c + d)
- Three  Address Code for the given expression i
1) T1 = a * b              | T1 := a * b
2) T2 = `uminus` T1        | T2 := -T1
3) T3 = c + d              | T3 := c + d
4) T4 = T2 + T3           | T4 := T2 + T3
5) T5 = a + b             | T5 := a + b
6) T6 = T3 + T5           | T6 := T3 + T5
7) T7 = T4 – T6           | T7 := T4 – T5


This version organizes the concepts of Intermediate Code Generation (ICG) into a logical flow. I have integrated the specific expression  into each section to show how these representations look in practice.

---

## # CH 6: Intermediate Code Generation

Intermediate code is a machine-independent representation used because a compiler cannot easily generate efficient machine code directly from a source program in one pass. It serves as a bridge between the front-end (analysis) and the back-end (synthesis).

### 1. Graphical Representations

#### A. Syntax Tree (AST)

A syntax tree is a condensed version of a parse tree. It removes unnecessary information like keywords (parentheses) and chains of single productions.

* **Interior Nodes:** Operators.
* **Leaf Nodes:** Operands (identifiers or constants).
![[Pasted image 20260103134452.png]]

#### B. Directed Acyclic Graph (DAG)

A DAG is a more efficient version of a syntax tree. It offers **optimization** by identifying common sub-expressions and pointing multiple "parents" to the same shared "child" node.

* **Leaf nodes:** Represent identifiers or constants.
* **Interior nodes:** Represent operators and the results of expressions.
* **Advantage:** Helps see the flow of values and eliminates redundant computations.
![[Pasted image 20260103134622.png]]
---

### 2. Postfix Notation

Postfix notation (Reverse Polish) is a linearized representation of a syntax tree where operands appear before their operators.

* **Example:** $A+B∗C+D → ABC∗+D+$ 
* **For our expression:** `a + b * c + d * (b + c)`  `a b c * + d b c + * +`

---

### 3. Three-Address Code (3AC)

Three-address code is a sequence of statements in the form: `X := Y op Z`. It is called "three-address" because it typically involves three locations: two operands and one result.

* **Linearized:** It flattens complex structures into simple steps.
* **One Operator Limit:** Complex expressions must be broken down using compiler-generated temporaries (, etc.).

#### Types of Three-Address Statements

* **Assignment:** `x := y op z` (binary) or `x := op y` (unary).
* **Copy:** `x := y`
* **Jumps:** `goto L` (unconditional) or `if x relop y goto L` (conditional).
* **Functions:** `param x`, `call P, n`, `return y`.
* **Pointers:** `x := &y`, `x := *y`, `*x := y`.

---

### 4. Implementation of 3AC (Example: )

The 3AC sequence for our target expression is:
1. $t1:=b∗c$ 
2. $t2:=a+t1$ 
3. $t3:=b+c$ 
4. $t4:=d∗t3$ 
5. $t5:=t2+t4$ 

#### I. Quadruples
Uses four fields: `op`, `arg1`, `arg2`, and `result`. This is easy to rearrange for optimization.

| # | op | arg1 | arg2 | result |
| --- | --- | --- | --- | --- |
| (0) | `*` | `b` | `c` |  |
| (1) | `+` | `a` |  |  |
| (2) | `+` | `b` | `c` |  |
| (3) | `*` | `d` |  |  |
| (4) | `+` |  |  |  |

#### II. Triples
Uses three fields: `op`, `arg1`, and `arg2`. It avoids temporary names by referencing the **position index** (e.g., `(0)`) of a previous instruction.

| # | op | arg1 | arg2 |
| --- | --- | --- | --- |
| (0) | `*` | `b` | `c` |
| (1) | `+` | `a` | (0) |
| (2) | `+` | `b` | `c` |
| (3) | `*` | `d` | (2) |
| (4) | `+` | (1) | (3) |

#### III. Indirect Triples

This uses a separate **execution list** of pointers to the Triples table.
* **Triples Table:** (Same as the Triples table above).
* **Execution List:** `{100, 101, 102, 103, 104}` (where 100 points to Triple #0).
* **Benefit:** Allows the compiler to reorder code for optimization without changing the Triples table itself.




**Syntax Directed Translation into Three Address Code** (not learned)
When the 3 address code is generated (as an attribute of parse tree or by writing the statements in a file as soon as they are generated), it is often necessary to use temporary variables and temporary names.

**The Core Helper Functions** 
* `NewTemp()`: Generates unique temporary names (e.g., $t_1, t_2$).
* `NewLabel()`: Generates unique jump targets(label names) (e.g., $L_1, L_2$).
* `gen()`: The "print" command that emits the actual TAC string (e.g., gen(x, '=', y, '+', z)).
**How SDT Works (Process)** 
1. **Bottom-Up Evaluation**: As the compiler moves up the parse tree, it calls `NewTemp()` for every operation.
2. **Attribute Association**: Each node in the parse tree gets two main attributes:
	* **`.place`**: Stores the name of the variable/temporary holding the value.
	* **`.code`**: Stores the actual sequence of TAC instructions generated for that node.
3. **Code Concatenation**: The `.code` of a parent node is usually the `.code` of its children joined together, plus one final `gen()` statement.

**Example: Translating** $x=a+b*c$ 
When the compiler sees this, the SDT logic would look like this:

1. **Step 1**: `t1 = NewTemp()`  `gen(t1, '=', b, '*', c)`
2. **Step 2**: `t2 = NewTemp()`  `gen(t2, '=', a, '+', t1)`
3. **Step 3**: `gen(x, '=', t2)`

**Final Result:**

```text
t1 = b * c
t2 = a + t1
x = t2
```


**Variable Declarations**
When the compiler handles **Declarations** (like `int x;` or `float y;`), it isn't generating math operations; instead, it is organizing memory.

How the compiler manages this process:
**1. Memory Allocation & Offsets**
* **Memory Reservation**: The compiler reserves space in the "static data area" for every variable declared.
* **The Offset Variable**: The compiler tracks a variable called `offset`, which starts at **zero**.
* **Relative Addressing**: It stores the **relative address** (the distance from the start of memory) in the symbol table.
* **Updating Offset**: Every time a variable is added, the `offset` increases by the **width** (size) of that data type.
* *Example:* If an integer is 4 bytes, after declaring one, the offset moves from 0 to 4.

**2. Symbol Table Entry** 
To keep this organized, the compiler uses a specific procedure:
* **`enter(name, type, address)`**: This function creates a record in the symbol table that links the variable's **name** to its **data type** and its calculated **offset address**.

**Summary of the Entire Process (The Workflow)**
1. **Symbol Table:** Holds names, types, and offsets.
2. **Type Checker:** Uses the "type" from the symbol table to ensure operations are valid.
3. **Declarations:** Sets the initial `offset` and uses `enter()` to populate the table.
4. **TAC Generation:** Uses `newtemp()`, `gen()`, and the `place` (offset/name) to write the final intermediate code.
