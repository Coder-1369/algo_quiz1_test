# CMPS323 — Comprehensive Concepts Guide
## Units 1, 2 & 3 — Full Explanation of Every Tested Topic

> This guide covers **every concept** tested across both `STUDY_GUIDE_MCQ.md` (80 questions) and `SUPPLEMENTARY_MCQ.md` (60 questions). No MCQs here — pure teaching. Read this first, then drill the MCQs.

---

## TABLE OF CONTENTS
1. [Unit 1 — Algorithm Efficiency, Analysis & Order](#unit1)
2. [Unit 2 — Divide and Conquer](#unit2)
3. [Unit 3 — Dynamic Programming](#unit3)
4. [Cross-Unit Concepts](#cross-unit)

---

## UNIT 1 — Algorithm Efficiency, Analysis & Order <a name="unit1"></a>

---

### 1.1 — Fundamental Definitions

A **problem** is a general question to be answered. For example: "Sort an array of integers."

A **parameter** is a variable that characterizes the size or structure of a problem instance — typically `n` (the number of elements).

An **instance** is a specific input: e.g., the array `[5, 3, 8, 1]` is an instance of the sorting problem with n = 4.

An **algorithm** is a step-by-step procedure that solves every instance of a problem. Examples:
- Exchange Sort solves the sorting problem
- Sequential Search solves the search problem
- Floyd's algorithm solves the all-pairs shortest path problem

---

### 1.2 — Algorithm Analysis

**Algorithm analysis** is the process of determining the computational resources (time, space) required by an algorithm as a function of its input size n.

**Why input size?** Because we want to predict performance as the data grows — not just for a single fixed test case.

The goal is to find a function T(n) that counts the number of **basic operations** executed for an input of size n.

---

### 1.3 — Basic Operation

The **basic operation** is the most frequently executed and most costly step inside the algorithm — typically the operation inside the **innermost loop**.

| Algorithm | Basic Operation |
|-----------|----------------|
| Sequential Search | Comparison: `x == A[i]` |
| Exchange Sort | Comparison: `A[i] > A[j]` |
| Matrix Multiplication | Multiplication: `A[i][k] * B[k][j]` |
| Binary Search | Comparison: `x == A[mid]` |
| Merge Sort | Comparison during merge |
| Quick Sort | Comparison during partition |

> **Key rule:** The basic operation is always in the innermost loop. Counting it gives T(n).

---

### 1.4 — Time Complexity: T(n), W(n), B(n), A(n)

For algorithms whose number of steps **depends on the values** of the input (not just the size), we distinguish cases:

| Symbol | Meaning |
|--------|---------|
| **T(n)** | Every-case complexity — same for all inputs of size n |
| **W(n)** | Worst-case — maximum operations over all inputs of size n |
| **B(n)** | Best-case — minimum operations over all inputs of size n |
| **A(n)** | Average-case — expected operations over all inputs of size n |

**Example — Sequential Search:**
- Worst case W(n) = n (key is last or not found)
- Best case B(n) = 1 (key is first element)
- Average case A(n) ≈ (n+1)/2 (key is equally likely anywhere)

---

### 1.5 — Every-Case Complexity

An algorithm has **every-case** complexity when T(n) is the same for every input of size n. Formally: W(n) = B(n) = A(n) = T(n).

**Algorithms with every-case complexity:**
- **Add Array Members** — always sums exactly n elements → T(n) = n
- **Standard Matrix Multiplication** — always does n³ multiplications → T(n) = n³
- **Exchange Sort** — always compares n(n-1)/2 pairs → T(n) = n(n-1)/2 ≈ n²/2
- **Floyd's Algorithm** — always runs 3 nested loops → T(n) = n³

**Algorithms WITHOUT every-case complexity** (case depends on input values):
- Sequential Search (key may be found early)
- Binary Search (key may be at the midpoint)
- Quick Sort (pivot quality varies)

---

### 1.6 — Average-Case Computation (Sequential Search Example)

Assume the key is in the array and equally likely to be at any position 1 through n.

If the key is at position i, the algorithm does i comparisons.

```
A(n) = (1/n) × (1 + 2 + 3 + ... + n)
     = (1/n) × n(n+1)/2
     = (n+1)/2
```

For large n, A(n) ≈ n/2. So on average, Sequential Search is about **twice as fast** as its worst case.

---

### 1.7 — Complexity Categories (Growth Rates)

From **slowest-growing (most efficient)** to **fastest-growing (least efficient)**:

| Category | Notation | Example |
|----------|----------|---------|
| Constant | O(1) | Accessing array element by index |
| Logarithmic | O(log n) | Binary Search |
| Linear | O(n) | Sequential Search, Add Array Members |
| n log n | O(n log n) | Merge Sort, Quick Sort (avg) |
| Quadratic | O(n²) | Exchange Sort, bubble sort |
| Cubic | O(n³) | Matrix Multiplication, Floyd's |
| Exponential | O(2ⁿ) | Naive Fibonacci, naive TSP |
| Factorial | O(n!) | Brute-force TSP |

**Ordering (slowest to fastest growth):**
```
1 < log n < n < n log n < n² < n³ < 2ⁿ < n!
```

> **Exam trap:** "Slower-growing" means MORE efficient (fewer operations). 1 < log n means O(1) is better than O(log n).

---

### 1.8 — Pure-Quadratic vs Complete-Quadratic

| Type | Form | Example |
|------|------|---------|
| **Pure-quadratic** | an² + b (no linear term) | 5n² + 100 |
| **Complete-quadratic** | an² + bn + c (has linear term) | 3n² + 7n + 4, 0.1n² + n + 100 |

Both are O(n²) and Θ(n²) — the distinction is in the exact form, not the asymptotic class.

---

### 1.9 — Big-O Notation

**Informal definition:** g(n) ∈ O(f(n)) means g(n) grows no faster than f(n) (upper bound).

**Formal definition:** g(n) ∈ O(f(n)) if and only if there exist positive constants c and integer N ≥ 0 such that:
```
g(n) ≤ c · f(n)   for all n ≥ N
```

**How to prove:** Find specific values of c and N that satisfy the inequality.

**Example:** Show that 3n² + 7n + 4 ∈ O(n²).

For n ≥ 1:
- 3n² + 7n + 4 ≤ 3n² + 7n² + 4n² = 14n²

So choose c = 14, N = 1. Since 3n² + 7n + 4 ≤ 14n² for all n ≥ 1, we have 3n² + 7n + 4 ∈ O(n²). ✓

**Important:** O(f(n)) is an upper bound, not necessarily tight. n ∈ O(n²) is true, but n ∉ Θ(n²).

---

### 1.10 — Big-Ω Notation

**Informal definition:** g(n) ∈ Ω(f(n)) means g(n) grows at least as fast as f(n) (lower bound).

**Formal definition:** g(n) ∈ Ω(f(n)) if and only if there exist positive constants c and integer N ≥ 0 such that:
```
g(n) ≥ c · f(n)   for all n ≥ N
```

**Example:** Show that 3n + 5 ∈ Ω(n).

For n ≥ 0: 3n + 5 ≥ 3n ≥ 1·n

Choose c = 1, N = 0. Since 3n + 5 ≥ 1·n for all n ≥ 0, we have 3n + 5 ∈ Ω(n). ✓

---

### 1.11 — Big-Θ Notation

**Informal definition:** g(n) ∈ Θ(f(n)) means g(n) grows at exactly the same rate as f(n) (tight bound).

**Formal definition:** g(n) ∈ Θ(f(n)) if and only if g(n) ∈ O(f(n)) **AND** g(n) ∈ Ω(f(n)).

Equivalently: there exist positive constants c₁, c₂ and integer N ≥ 0 such that:
```
c₁ · f(n) ≤ g(n) ≤ c₂ · f(n)   for all n ≥ N
```

**Example:** Show that n² + 5n ∈ Θ(n²).

- Upper bound: n² + 5n ≤ n² + 5n² = 6n² for n ≥ 1 → O(n²) with c = 6, N = 1
- Lower bound: n² + 5n ≥ n² for n ≥ 0 → Ω(n²) with c = 1, N = 0

Both hold, so n² + 5n ∈ Θ(n²). ✓

---

### 1.12 — Set Relationships Between Big-O Classes

O notation defines **sets** of functions. Key relationships:

```
O(1) ⊂ O(log n) ⊂ O(n) ⊂ O(n log n) ⊂ O(n²) ⊂ O(n³) ⊂ O(2ⁿ) ⊂ O(n!)
```

This means: every O(n) function is also O(n²), but NOT vice versa.

**Examples:**
- n ∈ O(n²) ✓ (true — n grows slower than n²)
- n ∉ Θ(n²) ✓ (true — they don't grow at the same rate)
- O(n) ⊂ O(n²) ✓ (every function bounded by n is also bounded by n²)

---

### 1.13 — Limit Approach for Comparing Growth Rates

Given g(n) and f(n), compute:
```
lim(n→∞) g(n) / f(n) = L
```

| Result | Meaning |
|--------|---------|
| L = 0 | g(n) ∈ O(f(n)) but g(n) ∉ Ω(f(n)) — f grows strictly faster |
| 0 < L < ∞ | g(n) ∈ Θ(f(n)) — same order of growth |
| L = ∞ | g(n) ∈ Ω(f(n)) but g(n) ∉ O(f(n)) — g grows strictly faster |

**Example:** Compare n² and n log n.
```
lim(n→∞) n² / (n log n) = lim(n→∞) n / log n = ∞
```
So n² grows strictly faster → n log n ∈ O(n²) and n² ∉ O(n log n).

---

### 1.14 — Proof Techniques

**Mathematical Induction** — proves a statement P(n) for all integers n ≥ n₀:
1. **Base case:** Prove P(n₀) is true.
2. **Inductive step:** Assume P(n) is true (inductive hypothesis), then prove P(n+1) is true.

Used in algorithm analysis to prove exact formulas like: 1 + 2 + ... + n = n(n+1)/2.

**Proof by Contradiction** — proves P by assuming ¬P and deriving a contradiction. If ¬P leads to an impossible conclusion, then P must be true.

---

### 1.15 — Exchange Sort Analysis

Exchange Sort compares every pair of elements and swaps if out of order:

```
for i = 1 to n-1:
    for j = i+1 to n:
        if A[i] > A[j]: swap(A[i], A[j])
```

Number of comparisons:
```
(n-1) + (n-2) + ... + 1 = n(n-1)/2
```

This count is the **same regardless of the input values** — Exchange Sort has **every-case** complexity T(n) = n(n-1)/2 ∈ Θ(n²).

---

---

## UNIT 2 — Divide and Conquer <a name="unit2"></a>

---

### 2.1 — What is Divide and Conquer?

**Divide and Conquer (D&C)** is a top-down algorithm design paradigm:

1. **Divide** — split the problem into smaller sub-instances of the **same type**
2. **Conquer** — recursively solve each sub-instance
3. **Combine (Obtain)** — merge the sub-solutions into the final answer

> **Critical requirement:** The sub-instances must be of the **same type** as the original problem. This is what enables recursion.

**Recursive vs Iterative implementations:**
- Recursive code is cleaner and more natural for D&C
- Recursion uses additional memory (the call stack) — O(log n) for balanced recursion, O(n) for unbalanced
- Iterative implementations can be more space-efficient but harder to write

---

### 2.2 — Binary Search

**Problem:** Given a sorted array and a key x, find the index of x (or determine it's absent).

**Precondition:** The array must be **sorted in non-decreasing order**. Binary Search is undefined (incorrect) on unsorted arrays.

**How it works:**
1. Compare x with the middle element A[mid]
2. If equal: found — return mid
3. If x < A[mid]: search the left half
4. If x > A[mid]: search the right half
5. Repeat until found or the search space is empty

**Recurrence relation (worst case):**
```
W(n) = W(n/2) + 1,   W(1) = 1
```
Each step halves the search space and does 1 comparison.

**Solving:** W(n) = log₂n + 1 ∈ Θ(log n)

**Cases:**
- Best case B(n) = 1 — key is exactly the middle element on the first comparison
- Worst case W(n) = ⌊log₂n⌋ + 1 — key is not found or is at a boundary
- No every-case (depends on where the key is)

**Basic operation:** Comparison between x and A[mid].

---

### 2.3 — Merge Sort

**How it works:**
1. **Divide:** Split the array into two halves
2. **Conquer:** Recursively sort each half
3. **Combine:** Merge the two sorted halves into one sorted array

**Recurrence relation:**
```
T(n) = 2T(n/2) + n,   T(1) = 0
```
- 2T(n/2): recursively sort two halves
- +n: merging takes n comparisons

**Solving:** T(n) = n log₂n ∈ Θ(n log n)

**Key properties:**
- **Every-case complexity**: Merge Sort has every-case Θ(n log n) because the merge step always requires n comparisons regardless of input values — W(n) = B(n) = A(n) = Θ(n log n)
- **NOT in-place:** Algorithm 2.2 creates auxiliary arrays U and V → extra space O(n)
- **Stable sort:** Equal elements preserve their original relative order
- **Basic operation:** Comparison during the merge step

**The Merge Step (Two-Way Merging):**
Given sorted arrays U[1..h] and V[1..m], produce sorted S[1..h+m]:
- Compare U[i] with V[j], take the smaller, advance that pointer
- Time: O(h + m) = O(n) for the combined array

**Space complexity:** O(n) extra space for the auxiliary arrays at each recursive level.

---

### 2.4 — Quick Sort

**How it works:**
1. **Divide (Partition):** Choose a pivot element, place it in its final position so that all elements left of it are smaller and all elements right are larger
2. **Conquer:** Recursively sort the left and right partitions
3. **Combine:** Nothing needed — the array is sorted in-place

**The Partition Procedure (textbook version with first element as pivot):**
```
pivot = A[low]
i = low + 1,  j = high

while i ≤ j:
    while i ≤ j and A[i] < pivot:  i++
    while i ≤ j and A[j] >= pivot: j--
    if i < j: swap(A[i], A[j])

swap(A[low], A[j])   // place pivot at position j
```

When i crosses j, the pivot is placed at position j — its final sorted position.

**Example:** Partition [15, 22, 13, 27, 12, 10, 20, 25] with pivot = 15:
- Elements < 15: {13, 12, 10} → left side
- Elements ≥ 15: {22, 27, 20, 25} → right side
- Pivot lands at index 3: [10, 12, 13, **15**, 22, 27, 20, 25]

**Time complexity cases:**

| Case | When | Recurrence | Complexity |
|------|------|-----------|-----------|
| Worst | Pivot always smallest/largest (sorted input) | T(n) = T(n-1) + (n-1) | Θ(n²) |
| Best | Pivot always splits array in half | T(n) = 2T(n/2) + n | Θ(n log n) |
| Average | Random input | Θ(n log n) | Θ(n log n) |

**Worst-case recurrence solving:**
```
T(n) = T(n-1) + (n-1)
     = T(n-2) + (n-2) + (n-1)
     = ...
     = (n-1) + (n-2) + ... + 1
     = n(n-1)/2 ∈ Θ(n²)
```

**Key properties:**
- **In-place:** partitions within the original array (only recursion stack uses extra space)
- **NOT stable:** the partition step can change relative order of equal elements
- **Basic operation:** Comparison during partition

**Improvement:** Using a **random pivot** or **median-of-three** pivot avoids the sorted-input worst case in practice, giving expected O(n log n) performance.

---

### 2.5 — Merge Sort vs Quick Sort Comparison

| Property | Merge Sort | Quick Sort |
|---------|-----------|-----------|
| Worst case | Θ(n log n) | Θ(n²) |
| Average case | Θ(n log n) | Θ(n log n) |
| Best case | Θ(n log n) | Θ(n log n) |
| In-place? | ❌ No (uses O(n) extra) | ✅ Yes |
| Stable? | ✅ Yes | ❌ No |
| Extra space | O(n) | O(log n) stack |
| Approach | D&C | D&C |

> **Practical note:** Quick Sort is often faster in practice despite the same average-case complexity, because in-place operation gives better cache performance (smaller constants).

---

### 2.6 — Standard Matrix Multiplication

**Algorithm:** Three nested loops compute C = A × B where each entry:
```
C[i][j] = Σ A[i][k] × B[k][j]   for k = 1 to n
```

**Complexity:**
- Basic operation: multiplication (innermost loop)
- T(n) = n³ multiplications → **every-case** Θ(n³)

**For 2×2 matrices:** requires 8 multiplications and 4 additions.

**Divide-and-conquer recurrence:**
```
T(n) = 8T(n/2) + cn²,   T(1) = 1
```
- 8 recursive calls to multiply n/2 × n/2 submatrices
- cn² for the additions to combine

By the Master Theorem, this solves to Θ(n³).

---

### 2.7 — Strassen's Matrix Multiplication

Strassen's algorithm multiplies 2×2 block matrices using **7 multiplications** (not 8) and 18 additions/subtractions.

**Why this matters:** Using 7 instead of 8 recursive calls changes the recurrence:
```
T(n) = 7T(n/2) + cn²
```

By the Master Theorem, this solves to Θ(n^(log₂7)) ≈ Θ(n^2.81).

Since 2.81 < 3, Strassen is asymptotically faster than standard matrix multiplication.

**The 7 products (m₁ through m₇):**
For 2×2 blocks A = [[a₁₁, a₁₂], [a₂₁, a₂₂]] and B = [[b₁₁, b₁₂], [b₂₁, b₂₂]]:
```
m₁ = (a₁₁ + a₂₂)(b₁₁ + b₂₂)
m₂ = (a₂₁ + a₂₂)b₁₁
m₃ = a₁₁(b₁₂ − b₂₂)
m₄ = a₂₂(b₂₁ − b₁₁)
m₅ = (a₁₁ + a₁₂)b₂₂
m₆ = (a₂₁ − a₁₁)(b₁₁ + b₁₂)
m₇ = (a₁₂ − a₂₂)(b₂₁ + b₂₂)
```

**Crossover point (threshold):** Below a certain matrix size, the overhead of 18 additions per recursive level makes Strassen **slower** than the standard algorithm. In practice, implementations switch back to standard multiplication at small matrix sizes.

**Strassen is a D&C algorithm** — it recursively divides n×n matrices into four n/2 × n/2 submatrices.

---

### 2.8 — Large Integer Multiplication

**Problem:** Multiply two n-digit integers u and v.

**Standard grade-school multiplication:** O(n²) digit operations.

**Divide-and-conquer approach:**
Split each n-digit number into two n/2-digit halves:
```
u = a × 10^(n/2) + b
v = c × 10^(n/2) + d
```

Then: `u × v = ac × 10^n + (ad + bc) × 10^(n/2) + bd`

**Naive D&C:** This requires 4 multiplications of n/2-digit numbers (ac, ad, bc, bd).
```
T(n) = 4T(n/2) + cn   →   Θ(n²)   (no better than grade school!)
```

**Karatsuba trick (3 multiplications):**
Compute only: `ac`, `bd`, and `(a+b)(c+d)`.
Then: `ad + bc = (a+b)(c+d) - ac - bd` (recovered from 3 results, no extra multiplications)
```
T(n) = 3T(n/2) + cn   →   Θ(n^(log₂3)) ≈ Θ(n^1.585)
```

This is a genuine improvement over O(n²)!

> **Threshold concept applies here too:** For small integers, the overhead of the recursive calls makes the naive approach faster. Switch to grade-school multiplication below a threshold.

---

---

## UNIT 3 — Dynamic Programming <a name="unit3"></a>

---

### 3.1 — What is Dynamic Programming?

**Dynamic Programming (DP)** is a **bottom-up** algorithm design approach that:
1. Identifies a recursive structure for the optimal (or desired) solution
2. Solves the smallest subproblems first
3. Stores (memoizes) those results in a table
4. Builds up to the final answer using stored results

**Why bottom-up?** Because it avoids recomputing the same subproblem multiple times — each subproblem is solved exactly once.

---

### 3.2 — DP vs Divide and Conquer

| Feature | Divide & Conquer | Dynamic Programming |
|---------|-----------------|-------------------|
| Direction | Top-down (recursive) | Bottom-up (iterative) |
| Subproblems | Independent | Overlapping |
| Recomputation | May recompute (bad for overlapping) | Never recomputes |
| Memory | Stack (O(log n) or O(n)) | Table (O(size of table)) |
| Best for | Independent subproblems | Overlapping subproblems |

**Both use the same recursive property** — the difference is HOW they solve it.

---

### 3.3 — Overlapping Subproblems

**Overlapping subproblems** means the same sub-computations appear multiple times during recursion.

**Fibonacci example** — the classic illustration:
```
Fibonacci(5)
├── Fibonacci(4)
│   ├── Fibonacci(3)
│   │   ├── Fibonacci(2) ← computed again
│   │   └── Fibonacci(1)
│   └── Fibonacci(2) ← computed again
└── Fibonacci(3) ← computed again
    ├── Fibonacci(2) ← computed again
    └── Fibonacci(1)
```

- **Naive recursion:** O(2ⁿ) — exponential blowup due to repeated work
- **DP (bottom-up):** Fill table F[0]=0, F[1]=1, F[i]=F[i-1]+F[i-2] → O(n)

This is WHY DP was invented — to handle overlapping subproblems efficiently.

---

### 3.4 — Steps in Dynamic Programming

**For non-optimization problems (e.g., Binomial Coefficient, Fibonacci):**
1. Establish a recursive property that gives the solution in terms of smaller instances
2. Solve the problem bottom-up, filling a table

**For optimization problems (e.g., TSP, Shortest Path):**
1. Establish a recursive property for the optimal solution
2. Compute the optimal value bottom-up
3. Construct the actual optimal solution (trace back through the table)

---

### 3.5 — Principle of Optimality

The **Principle of Optimality** states: *An optimal solution to a problem contains optimal solutions to its subproblems.*

**Where it applies:**
- ✅ **Shortest path:** If the shortest path A→C goes through B, then A→B must also be the shortest path from A to B
- ✅ **TSP (Traveling Salesperson):** The DP solution relies on this principle
- ✅ **Binomial Coefficient:** B[n][k] = B[n-1][k-1] + B[n-1][k]

**Where it FAILS:**
- ❌ **Longest simple path (no repeated vertices):** Consider a triangle A→B→C→A. The longest simple path from A to C might be A→B→C (length 2), but the sub-path A→B might not be the longest path from A to B (A→C→B might be longer). The principle fails here because using optimal subpaths can lead to cycles.

> If the Principle of Optimality does not hold, **DP cannot be applied** to find an optimal solution.

---

### 3.6 — Binomial Coefficient

**Definition:** B[n][k] = C(n,k) = the number of ways to choose k items from n items.

**Recursive property:**
```
B[n][k] = B[n-1][k-1] + B[n-1][k]
```
"Either the last item IS chosen (then choose k-1 from n-1 remaining) or it IS NOT (then choose k from n-1 remaining)."

**Base cases:**
```
B[n][0] = 1   for all n ≥ 0   (1 way to choose nothing)
B[n][n] = 1   for all n ≥ 0   (1 way to choose everything)
```

> **Common exam trap:** B[n][0] = **1**, NOT 0.

**Symmetry:** B[n][k] = B[n][n-k] (choosing k to include = choosing n-k to exclude)

**Building Pascal's Triangle up to B[5][3]:**

```
     k=0  k=1  k=2  k=3
n=0:  1
n=1:  1    1
n=2:  1    2    1
n=3:  1    3    3    1
n=4:  1    4    6    4
n=5:  1    5   10   10
```

- B[5][2] = B[4][1] + B[4][2] = 4 + 6 = **10**
- B[5][3] = B[4][2] + B[4][3] = 6 + 4 = **10** ← confirms symmetry B[5][2] = B[5][3]

**Complexity comparison:**
| Approach | Time Complexity |
|---------|----------------|
| Naive recursion (D&C) | O(2ⁿ) — exponential (recomputes B[i][j] many times) |
| Dynamic Programming | O(nk) — each of the (n+1)(k+1) cells computed once |

**Space complexity:** O(nk) for the table.

---

### 3.7 — Floyd's Algorithm (All-Pairs Shortest Paths)

**Problem:** Find the shortest path between every pair of vertices in a weighted directed graph. Also called the **All-Pairs Shortest Path (APSP)** problem.

**Key idea (DP formulation):** Gradually allow more intermediate vertices.

**D(k)[i][j]** = the length of the shortest path from vertex vᵢ to vertex vⱼ using **only vertices {v1, v2, ..., vk}** as intermediate vertices.

**Recurrence:**
```
D(k)[i][j] = min(D(k-1)[i][j],   D(k-1)[i][k] + D(k-1)[k][j])
```
"Either the shortest path doesn't use vk as intermediate (first term), or it goes through vk (second term)."

**Initialization:**
```
D(0) = W   (the original weight matrix, with ∞ for missing edges, 0 on diagonal)
```

**Final answer:** D(n) after considering all n vertices as potential intermediates.

**The P matrix (path reconstruction):**
- P[i][j] stores the **highest-indexed intermediate vertex** on the shortest path from vᵢ to vⱼ
- Updated: when D(k)[i][j] is improved via vk, set P[i][j] = k
- If P[i][j] = 0: the shortest path uses no intermediate vertices (direct edge)

**Path reconstruction procedure:**
```
path(i, j):
    if P[i][j] = 0:
        print edge (vi → vj) directly
    else:
        k = P[i][j]
        path(i, k)
        path(k, j)
```

**Worked Example — Tracing D(1) on a 3×3 matrix:**

Initial D(0) = W:
```
     v1   v2   v3
v1 [  0    4    ∞ ]
v2 [  ∞    0    2 ]
v3 [  3    ∞    0 ]
```

Computing D(1) (allow v1 as intermediate: can we improve paths by routing through v1?):

For each pair (i,j), check: min(D(0)[i][j], D(0)[i][1] + D(0)[1][j])

- D(1)[2][3]: min(D(0)[2][3], D(0)[2][1] + D(0)[1][3]) = min(2, ∞+∞) = 2 (no change)
- D(1)[3][2]: min(D(0)[3][2], D(0)[3][1] + D(0)[1][2]) = min(∞, 3+4) = **7** ✓ (improved! P[3][2] = 1)

D(1):
```
     v1   v2   v3
v1 [  0    4    ∞ ]
v2 [  ∞    0    2 ]
v3 [  3    7    0 ]
```

**Important property:** Row k and column k do not change during iteration k.
- D(k)[i][k] = D(k-1)[i][k] (going to vk via vk doesn't help)
- D(k)[k][j] = D(k-1)[k][j] (going from vk via vk doesn't help)

This means we can **update the matrix in-place** during each iteration k.

**Complexity:** 3 nested loops (k from 1 to n, i from 1 to n, j from 1 to n) → **every-case Θ(n³)**

**Negative edge weights:** Floyd's algorithm works correctly with negative edge weights (unlike Dijkstra's). However, **negative-weight cycles** cause incorrect results.

**Detecting negative cycles:** After running Floyd's, if D[i][i] < 0 for any vertex i, there is a negative-weight cycle through vᵢ.

**Floyd's vs Dijkstra's:**

| Feature | Floyd's | Dijkstra's |
|---------|---------|-----------|
| Problem type | All-pairs shortest paths | Single-source shortest paths |
| Approach | Dynamic Programming | Greedy |
| Complexity | O(n³) | O(n²) or O((V+E) log V) |
| Negative edges | ✅ Allowed | ❌ Not allowed |
| Negative cycles | ❌ Incorrect (detectable) | ❌ Not applicable |

---

### 3.8 — Traveling Salesperson Problem (TSP)

**Definition:** Given a complete weighted directed graph with n vertices, find the minimum-weight **Hamiltonian cycle** — a tour that visits every vertex exactly once and returns to the start.

**Brute-force approach:** Try all (n-1)! possible tours (fix the starting vertex to remove rotational duplicates) → O((n-1)!) time.

For 5 vertices: 4! = 24 tours. For 10 vertices: 9! = 362,880 tours. Quickly intractable.

**DP approach (Held-Karp algorithm):**

**D[vᵢ][A]** = the length of the shortest path from vᵢ to v1, using each vertex in set A exactly once as an intermediate.

**Base case** (A = ∅, empty set — no intermediate cities, go directly back to start):
```
D[vᵢ][∅] = W[i][1]   (direct edge weight from vᵢ to v1)
```

**Recursive step:**
```
D[vᵢ][A] = min over all vⱼ ∈ A of { W[i][j] + D[vⱼ][A \ {vⱼ}] }
```
"Go to some city vⱼ in A, then optimally complete the tour from vⱼ."

**Complexity:**
- Number of subsets of {v2, ..., vn}: 2^(n-1)
- For each subset and each vertex: O(n) work
- Total: O(n² · 2ⁿ)

**For n = 5:** 5² · 2⁵ = 25 · 32 = 800 operations (vs 24 for brute force — DP is worse for small n!)

> **Key insight:** DP's advantage over brute force only materializes for larger n. At n=5, brute force is faster. But at n=20, DP is 20² · 2²⁰ ≈ 400 million vs 19! ≈ 10¹⁷ — DP wins enormously.

**TSP is NP-complete:** No polynomial-time algorithm is known. Both brute force (O((n-1)!)) and DP (O(n² · 2ⁿ)) are exponential — DP is just a smaller exponential.

---

### 3.9 — Galactic Algorithms

A **galactic algorithm** is one that is theoretically faster (better asymptotic complexity) than known practical algorithms, but whose constants or threshold sizes are so large that it would only be faster on inputs too large to exist in practice. The term captures the humorous idea that the inputs would need to be the size of a galaxy.

Strassen's algorithm is sometimes called a "near-galactic" algorithm because its crossover point can be very large for naive implementations.

---

---

## Cross-Unit Concepts <a name="cross-unit"></a>

---

### 4.1 — Every-Case vs Non-Every-Case Algorithms

| Algorithm | Every-Case? | Why? |
|-----------|-------------|------|
| Add Array Members | ✅ Yes | Always sums n elements |
| Standard Matrix Multiplication | ✅ Yes | Always does n³ multiplications |
| Exchange Sort | ✅ Yes | Always compares n(n-1)/2 pairs |
| Floyd's Algorithm | ✅ Yes | Always runs n³ iterations |
| Merge Sort | ✅ Yes | Always does n log n comparisons |
| Sequential Search | ❌ No | May find key early |
| Binary Search | ❌ No | May find key at midpoint immediately |
| Quick Sort | ❌ No | Depends on pivot placement |

---

### 4.2 — Algorithm Design Paradigms Comparison

| Paradigm | Direction | Key Idea | Examples |
|----------|-----------|---------|---------|
| **Divide & Conquer** | Top-down | Split → recurse → combine | Binary Search, Merge Sort, Quick Sort, Strassen |
| **Dynamic Programming** | Bottom-up | Solve small first, store results | Floyd's, TSP, Binomial Coefficient, Fibonacci |
| **Greedy** | Local optimal | Make the best local choice at each step | Dijkstra's, Prim's, Kruskal's |

**When to use DP vs D&C:**
- Subproblems are **independent** (no overlap) → D&C is fine
- Subproblems **overlap** (same sub-computations repeated) → Use DP to avoid recomputation

---

### 4.3 — Polynomial vs Exponential Complexity

An algorithm is considered **efficient** if its time complexity is **polynomial**: O(nᵏ) for some constant k.

**Polynomial examples:** O(1), O(log n), O(n), O(n log n), O(n²), O(n³)
**Exponential examples:** O(2ⁿ), O(n!), O(n² · 2ⁿ)

> **Key fact:** Adding a polynomial factor to an exponential does not make it polynomial. O(n² · 2ⁿ) is still exponential.

---

### 4.4 — NP-Completeness (Brief Overview)

**P** = class of problems solvable in polynomial time.

**NP** = class of problems whose solutions can be **verified** in polynomial time.

**NP-complete** = hardest problems in NP. If you could solve any NP-complete problem in polynomial time, you could solve ALL NP problems in polynomial time (P = NP).

**TSP** (as a decision problem) is NP-complete. No polynomial-time algorithm is known — the best algorithms (like Held-Karp DP) are still exponential O(n² · 2ⁿ).

---

### 4.5 — Big-O Subset Relationships (Visual)

```
Complexity classes as nested sets (smaller = more efficient = inner):

 ┌──────────────────────────────────────────────┐
 │  O(n!)                                       │
 │  ┌────────────────────────────────────────┐  │
 │  │  O(2ⁿ)                                │  │
 │  │  ┌──────────────────────────────────┐  │  │
 │  │  │  O(n³)                          │  │  │
 │  │  │  ┌──────────────────────────┐    │  │  │
 │  │  │  │  O(n²)                  │    │  │  │
 │  │  │  │  ┌────────────────────┐  │    │  │  │
 │  │  │  │  │  O(n log n)       │  │    │  │  │
 │  │  │  │  │  ┌──────────────┐  │  │    │  │  │
 │  │  │  │  │  │  O(n)       │  │  │    │  │  │
 │  │  │  │  │  │  ┌────────┐  │  │  │    │  │  │
 │  │  │  │  │  │  │O(log n)│  │  │  │    │  │  │
 │  │  │  │  │  │  │ ┌────┐ │  │  │  │    │  │  │
 │  │  │  │  │  │  │ │O(1)│ │  │  │  │    │  │  │
 │  │  │  │  │  │  │ └────┘ │  │  │  │    │  │  │
 │  │  │  │  │  │  └────────┘  │  │  │    │  │  │
 │  │  │  │  │  └──────────────┘  │  │    │  │  │
 │  │  │  │  └────────────────────┘  │    │  │  │
 │  │  │  └──────────────────────────┘    │  │  │
 │  │  └──────────────────────────────────┘  │  │
 │  └────────────────────────────────────────┘  │
 └──────────────────────────────────────────────┘
```

If g(n) ∈ O(n), then g(n) ∈ O(n²), O(n³), O(2ⁿ), and O(n!) — because O(n) ⊆ O(n²) ⊆ ...

---

### 4.6 — Asymptotic vs Actual Performance

Big-O describes **asymptotic** behavior — what happens for very large n. In practice:

- **Constants matter for small n:** An O(n²) algorithm with constant 0.001 may beat an O(n log n) algorithm with constant 100 for small n.
- **Hardware and memory access patterns matter:** Quick Sort's in-place property gives better cache performance vs Merge Sort's O(n) extra memory, despite both being O(n log n) average.
- **Big-O only gives asymptotic guarantees:** An O(n log n) algorithm is only guaranteed faster than O(n²) for **sufficiently large n**.

> **Exam trap:** "Algorithm B is O(n log n) and Algorithm A is O(n²), therefore B is ALWAYS faster than A." — **FALSE**. Only true for sufficiently large n.

---

### 4.7 — Master Summary Table

| Algorithm | Unit | Approach | Best | Average | Worst | Every-Case? | In-Place? | Stable? |
|-----------|------|----------|------|---------|-------|------------|-----------|---------|
| Sequential Search | 1 | Brute Force | O(1) | O(n) | O(n) | ❌ | ✅ | N/A |
| Exchange Sort | 1 | Brute Force | Θ(n²) | Θ(n²) | Θ(n²) | ✅ | ✅ | ❌ |
| Binary Search | 2 | D&C | O(1) | O(log n) | O(log n) | ❌ | ✅ | N/A |
| Merge Sort | 2 | D&C | Θ(n log n) | Θ(n log n) | Θ(n log n) | ✅ | ❌ | ✅ |
| Quick Sort | 2 | D&C | O(n log n) | Θ(n log n) | O(n²) | ❌ | ✅ | ❌ |
| Matrix Mult | 2 | D&C | Θ(n³) | Θ(n³) | Θ(n³) | ✅ | ✅ | N/A |
| Strassen | 2 | D&C | Θ(n^2.81) | Θ(n^2.81) | Θ(n^2.81) | ✅ | ✅ | N/A |
| Floyd's | 3 | DP | Θ(n³) | Θ(n³) | Θ(n³) | ✅ | ✅ | N/A |
| TSP (DP) | 3 | DP | — | — | O(n² · 2ⁿ) | ✅ | — | N/A |
| Binomial Coeff (DP) | 3 | DP | — | — | O(nk) | ✅ | — | N/A |

---

*Use this guide to build your conceptual foundation. Then drill the MCQs to test your understanding. Good luck on the quiz!* 🎯
