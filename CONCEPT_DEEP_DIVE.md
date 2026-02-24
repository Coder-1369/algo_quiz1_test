# CMPS323 — Concept Deep Dive
## In-Depth Explanations + Worked Examples for Tricky Topics

> This file covers the **hardest concepts** that typically trip students up. Each section has a clear explanation, worked example, and common mistake to avoid.

---

## TABLE OF CONTENTS
1. [Big-O, Omega, Theta — How to Prove Them](#notation)
2. [Pure vs. Complete Quadratic](#quadratic)
3. [Overhead and Crossover Points](#overhead)
4. [Binary Search — Complexity Analysis](#binary)
5. [Merge Sort — Why Not In-Place](#mergesort)
6. [Quick Sort — Why Worst Case is Sorted Input](#quicksort)
7. [Strassen — 7 Multiplications Explained](#strassen)
8. [Binomial Coefficient — D&C vs DP](#binomial)
9. [Floyd's Algorithm — Full Worked Example](#floyd)
10. [TSP — Held-Karp DP Explained](#tsp)
11. [Principle of Optimality — Counter-Example](#optimality)
12. [Common Traps Summary](#traps)

---

## 1. Big-O, Omega, Theta — How to Prove Them <a name="notation"></a>

### The Definitions (Memorize These!)

| Notation | Meaning | Condition |
|----------|---------|-----------|
| g(n) ∈ **O(f(n))** | Upper bound | ∃ c > 0, N ≥ 0: g(n) **≤** c·f(n) for all n ≥ N |
| g(n) ∈ **Ω(f(n))** | Lower bound | ∃ c > 0, N ≥ 0: g(n) **≥** c·f(n) for all n ≥ N |
| g(n) ∈ **Θ(f(n))** | Tight bound | g(n) ∈ O(f(n)) **AND** g(n) ∈ Ω(f(n)) |

### Step-by-Step: Proving g(n) = n² + 10n ∈ O(n²)

**Goal:** Find c > 0 and N ≥ 0 such that n² + 10n ≤ c·n² for all n ≥ N.

**Technique:** Replace lower-order terms with the dominant term.

```
n² + 10n ≤ n² + 10n²      (since n ≤ n² for n ≥ 1)
         = 11n²
```

✅ So **c = 11, N = 1** works.

**Alternative proof (same answer, different path):**
```
n² + 10n ≤ 2n²     ←  need 10n ≤ n², i.e., n ≥ 10
```
✅ So **c = 2, N = 10** also works. Both are valid!

> ⚠️ **Common mistake:** Students think there is one "correct" c and N. There are infinitely many valid pairs — just find ONE that works.

---

### Step-by-Step: Proving n² + 10n ∈ Ω(n²)

**Goal:** Find c > 0 and N ≥ 0 such that n² + 10n ≥ c·n² for all n ≥ N.

```
n² + 10n ≥ n²       (since 10n ≥ 0 for n ≥ 0)
```

✅ So **c = 1, N = 0** works.

Since n² + 10n ∈ O(n²) AND n² + 10n ∈ Ω(n²), we conclude n² + 10n ∈ **Θ(n²)**.

---

### What is NOT in Θ(n²)?

| Function | In O(n²)? | In Ω(n²)? | In Θ(n²)? |
|----------|-----------|-----------|-----------|
| n | ✅ Yes | ❌ No | ❌ No |
| n² | ✅ Yes | ✅ Yes | ✅ Yes |
| 5n² + 3n | ✅ Yes | ✅ Yes | ✅ Yes |
| n³ | ❌ No | ✅ Yes | ❌ No |
| 5n + 7 | ✅ Yes | ❌ No | ❌ No |
| 4n³ + 3n² | ❌ No | ✅ Yes | ❌ No |

---

## 2. Pure vs. Complete Quadratic <a name="quadratic"></a>

| Type | Form | Examples |
|------|------|---------|
| **Pure quadratic** | an² + c | 5n², 5n² + 100 |
| **Complete quadratic** | an² + bn + c (b ≠ 0) | 0.1n² + n + 100, 3n² + 50n |

**Why it matters:** Both are Θ(n²). The linear term (bn) eventually becomes negligible compared to n².

```
0.1n² + n + 100   for large n
→ n term = 1000     when n = 1000
→ n² term = 100,000 when n = 1000    (100x larger already!)
→ ratio keeps growing...
```

> 💡 Exam tip: "Pure-quadratic" = no linear term. "Complete-quadratic" = has a linear term.

---

## 3. Overhead and Crossover Points <a name="overhead"></a>

### The Paradox: A Slower Algorithm Can Be Faster!

Suppose:
- Algorithm 1: T(n) = n (linear), but each basic op takes 1000t seconds
- Algorithm 2: T(n) = n² (quadratic), but each basic op takes t seconds

Total times:
- Algorithm 1 takes: **n × 1000t**
- Algorithm 2 takes: **n² × t**

Algorithm 2 is faster when: n² × t < n × 1000t → **n < 1000**

For n < 1000: Algorithm 2 (quadratic) is actually **FASTER**!  
For n > 1000: Algorithm 1 (linear) becomes faster.

### Generalizing:
If Algorithm 1 has overhead k times higher:
- Crossover point: **n = k**
- For n < k: Algorithm 2 wins
- For n > k: Algorithm 1 wins

> 💡 This is why we say algorithms are compared for "sufficiently large n" — there's always a crossover point.

---

## 4. Binary Search — Complexity Analysis <a name="binary"></a>

### How It Works
```
Sorted array: [2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
Search for 23:
  Step 1: mid = index 4 → value 16. 23 > 16 → search RIGHT half
  Step 2: mid = index 7 → value 56. 23 < 56 → search LEFT half
  Step 3: mid = index 5 → value 23. FOUND! ✓
```

### Complexity Analysis
- **Every comparison** cuts the remaining array in half
- After k comparisons, at most n/2ᵏ elements remain
- Worst case (not found or last element): need k comparisons where n/2ᵏ ≈ 1 → k ≈ log₂(n)

| Case | Complexity | When |
|------|-----------|------|
| **Best** B(n) = 1 | O(1) | Key is exactly at midpoint first try |
| **Worst** W(n) = ⌊log₂n⌋ + 1 | O(log n) | Key not in array |
| **Average** A(n) | O(log n) | Key in random position |

> ⚠️ **Binary Search does NOT have every-case complexity** — it depends on WHERE the key is.

### Iterative vs. Recursive
- Both: O(log n) time
- Iterative: O(1) space (no stack)
- Recursive: O(log n) space (call stack)
- **Iterative is faster in practice** (no stack overhead)

---

## 5. Merge Sort — Why NOT In-Place <a name="mergesort"></a>

### Algorithm 2.2 (Textbook)
```
mergesort(S, low, high):
    if high > low:
        mid = (low + high) / 2
        U = S[low..mid]    ← COPY to new array U
        V = S[mid+1..high] ← COPY to new array V
        mergesort(U, ...)
        mergesort(V, ...)
        merge(U, V, S)     ← MERGE back into S
```

**Why not in-place?** Creating arrays U and V requires O(n) extra memory. If U and V weren't created, you couldn't sort left half without overwriting right half.

### Merge Sort Complexity — ALL Cases = Θ(n log n)
```
T(n) = 2T(n/2) + n      (divide into 2 halves, merge costs n)
T(1) = 0

Solving: T(n) = Θ(n log₂n)  *(Θ notation already abstracts away constant factors — the recurrence T(n) = 2T(n/2) + n always yields Θ(n log n))*
```

**Recursion tree visualization:**
```
Level 0:     [n elements]                → n work (merge)
Level 1:  [n/2]    [n/2]                → n work total
Level 2: [n/4][n/4][n/4][n/4]           → n work total
...
Level log n: [1][1][1]...[1]             → n work total

Total = n × log n = n log n
```

---

## 6. Quick Sort — Why Worst Case is Sorted Input <a name="quicksort"></a>

### Why Sorted Input Is Worst Case

With first element as pivot on array [1, 2, 3, 4, 5]:
```
Pivot = 1 → LEFT = [], RIGHT = [2,3,4,5]  → n-1 elements on one side
  Pivot = 2 → LEFT = [], RIGHT = [3,4,5]  → n-2 elements
    Pivot = 3 → LEFT = [], RIGHT = [4,5]  → n-3 elements
      ...
```

This creates a "lopsided tree" with depth n (not log n)!

**Recurrence:** T(n) = T(n-1) + n → T(n) = O(n²)

### Average Case: Θ(n log n)
When the pivot roughly splits the array in half each time:
**Recurrence:** T(n) = 2T(n/2) + n → T(n) = O(n log n)

### Summary Table

| Case | Complexity | When |
|------|-----------|------|
| **Best** | O(n log n) | Pivot always splits equally |
| **Average** | Θ(n log n) | Random pivot choices |
| **Worst** | O(n²) | Array already sorted, first element as pivot |

> 💡 **Trick question alert:** "Quick Sort is in-place" → TRUE (it sorts within the array). "Quick Sort is always O(n log n)" → FALSE (worst case is O(n²)).

---

## 7. Strassen's Matrix Multiplication — 7 Multiplications Explained <a name="strassen"></a>

### The Problem with Standard 2×2 Multiplication
For:
```
[a b] × [e f]
[c d]   [g h]
```
Standard requires 8 multiplications: ae, bg, af, bh, ce, dg, cf, dh

### Strassen's 7 Products (p₁ through p₇)
```
p₁ = (a + d)(e + h)
p₂ = (c + d)e
p₃ = a(f − h)
p₄ = d(g − e)
p₅ = (a + b)h
p₆ = (c − a)(e + f)
p₇ = (b − d)(g + h)
```

Result matrix:
```
[p₁+p₄−p₅+p₇  p₃+p₅    ]
[p₂+p₄        p₁−p₂+p₃+p₆]
```

Only **7 multiplications** (p₁–p₇) but **18 additions/subtractions**.

### Complexity Comparison

| Algorithm | Multiplications | Additions | Complexity |
|-----------|----------------|-----------|-----------|
| Standard | 8 per level | 4 per level | T(n) = 8T(n/2) → **Θ(n³)** |
| Strassen | 7 per level | 18 per level | T(n) = 7T(n/2) → **Θ(n^2.81)** |

### When is Strassen Better?
- Strassen saves 1 multiplication but adds 14 extra additions per level
- For **small** n: extra additions slow it down
- For **large** n: the n^2.81 vs n³ difference dominates
- Crossover point: implementation and hardware-dependent — exact value varies, but Strassen only outperforms standard multiplication for matrices larger than a few dozen rows on most hardware

> ⚠️ **Key exam traps:**
> - Strassen always more efficient in **multiplications**: TRUE
> - Strassen always more efficient in **additions**: FALSE (18 vs 4!)
> - Strassen always faster: FALSE (only for large n)

---

## 8. Binomial Coefficient — D&C vs DP <a name="binomial"></a>

### The Recursive Property (Same in Both!)
```
B[i][j] = 1                           if j = 0 or j = i
B[i][j] = B[i-1][j-1] + B[i-1][j]    if 0 < j < i
```

### Why D&C is Exponential O(2ⁿ)
The call tree for bin(5,2):
```
         bin(5,2)
        /        \
    bin(4,1)   bin(4,2)
    /    \     /      \
bin(3,0) bin(3,1) bin(3,1) bin(3,2)
              ↑         ↑
           SAME!     SAME!
```
`bin(3,1)` is computed **TWICE**. This duplication compounds exponentially.

### Why DP is O(nk)
Build the Pascal's Triangle table row by row:
```
i\j  0  1  2  3  4
 0 [ 1 ]
 1 [ 1  1 ]
 2 [ 1  2  1 ]
 3 [ 1  3  3  1 ]
 4 [ 1  4  6  4  1 ]
```

Each cell computed **ONCE** from cells already in the table.
Total cells filled = O(nk) → **much better than O(2ⁿ)**

### Worked Example: Compute B[4][2]
```
B[0][0] = 1
B[1][0] = 1, B[1][1] = 1
B[2][0] = 1, B[2][1] = B[1][0] + B[1][1] = 1+1 = 2, B[2][2] = 1
B[3][0] = 1, B[3][1] = B[2][0] + B[2][1] = 1+2 = 3, B[3][2] = B[2][1]+B[2][2] = 2+1 = 3
B[4][0] = 1, B[4][1] = B[3][0]+B[3][1] = 1+3 = 4, B[4][2] = B[3][1]+B[3][2] = 3+3 = 6
```
Answer: **B[4][2] = 6** = C(4,2) = 4!/(2!×2!) = 6 ✓

---

## 9. Floyd's Algorithm — Full Worked Example <a name="floyd"></a>

### Graph Example
```
Vertices: v1, v2, v3, v4, v5
Edges (weight matrix W):
     v1  v2  v3  v4  v5
v1 [  0   1   ∞   1   5 ]
v2 [  9   0   3   2   ∞ ]
v3 [  ∞   ∞   0   4   ∞ ]
v4 [  ∞   ∞   2   0   3 ]
v5 [  3   ∞   ∞   ∞   0 ]
```

### D(0) = W (the adjacency matrix as initial state)

### Computing D(1) — Using v1 as intermediate
Rule: D(1)[i][j] = min(D(0)[i][j], D(0)[i][1] + D(0)[1][j])

Example calculations:
- D(1)[5][2] = min(D(0)[5][2], D(0)[5][1] + D(0)[1][2])
             = min(∞, 3 + 1) = **4**
- D(1)[5][4] = min(D(0)[5][4], D(0)[5][1] + D(0)[1][4])
             = min(∞, 3 + 1) = **4**
- D(1)[2][4] = min(D(0)[2][4], D(0)[2][1] + D(0)[1][4])
             = min(2, 9 + 1) = **2** (no improvement)

### Key Insight: What k Means
When k=3: "Can we find a shorter path by going THROUGH v3?"
- If yes, D(k)[i][j] updates
- If the direct path is already shorter, keep D(k-1)[i][j]

### The Algorithm (Every-Case T(n) = n³)
```
D = W;
for k = 1 to n:          ← n iterations
  for i = 1 to n:        ← n iterations
    for j = 1 to n:      ← n iterations
      D[i][j] = min(D[i][j], D[i][k] + D[k][j])
```
3 nested loops, each running n times → **T(n) = n³**

### Path Reconstruction with P matrix
P[i][j] stores the highest-index intermediate vertex k used.
To find path from vi to vj:
```
path(q, r):
  if P[q][r] != 0:           // there's an intermediate vertex
    path(q, P[q][r])         // first half of path
    print P[q][r]            // the intermediate vertex
    path(P[q][r], r)         // second half of path
```

**Example:** P[1][3] = 4 means "the path from v1 to v3 goes through v4"
- path(1, 3): P[1][3]=4 → path(1,4), print v4, path(4,3)
- If P[1][4]=0 and P[4][3]=0 → direct edges
- Result: v1 → v4 → v3

---

## 10. TSP — Held-Karp DP Explained <a name="tsp"></a>

### Problem Setup
- n cities, starting and ending at v1
- Find minimum-cost tour visiting each city exactly once

### Key Notation
- **V** = all vertices = {v1, v2, v3, v4}
- **A** = subset of V − {v1}
- **D[vi][A]** = length of shortest path from vi → v1, visiting each vertex in A exactly once

### Base Cases (Empty Set)
No intermediate vertices — just go directly back to v1:
```
D[v2][∅] = W[2][1]
D[v3][∅] = W[3][1]
D[v4][∅] = W[4][1]
```

### Recursive Property
```
D[vi][A] = min over all vj in A of:  W[i][j] + D[vj][A − {vj}]
```
"To get from vi to v1 via cities in A: go to some city vj in A first, then optimally travel from vj through the remaining cities A−{vj} back to v1."

### Worked Example (4 cities, W from slides)
```
W:     v1  v2  v3  v4
v1  [   0   2  ∞   8 ]
v2  [   5   0  3   ∞ ]
v3  [   ∞   ∞  0   6 ]
v4  [   8   ∞  2   0 ]
```

**Step 1 — Base case (empty sets):**
```
D[v2][∅] = W[2][1] = 5
D[v3][∅] = W[3][1] = ∞  (no direct edge v3→v1)
D[v4][∅] = W[4][1] = 8
```

**Step 2 — Sets of size 1:**
```
D[v2][{v3}] = W[2][3] + D[v3][∅] = 3 + ∞ = ∞
D[v2][{v4}] = W[2][4] + D[v4][∅] = ∞ + 8 = ∞
D[v3][{v2}] = W[3][2] + D[v2][∅] = ∞ + 5 = ∞
D[v3][{v4}] = W[3][4] + D[v4][∅] = 6 + 8 = 14
D[v4][{v2}] = W[4][2] + D[v2][∅] = ∞ + 5 = ∞
D[v4][{v3}] = W[4][3] + D[v3][∅] = 2 + ∞ = ∞
```

**Step 3 — Final answer (tour from v1):**
```
D[v1][{v2,v3,v4}] = min over j in {v2,v3,v4}:
  W[1][2] + D[v2][{v3,v4}]
  W[1][3] + D[v3][{v2,v4}]
  W[1][4] + D[v4][{v2,v3}]
```

### Complexity: O(n²·2ⁿ)
- 2^(n-1) subsets of V−{v1}
- For each subset, n−1 possible starting cities
- Each computation: O(n) work
- Total: O(n · 2^n · n) = O(n²·2ⁿ)

---

## 11. Principle of Optimality — Counter-Example <a name="optimality"></a>

### Definition
The principle applies if: **an optimal solution to the whole problem always includes optimal solutions to all sub-problems.**

### Why It WORKS for Shortest Paths
If the shortest path from v1 to v5 goes through v3, then the portion from v1 to v3 must itself be the shortest path from v1 to v3.

**Proof by contradiction:** If there were a shorter path from v1 to v3, we could substitute it into the full path and get a shorter v1-to-v5 path, contradicting optimality.

### Why It FAILS for Longest Paths
Consider this textbook example with 4 vertices:
```
Vertices: v1, v2, v3, v4

Edges (with weights):
  v1 → v2 (weight 2)
  v1 → v3 (weight 1)
  v2 → v3 (weight 3)    ← longer route v1→v2→v3 = 5
  v2 → v4 (weight 4)
  v3 → v2 (weight 8)    ← another route through v3
  v3 → v4 (weight 2)
```
- Longest **simple** path from v1 to v4: [v1, v3, v2, v4] = 1 + 8 + 4 = **13**
- Sub-path from v1 to v3 on this path: [v1, v3] = **1**
- BUT the longest path from v1 to v3 is actually [v1, v2, v3] = 2 + 3 = **5**

The optimal path v1→v4 uses a sub-path v1→v3 of length 1, which is **NOT** the longest path from v1 to v3 (which is 5). This violates the Principle of Optimality.

> 💡 **Exam key:** Principle of Optimality applies to **shortest paths** ✅ but NOT **longest paths** ❌.

---

## 12. Common Traps Summary <a name="traps"></a>

### Top 15 Exam Traps

| # | Tricky Statement | Correct Answer | Quick Reason |
|---|-----------------|----------------|--------------|
| 1 | W(n) = minimum times basic op is done | **FALSE** | W = worst = MAXIMUM; B = best = minimum |
| 2 | Any quadratic algorithm is more efficient than linear | **FALSE** | Linear is always eventually MORE efficient |
| 3 | Quick Sort items < pivot go RIGHT | **FALSE** | They go LEFT |
| 4 | Strassen always faster in add/subtract ops | **FALSE** | Uses 18 vs 4 — worse! Only multiplications are reduced |
| 5 | Merge Sort (Alg 2.2) is in-place | **FALSE** | Creates extra arrays U and V |
| 6 | Bottom-up = same as top-down | **FALSE** | Top-down: big→small; Bottom-up: small→big |
| 7 | Binary Search has every-case complexity | **FALSE** | Depends on where key is in array |
| 8 | D&C is bottom-up | **FALSE** | D&C is TOP-DOWN; DP is bottom-up |
| 9 | Principle of Optimality holds for longest path | **FALSE** | Counter-example exists |
| 10 | Floyd allows negative edges | **TRUE** | Unlike Dijkstra |
| 11 | TSP Held-Karp is polynomial time | **FALSE** | O(n²·2ⁿ) is still exponential |
| 12 | Recursive Binary Search is faster than iterative | **FALSE** | Iterative is faster (no stack overhead) |
| 13 | Strassen works best for 2×2 matrices | **FALSE** | Only efficient for LARGE matrices |
| 14 | n ∈ O(n²) | **TRUE** | n ≤ 1·n² for n≥1. O is upper bound, not tight bound |
| 15 | A(n) = n for sequential search (x always present) | **FALSE** | A(n) = (n+1)/2 — average position |

---

### Big Notation Membership Quick Test

To test if g(n) ∈ O(f(n)): Ask "Can n·f(n) eventually dominate g(n)?"
- g(n) = n, f(n) = n²: YES → n ∈ O(n²) ✅
- g(n) = n³, f(n) = n²: NO → n³ ∉ O(n²) ❌

To test if g(n) ∈ Ω(f(n)): Ask "Is g(n) eventually at least as large as some multiple of f(n)?"
- g(n) = n², f(n) = n: YES → n² ∈ Ω(n) ✅
- g(n) = n, f(n) = n²: NO → n ∉ Ω(n²) ❌

---

### Algorithm Paradigm Quick Reference

| Algorithm | Paradigm | In-Place? | Stable? | Every-Case? |
|-----------|---------|----------|--------|-------------|
| Sequential Search | Brute Force | ✅ | N/A | ❌ |
| Binary Search | Divide & Conquer | ✅ | N/A | ❌ |
| Merge Sort | Divide & Conquer | ❌ (uses U,V) | ✅ | ✅ |
| Quick Sort | Divide & Conquer | ✅ | ❌ | ❌ |
| Floyd-Warshall | Dynamic Programming | ✅ | N/A | ✅ |
| Binomial (DP) | Dynamic Programming | N/A | N/A | ✅ |
| TSP Held-Karp | Dynamic Programming | N/A | N/A | ✅ |
| Dijkstra | Greedy | N/A | N/A | ❌ |

---

*Master these concepts and you'll ace any CMPS323 quiz! 🎯*
