# CMPS323 — Quick Reference Flashcards
## Fill-in-the-Blank, True/False Bank & Formula Flashcards

> Print this page, cover the right column, and test yourself! 🃏

---

## PART A — Fill-in-the-Blank Flashcards

| Question (cover the answer ↓) | Answer |
|-------------------------------|--------|
| Variables are called ________ to the problem | **Parameters** |
| Each specific assignment of values to parameters is a(n) ________ | **Instance** |
| A step-by-step procedure to solve a problem is a(n) ________ | **Algorithm** |
| Algorithm analysis measures efficiency as ________ becomes large | **Input size (n)** |
| T(n) = number of times the algorithm does the ________ for an instance of size n | **Basic operation** |
| W(n) = ________ number of times the basic operation is done | **Maximum (worst-case)** |
| B(n) = ________ number of times the basic operation is done | **Minimum (best-case)** |
| A(n) = ________ time complexity | **Average-case** |
| Functions like 5n² and 5n² + 100 are called ________ functions | **Pure-quadratic** |
| Functions like 0.1n² + n + 100 are called ________ functions | **Complete-quadratic** |
| O(f(n)) provides a(n) ________ bound | **Upper** |
| Ω(f(n)) provides a(n) ________ bound | **Lower** |
| Θ(f(n)) provides a(n) ________ bound | **Tight** |
| Θ(f(n)) = ________ ∩ ________ | **O(f(n)) ∩ Ω(f(n))** |
| To prove g(n) ∈ O(f(n)): g(n) ________ c·f(n) for all n ≥ N | **≤** |
| To prove g(n) ∈ Ω(f(n)): g(n) ________ c·f(n) for all n ≥ N | **≥** |
| For Add Array Members: T(n) = ________ | **n** |
| For Matrix Multiplication (standard): T(n) = ________ | **n³** |
| For Sequential Search: W(n) = ________ , B(n) = ________ | **n, 1** |
| For Binary Search: W(n) = ________ , B(n) = ________ | **⌊log₂n⌋+1, 1** |
| ________ assumes something is true, then leads to a contradiction | **Proof by contradiction** |
| Iterative algorithms are faster than recursive because no ________ is needed | **Stack** |
| D&C divides a problem into ________ smaller instances | **Two or more** |
| The three steps of D&C are ________ , ________ , ________ | **Divide, Conquer, Obtain** |
| D&C is a ________ approach | **Top-down** |
| DP is a ________ approach | **Bottom-up** |
| A sort that uses no extra memory beyond the input is called ________ | **In-place sort** |
| Merge Sort uses extra arrays named ________ and ________ | **U and V** |
| Quick Sort worst case is O(________ ) | **n²** |
| Quick Sort average case is Θ(________ ) | **n log n** |
| Merge Sort complexity in ALL cases is Θ(________ ) | **n log n** |
| Items smaller than the pivot in Quick Sort go to the ________ | **Left** |
| Quick Sort's partitioning is done by the ________ procedure | **Partition** |
| Quick Sort worst case occurs when input is ________ | **Already sorted** |
| Strassen's algorithm complexity is Θ(________ ) | **n^2.81** |
| Strassen uses ________ multiplications per level (vs standard's 8) | **7** |
| Strassen uses ________ additions/subtractions per level (vs standard's 4) | **18** |
| Strassen recurrence for multiplications: T(n) = ________ | **7T(n/2), T(1) = 1** |
| Standard matrix mult recurrence: T(n) = ________ | **8T(n/2), T(1) = 1** |
| Large integer multiplication divides until ________ value is reached | **Threshold** |
| In Strassen's algorithm, matrices are divided into ________ sub-matrices | **Four** |
| Two-way merging combines ________ sorted arrays into one | **Two** |
| DP for Binomial Coefficient has complexity O(________ ) | **nk** |
| D&C for Binomial Coefficient has complexity O(________ ) | **2ⁿ** |
| B[i][j] = 1 when j = ________ or j = ________ | **0 or i (j=0 or j=i)** |
| B[i][j] = B[i-1][j-1] + B[i-1][j] when ________ < j < ________ | **0 < j < i** |
| B[4][2] = ________ | **6** |
| Floyd's algorithm computes ________ shortest paths | **All-pairs** |
| Floyd's algorithm complexity is T(n) = ________ | **n³** |
| D(0) in Floyd's = ________ | **Adjacency/weight matrix W** |
| D(n) in Floyd's = ________ | **Final shortest path matrix** |
| Floyd's recurrence: D(k)[i][j] = min( ________ , ________ ) | **D(k-1)[i][j], D(k-1)[i][k]+D(k-1)[k][j]** |
| P[i][j] in Floyd's stores ________ | **Highest-index intermediate vertex on path vi→vj** |
| P[i][j] = 0 means ________ | **No intermediate vertex (direct edge)** |
| Floyd's algorithm ________ (can/cannot) handle negative edges | **Can** |
| Dijkstra's algorithm ________ (can/cannot) handle negative edges | **Cannot** |
| Dijkstra's algorithm uses a ________ approach | **Greedy** |
| Bellman-Ford algorithm uses a ________ approach | **Dynamic Programming** |
| The Principle of Optimality: optimal solution includes optimal ________ to all sub-problems | **Solutions** |
| Principle of Optimality applies to shortest paths: ________ | **True** |
| Principle of Optimality applies to longest paths: ________ | **False** |
| TSP requires a tour that starts at v1, visits each city ________ , and returns to ________ | **Exactly once, v1** |
| TSP brute force complexity is O(________ ) | **(n-1)!** |
| TSP Held-Karp DP complexity is O(________ ) | **n²·2ⁿ** |
| Held-Karp is ________ (polynomial/exponential) time | **Exponential** |
| D[vi][A] in TSP = length of shortest path from vi to ________ passing through each vertex in A exactly once | **v1** |
| D[vi][∅] = ________ (base case in TSP DP) | **W[i][1] (direct edge to v1)** |
| DP for optimization problems requires ________ steps | **3** |
| The third step (for optimization) is ________ | **Construct the optimal solution** |
| A "galactic algorithm" has great ________ but impractical ________ | **Asymptotic complexity, constants** |
| For TSP with n > 20, use ________ instead of Held-Karp | **Approximation algorithms, greedy, or metaheuristics** |
| Complete-quadratic functions eventually behave like ________ | **Pure-quadratic (quadratic term dominates)** |

---

## PART B — True/False Bank (cover the answer column)

| Statement | T/F | Explanation |
|-----------|-----|-------------|
| W(n) is the minimum number of times the basic op is done | **FALSE** | W = maximum (WORST-case) |
| B(n) is the minimum number of times the basic op is done | **TRUE** | B = best-case = minimum |
| A(n) is the average-case time complexity | **TRUE** | By definition |
| An algorithm can solve a problem in only one way | **FALSE** | Multiple algorithms can solve same problem |
| Sequential search is more efficient than binary search | **FALSE** | Binary search O(log n) is much better than O(n) |
| Any quadratic-time algorithm is eventually more efficient than any linear-time algorithm | **FALSE** | Linear is eventually MORE efficient |
| 5n² + 100 is a pure-quadratic function | **TRUE** | No linear term |
| 0.1n² + n + 100 is a pure-quadratic function | **FALSE** | Has linear term → complete-quadratic |
| Big-O gives a lower bound | **FALSE** | Big-O is upper bound |
| Omega gives a lower bound | **TRUE** | Ω is lower bound |
| Theta gives both upper and lower bound | **TRUE** | Θ = O ∩ Ω = tight bound |
| n² + 10n ∈ O(n²) | **TRUE** | n² + 10n ≤ 11n² for n ≥ 1 |
| n ∈ O(n²) | **TRUE** | n ≤ 1·n² for n ≥ 1. O is upper bound! |
| n³ ∈ O(n²) | **FALSE** | n³ grows faster than n² |
| 5n² ∈ Ω(n²) | **TRUE** | 5n² ≥ 1·n² for n ≥ 0 |
| n ∈ Ω(n²) | **FALSE** | n grows slower, not lower-bounded by n² |
| Θ(f(n)) = O(f(n)) ∩ Ω(f(n)) | **TRUE** | Definition of Theta |
| D&C is a top-down approach | **TRUE** | Starts with big problem, divides down |
| DP is a top-down approach | **FALSE** | DP is BOTTOM-UP |
| D&C divides into two or more smaller instances | **TRUE** | Core definition |
| Merge Sort is an in-place sort | **FALSE** | Uses extra arrays U and V |
| Quick Sort is an in-place sort | **TRUE** | Sorts within the array |
| Items smaller than pivot go to the right in Quick Sort | **FALSE** | They go LEFT |
| Quick Sort's partitioning is done by the Partition procedure | **TRUE** | |
| In good conditions, Quick Sort has O(n log n) performance | **TRUE** | Average case |
| Quick Sort worst case is O(n²) | **TRUE** | When array is already sorted |
| Quick Sort worst case occurs when array is already sorted | **TRUE** | Pivot always picks min/max |
| Merge Sort is O(n log n) in all cases | **TRUE** | Best, average, worst all = n log n |
| Iterative Binary Search is slower than recursive | **FALSE** | Iterative is FASTER (no stack overhead) |
| Strassen's method works best for 2×2 matrices | **FALSE** | Only efficient for LARGE matrices |
| Strassen divides matrices into four sub-matrices | **TRUE** | Each n×n into four n/2×n/2 |
| Strassen always more efficient in multiplications | **TRUE** | 7 vs 8 per level |
| Strassen always more efficient in additions/subtractions | **FALSE** | 18 vs 4 — Strassen uses MORE! |
| Strassen complexity is Θ(n^2.81) | **TRUE** | From T(n)=7T(n/2) → log₂7 ≈ 2.807 |
| Standard matrix mult recurrence is T(n) = 8T(n/2) | **TRUE** | 8 multiplications per level |
| Large integer division stops at a threshold | **TRUE** | Not at 0 or 1 digit necessarily |
| Two-way merging combines two sorted arrays | **TRUE** | Definition |
| DP solves small instances first and saves results | **TRUE** | Core of DP |
| D&C may recompute sub-problems multiple times | **TRUE** | Unlike DP — this is why D&C is slower for overlapping sub-problems |
| DP Binomial Coefficient has complexity O(nk) | **TRUE** | Fills (n+1)×(k+1) table once |
| D&C Binomial Coefficient has complexity O(2ⁿ) | **TRUE** | Binary call tree with repeated sub-problems |
| Floyd's algorithm finds all-pairs shortest paths | **TRUE** | Definition |
| Floyd's algorithm has T(n) = n³ | **TRUE** | Three nested loops of n |
| Floyd's D(0) is initialized to the identity matrix | **FALSE** | D(0) = adjacency/weight matrix W |
| Floyd's algorithm can handle negative edge weights | **TRUE** | Unlike Dijkstra |
| P[i][j] = 0 in Floyd's means no intermediate vertex | **TRUE** | Direct edge used |
| The Principle of Optimality applies to shortest paths | **TRUE** | Optimal sub-paths → optimal full path |
| The Principle of Optimality applies to longest paths | **FALSE** | Counter-example: longest path v1→v4 doesn't contain longest sub-paths |
| TSP tours start and end at same vertex | **TRUE** | It's a Hamiltonian circuit |
| TSP brute force has complexity O(n!) | **FALSE** | It's O((n-1)!) — one less because starting city is fixed |
| Held-Karp algorithm is polynomial time | **FALSE** | O(n²·2ⁿ) is exponential |
| Held-Karp is more efficient than brute force | **TRUE** | O(n²·2ⁿ) << O((n-1)!) |
| For n > 20, Held-Karp is practical | **FALSE** | Too slow — use approximation algorithms |
| Floyd-Warshall is a Dynamic Programming algorithm | **TRUE** | |
| Dijkstra's is a Dynamic Programming algorithm | **FALSE** | Dijkstra is GREEDY |
| Bellman-Ford handles negative edge weights | **TRUE** | Unlike Dijkstra |
| A "galactic algorithm" is impractical due to large constants | **TRUE** | Great asymptotic, terrible in practice |

---

## PART C — Formula Flashcards

### Complexity Order (Best → Worst)
```
Θ(1) < Θ(log n) < Θ(n) < Θ(n log n) < Θ(n²) < Θ(n^2.81) < Θ(n³) < Θ(2ⁿ) < Θ(n!)
```

### Algorithm Complexities
| Algorithm | Basic Op | Complexity |
|-----------|---------|-----------|
| Add Array Members | Addition | T(n) = n |
| Matrix Mult (standard) | Multiplication | T(n) = n³ |
| Sequential Search | Comparison | W(n)=n, B(n)=1, A(n)=(n+1)/2 |
| Binary Search | Comparison | W(n)=⌊log₂n⌋+1, B(n)=1 |
| Merge Sort | Comparison | T(n) = n log n (ALL cases) |
| Quick Sort | Comparison | W(n)=n², A(n)=n log n, B(n)=n log n |
| Strassen Matrix Mult | Multiplication | T(n) = n^2.81 |
| Binomial (D&C) | Addition | O(2ⁿ) |
| Binomial (DP) | Addition | O(nk) |
| Floyd's Shortest Path | Comparison+add | T(n) = n³ |
| TSP Brute Force | All | O((n-1)!) |
| TSP Held-Karp | Comparison+add | O(n²·2ⁿ) |

### Recurrence Relations
| Algorithm | Recurrence | Solution |
|-----------|-----------|---------|
| Binary Search | T(n) = T(n/2) + 1 | T(n) = log₂n |
| Merge Sort | T(n) = 2T(n/2) + n | T(n) = n log n |
| Standard Matrix | T(n) = 8T(n/2) | T(n) = n^log₂8 = n³ |
| Strassen | T(n) = 7T(n/2) | T(n) = n^log₂7 ≈ n^2.81 |

### Big-O Definitions
```
g(n) ∈ O(f(n)):  ∃ c>0, N≥0  such that  g(n) ≤ c·f(n)  ∀n≥N
g(n) ∈ Ω(f(n)):  ∃ c>0, N≥0  such that  g(n) ≥ c·f(n)  ∀n≥N
g(n) ∈ Θ(f(n)):  g(n) ∈ O(f(n)) AND g(n) ∈ Ω(f(n))
```

### Floyd's Recurrence
```
D(k)[i][j] = min( D(k-1)[i][j],  D(k-1)[i][k] + D(k-1)[k][j] )
D(0) = W  (weight matrix)
D(n) = final shortest paths matrix
```

### Binomial Coefficient Recurrence
```
B[i][j] = 1                           when j=0 or j=i
B[i][j] = B[i-1][j-1] + B[i-1][j]    when 0 < j < i
```

### TSP DP (Held-Karp)
```
D[vi][∅] = W[i][1]                                    (base case)
D[vi][A] = min over vj∈A of (W[i][j] + D[vj][A−{vj}])  (recursive)
```

---

## PART D — Worked Example: Pascal's Triangle (B[5][3])

```
Row 0:  1
Row 1:  1  1
Row 2:  1  2  1
Row 3:  1  3  3  1
Row 4:  1  4  6  4   1
Row 5:  1  5 10 10   5  1
```
B[5][3] = B[4][2] + B[4][3] = 6 + 4 = **10**

---

## PART E — Worked Example: Big-O Proofs

**Prove 3n + 7 ∈ O(n):**
- Need: 3n + 7 ≤ c·n for all n ≥ N
- Approach: 3n + 7 ≤ 3n + 7n = 10n for n ≥ 1
- ✅ c = 10, N = 1

**Prove n² ∈ Ω(n):**
- Need: n² ≥ c·n for all n ≥ N
- Approach: n² ≥ 1·n for all n ≥ 1
- ✅ c = 1, N = 1

**Prove n ∉ Ω(n²):**
- Would need: n ≥ c·n² for some c > 0 and all n ≥ N
- But n ≥ c·n² means 1 ≥ c·n, which fails for large n
- ❌ No such c and N exist

---

## PART F — Number of Comparisons in Binary Search

For array size n, worst-case comparisons = **⌊log₂n⌋ + 1**

| n | log₂n | W(n) comparisons |
|---|-------|-----------------|
| 1 | 0 | 1 |
| 2 | 1 | 2 |
| 4 | 2 | 3 |
| 8 | 3 | 4 |
| 16 | 4 | 5 |
| 32 | 5 | 6 |
| 64 | 6 | 7 |
| 128 | 7 | 8 |
| 256 | 8 | 9 |
| 512 | 9 | 10 |
| 1024 | 10 | 11 |
| 1,000,000 | ≈20 | 21 |
| 1,000,000,000 | ≈30 | 31 |

> This is why binary search is AMAZING — 31 comparisons to find anything in 1 billion elements!

---

## PART G — TSP: Number of Tours

| n (cities) | Brute Force Tours (n-1)! | Held-Karp n²·2ⁿ |
|------------|--------------------------|-----------------|
| 4 | 6 | 64 |
| 5 | 24 | 800 |
| 6 | 120 | 2,304 |
| 10 | 362,880 | 102,400 |
| 15 | 87 billion | ~7.4 million |
| 20 | ~1.2 × 10¹⁷ | ~419 million |
| 25 | ~1.6 × 10²⁴ | ~21 billion |

> For n=20: Held-Karp (419M) is billions of times faster than brute force (10¹⁷)!

---

*📌 Study tip: Go through each column of Part A covering the answers, then Part B and Part C formulae — aim for 100% accuracy before the quiz!* 🎯
