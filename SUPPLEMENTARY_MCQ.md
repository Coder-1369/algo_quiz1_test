# CMPS323 – Supplementary MCQ Set
## Units 1, 2 & 3 — "No Surprises" Edition 🎯

> These are **original questions** created to fill gaps in the main study guide. They test the same Units 1–3 concepts from **different angles** — the way a professor writes new quiz questions. Combined with the 80 questions in `STUDY_GUIDE_MCQ.md`, you'll have 140 MCQs covering every possible angle.

---

## TABLE OF CONTENTS
1. [Unit 1 — Gaps Filled](#unit-1-sup)
2. [Unit 2 — Gaps Filled](#unit-2-sup)
3. [Unit 3 — Gaps Filled](#unit-3-sup)
4. [Cross-Unit Comparison Questions](#cross-unit)
5. [Tricky True/False — Exam Traps](#traps)

---

## UNIT 1 — Gaps Filled <a name="unit-1-sup"></a>

> **What the original guide missed:** basic operation identification, complete-quadratic vs pure-quadratic deeper, limit approach for comparing orders, Ω proofs, mathematical induction, exchange sort analysis, average-case computation, constant-time algorithms.

---

**S1.** The function 0.1n² + n + 100 is called a ________ function.
- A) Pure-quadratic
- B) **Complete-quadratic ✅**
- C) Linear
- D) Cubic

> 💡 Has a linear term (n), so it's *complete*-quadratic. Pure-quadratic has no linear term (e.g., 5n² + 100).

---

**S2.** What is the **basic operation** in the standard matrix multiplication algorithm?
- A) Addition
- B) Comparison
- C) **Multiplication (in the innermost loop) ✅**
- D) Assignment

> The basic operation is always the one in the **innermost** loop that dominates the count.

---

**S3.** What is the **basic operation** in Sequential Search?
- A) Swapping
- B) **Comparison (comparing x with array elements) ✅**
- C) Addition
- D) Assignment

---

**S4.** What is the **basic operation** in a sorting algorithm like Exchange Sort?
- A) Incrementing the loop counter
- B) Array access
- C) **Comparison of array elements ✅**
- D) Printing the result

---

**S5.** The time complexity of Exchange Sort (comparing all pairs) is:
- A) O(n)
- B) O(n log n)
- C) **O(n²) — every-case ✅**
- D) O(n³)

> Exchange Sort always compares n(n-1)/2 pairs regardless of input → every-case Θ(n²).

---

**S6.** An algorithm has T(n) = 3n² + 7n + 4. What is its time complexity in Θ notation?
- A) Θ(n)
- B) Θ(n³)
- C) **Θ(n²) ✅**
- D) Θ(n log n)

> Drop constants and lower-order terms.

---

**S7.** Is 6n³ ∈ O(n²)? (True/False)
- **False ✅** — n³ grows faster than n². No constant c can make 6n³ ≤ c·n² for all large n.

---

**S8.** Is n ∈ O(n²)? (True/False)
- **True ✅** — n ≤ 1·n² for all n ≥ 1. But it's NOT a tight bound — n ∉ Θ(n²).

---

**S9.** Is 3n + 5 ∈ Ω(n)? (True/False)
- **True ✅** — 3n + 5 ≥ 1·n for all n ≥ 0. Use c = 1.

---

**S10.** Show that n² + 5n ∈ Θ(n²). Which of the following is the correct reasoning?
- A) Because n² + 5n ≤ 6n² for n ≥ 1, and n² + 5n ≥ n² for n ≥ 0
- B) Because the coefficient of n² is 1
- C) **A is correct — it proves both O(n²) (c=6, N=1) and Ω(n²) (c=1, N=0), so Θ(n²) ✅**
- D) It cannot be proven

---

**S11.** To prove g(n) ∈ Ω(f(n)), you must find:
- A) c > 0 and N ≥ 0 such that g(n) ≤ c·f(n) for all n ≥ N
- B) **c > 0 and N ≥ 0 such that g(n) ≥ c·f(n) for all n ≥ N ✅**
- C) c > 0 such that g(n) = c·f(n)
- D) N ≥ 0 such that g(n) < f(n) for all n ≥ N

---

**S12.** If g(n) ∈ O(f(n)) and g(n) ∈ Ω(f(n)), then g(n) ∈ ________.
- A) O(f(n)) only
- B) Ω(f(n)) only
- C) **Θ(f(n)) ✅**
- D) None of the above

---

**S13.** Which of the following is true about an algorithm with **every-case** time complexity?
- A) It always runs in O(1)
- B) **T(n) = W(n) = B(n) = A(n) for every input of size n ✅**
- C) It has no basic operation
- D) It cannot be analyzed

> Examples: Add Array Members (T(n) = n), Matrix Mult (T(n) = n³), Floyd's (T(n) = n³).

---

**S14.** Arranging the following in order from slowest to fastest growing: n!, 2ⁿ, n³, n log n, n², log n, n, 1
- A) 1, n, log n, n², n log n, n³, 2ⁿ, n!
- B) **1, log n, n, n log n, n², n³, 2ⁿ, n! ✅**
- C) log n, 1, n, n², n log n, n³, n!, 2ⁿ
- D) 1, log n, n log n, n, n², n³, 2ⁿ, n!

---

**S15.** Using the limit approach: if lim(n→∞) g(n)/f(n) = c where 0 < c < ∞, then:
- A) g(n) ∈ O(f(n)) only
- B) g(n) ∈ Ω(f(n)) only
- C) **g(n) ∈ Θ(f(n)) ✅**
- D) They are unrelated

---

**S16.** ________ proves a theorem by first proving a base case and then proving that if the theorem is true for n, it must also be true for n+1.
- A) Proof by contradiction
- B) Direct proof
- C) **Mathematical induction ✅**
- D) Proof by counterexample

---

**S17.** For Sequential Search, what is A(n) assuming the key is equally likely to be at any position (and is guaranteed to be in the array)?
- A) n
- B) 1
- C) **n/2 (approximately (n+1)/2) ✅**
- D) log n

> Average = (1 + 2 + 3 + ... + n)/n = (n+1)/2 ≈ n/2.

---

**S18.** An algorithm with T(n) = 5 for all n has complexity:
- A) O(n)
- B) O(log n)
- C) **O(1) — constant time ✅**
- D) O(n²)

---

## UNIT 2 — Gaps Filled <a name="unit-2-sup"></a>

> **What the original guide missed:** Merge Sort recurrence relation, Quick Sort best-case, Binary Search recurrence, partition step-by-step, stability of sorts, Merge Sort space complexity, Strassen crossover point, large integer multiplication recurrence, Binary Search precondition.

---

**S19.** Binary Search requires the array to be:
- A) Of even length
- B) Containing unique elements
- C) **Sorted in non-decreasing order ✅**
- D) Stored in a linked list

---

**S20.** The recurrence relation for Binary Search (worst-case) is:
- A) T(n) = T(n-1) + 1
- B) T(n) = 2T(n/2) + 1
- C) **W(n) = W(n/2) + 1, W(1) = 1 ✅**
- D) W(n) = W(n-1) + n

> Each step halves the search space and does 1 comparison.

---

**S21.** The recurrence relation for Merge Sort is:
- A) T(n) = T(n/2) + n
- B) T(n) = T(n-1) + n
- C) **T(n) = 2T(n/2) + n, with T(1) = 0 — which solves to Θ(n log n) ✅**
- D) T(n) = 7T(n/2) + n²

> Splits into 2 halves (2T(n/2)) and merging takes n comparisons.

---

**S22.** The recurrence relation for Quick Sort in the **worst case** is:
- A) T(n) = 2T(n/2) + n
- B) **T(n) = T(n-1) + n-1, which solves to Θ(n²) ✅**
- C) T(n) = T(n/2) + 1
- D) T(n) = 7T(n/2)

> Worst case: pivot is always smallest/largest → one partition has n-1 elements, other has 0.

---

**S23.** What is the **best-case** time complexity of Quick Sort?
- A) O(n)
- B) O(n²)
- C) **O(n log n) ✅**
- D) O(log n)

> Best case: pivot always splits array roughly in half → same as merge sort.

---

**S24.** After one complete partition step of Quick Sort on the array [15, 22, 13, 27, 12, 10, 20, 25] with pivot = 15, what is the pivot's final position (0-indexed)?
- A) Position 0
- B) Position 2
- C) **Position 3 ✅**
- D) Position 4

> Elements < 15: {13, 12, 10} go left. Elements ≥ 15: {22, 27, 20, 25} go right. Pivot lands at index 3: [10, 12, 13, **15**, 22, 27, 20, 25].

---

**S25.** Quick Sort is an in-place sorting algorithm. (True/False)
- **True ✅** — It partitions the array in-place (aside from the recursion stack). Unlike Merge Sort, it doesn't create new arrays.

---

**S26.** Merge Sort is a **stable** sorting algorithm. Quick Sort (textbook version) is also stable. (True/False)
- **False ✅** — Merge Sort IS stable (preserves relative order of equal elements). Quick Sort is generally NOT stable.

---

**S27.** The extra space complexity of Merge Sort (Algorithm 2.2) is:
- A) O(1)
- B) O(log n)
- C) **O(n) ✅**
- D) O(n²)

> It creates subarrays U and V at each level. Total extra space is O(n).

---

**S28.** In Merge Sort, the "merge" step combines two sorted subarrays. What is the time complexity of merging two sorted arrays of total size n?
- A) O(1)
- B) O(log n)
- C) **O(n) ✅**
- D) O(n²)

---

**S29.** Quick Sort with a **random pivot** selection has an expected time complexity of:
- A) O(n²)
- B) O(n)
- C) **O(n log n) ✅**
- D) O(log n)

> Randomized pivot avoids the sorted-input worst case with high probability.

---

**S30.** In the Quick Sort partition procedure, what happens when the scanning index i meets or crosses j?
- A) The array is sorted
- B) We restart the partition
- C) **The partition is complete and the pivot is placed at position j ✅**
- D) We pick a new pivot

---

**S31.** Standard 2×2 matrix multiplication requires ________ multiplications and ________ additions.
- A) 7 multiplications, 18 additions
- B) **8 multiplications, 4 additions ✅**
- C) 4 multiplications, 8 additions
- D) 8 multiplications, 18 additions

---

**S32.** Strassen's 2×2 matrix multiplication requires ________ multiplications and ________ additions/subtractions.
- A) 8 multiplications, 4 additions
- B) **7 multiplications, 18 additions/subtractions ✅**
- C) 6 multiplications, 12 additions
- D) 7 multiplications, 4 additions

---

**S33.** The recurrence relation for **standard** matrix multiplication is:
- A) T(n) = 7T(n/2) + cn²
- B) **T(n) = 8T(n/2) + cn², which gives Θ(n³) ✅**
- C) T(n) = 4T(n/2) + cn
- D) T(n) = 2T(n/2) + n

---

**S34.** The recurrence relation for **Strassen's** matrix multiplication is:
- A) T(n) = 8T(n/2) + cn²
- B) T(n) = 7T(n/2), no additional work
- C) **T(n) = 7T(n/2) + cn², which gives Θ(n^log₂7) ≈ Θ(n^2.81) ✅**
- D) T(n) = 4T(n/2) + cn²

> 7 recursive multiplications of n/2 × n/2 submatrices + cn² additions/subtractions.

---

**S35.** Strassen's algorithm becomes practically faster than standard multiplication only when matrices exceed a certain size, called the ________.
- A) Base case
- B) Recursion limit
- C) **Crossover point (threshold) ✅**
- D) Pivot point

> Below this size, the overhead of 18 additions per level makes Strassen slower.

---

**S36.** In the large integer multiplication (divide and conquer), an n-digit integer is split into:
- A) n pieces of 1 digit each
- B) **Two halves of n/2 digits each ✅**
- C) Three pieces of n/3 digits each
- D) Four pieces of n/4 digits each

---

**S37.** The naive large integer multiplication using divide-and-conquer requires ________ multiplications of n/2-digit numbers.
- A) 2
- B) 3
- C) **4 ✅**
- D) 7

> u = a·10^(n/2) + b, v = c·10^(n/2) + d → u×v needs ac, ad, bc, bd = 4 multiplications.

---

**S38.** The improved large integer multiplication (using the trick similar to Karatsuba) reduces the number of recursive multiplications to:
- A) 2
- B) **3 ✅**
- C) 4
- D) 7

> Compute ac, bd, and (a+b)(c+d) — then ad + bc = (a+b)(c+d) - ac - bd. Only 3 multiplications!

---

**S39.** Which of the following is TRUE about Binary Search?
- A) It works on unsorted arrays
- B) It works on linked lists efficiently
- C) Its best case is O(log n)
- D) **Its best case is O(1) — when the middle element is the key ✅**

---

**S40.** In divide and conquer, the sub-instances must be of the ________ type as the original problem.
- A) Different
- B) Larger
- C) **Same ✅**
- D) Opposite

---

## UNIT 3 — Gaps Filled <a name="unit-3-sup"></a>

> **What the original guide missed:** Floyd's tracing on actual numbers, P matrix path reconstruction, Binomial table with different values, TSP recurrence details, Fibonacci as DP example, overlapping subproblems deeper, space complexity of DP, when DP fails.

---

**S41.** The term "overlapping subproblems" in DP means:
- A) The subproblems are independent
- B) **The same subproblems appear multiple times during recursion ✅**
- C) The subproblems overlap in memory
- D) The problem cannot be divided

> This is WHY DP saves results — to avoid solving the same subproblem repeatedly.

---

**S42.** Computing the nth Fibonacci number using naive recursion has complexity:
- A) O(n)
- B) O(n²)
- C) O(n log n)
- D) **O(2ⁿ) approximately (exponential) ✅**

> The recursion tree has overlapping subproblems → exponential blowup.

---

**S43.** Computing the nth Fibonacci number using Dynamic Programming has complexity:
- A) O(2ⁿ)
- B) O(n²)
- C) **O(n) ✅**
- D) O(n log n)

> Simply fill a table bottom-up: F[0]=0, F[1]=1, F[i]=F[i-1]+F[i-2].

---

**S44.** In Floyd's algorithm, what does D(k)[i][j] represent?
- A) The weight of edge (i,j)
- B) **The length of the shortest path from vi to vj using only vertices {v1, v2, ..., vk} as intermediate vertices ✅**
- C) The number of edges from vi to vj
- D) The degree of vertex vk

---

**S45.** Given this weight matrix W (D(0)):

```
     v1   v2   v3
v1 [  0    4    ∞ ]
v2 [  ∞    0    2 ]
v3 [  3    ∞    0 ]
```

After computing D(1) (allowing v1 as intermediate), what is D(1)[3][2]?
- A) ∞
- B) 4
- C) 3
- D) **7 ✅**

> D(1)[3][2] = min(D(0)[3][2], D(0)[3][1] + D(0)[1][2]) = min(∞, 3 + 4) = **7**. Path: v3 → v1 → v2.

---

**S46.** In Floyd's algorithm, when we compute D(k)[i][j] and find that the path through vk is shorter, what do we store in P[i][j]?
- A) The value i
- B) The value j
- C) **The value k ✅**
- D) The distance D(k)[i][j]

---

**S47.** To reconstruct the actual shortest path from vi to vj using the P matrix, you:
- A) Simply read P[i][j] as the path
- B) **Recursively find the path from vi to P[i][j], then from P[i][j] to vj ✅**
- C) Look up the weight matrix W
- D) Run Dijkstra's algorithm

> The path function: path(i,j) = path(i, P[i][j]) → P[i][j] → path(P[i][j], j).

---

**S48.** In Floyd's algorithm, if P[i][j] = 0 (or undefined), it means:
- A) There is no path from vi to vj
- B) **The shortest path from vi to vj uses no intermediate vertices (direct edge) ✅**
- C) The distance is infinity
- D) vk = v0 is intermediate

---

**S49.** Floyd's algorithm has ________ nested loops.
- A) 1
- B) 2
- C) **3 ✅**
- D) 4

> k (intermediate vertex), i (source), j (destination) → O(n³).

---

**S50.** Using the Binomial Coefficient DP, compute B[5][2]:
- A) 5
- B) 8
- C) **10 ✅**
- D) 15

> B[5][2] = B[4][1] + B[4][2] = 4 + 6 = **10**.

---

**S51.** Using the Binomial Coefficient DP, compute B[5][3]:
- A) 5
- B) 8
- C) **10 ✅**
- D) 15

> B[5][3] = B[4][2] + B[4][3] = 6 + 4 = **10**. Note: B[n][k] = B[n][n-k] (symmetry!).

---

**S52.** The space complexity of the Binomial Coefficient DP table is:
- A) O(n)
- B) **O(nk) ✅**
- C) O(n²)
- D) O(2ⁿ)

> We build a table with at most (n+1) rows and (k+1) columns.

---

**S53.** In the TSP DP formulation, D[vi][∅] (empty set A) equals:
- A) 0
- B) ∞
- C) **W[i][1] — the direct edge weight from vi back to v1 ✅**
- D) 1

> Base case: if no intermediate cities remain, you go directly back to the starting city.

---

**S54.** In TSP with 4 cities (v1, v2, v3, v4), how many subsets A does the DP algorithm consider (excluding the starting city v1)?
- A) 4
- B) **8 (2³ = subsets of {v2, v3, v4}) ✅**
- C) 16
- D) 24

> We consider all subsets of the remaining n-1 = 3 cities → 2³ = 8 subsets.

---

**S55.** The Principle of Optimality applies to the **Shortest Path** problem. (True/False)
- **True ✅** — If the shortest path from A to C goes through B, then the sub-path from A to B must also be the shortest path from A to B.

---

**S56.** Which of the following problems does the Principle of Optimality NOT apply to?
- A) Shortest path
- B) TSP
- C) **Longest simple path (no repeated vertices) ✅**
- D) Binomial Coefficient

---

**S57.** Dynamic Programming for **non-optimization** problems (like Binomial Coefficient) requires ________ steps.
- A) 1
- B) **2 ✅**
- C) 3
- D) 4

> Steps: 1) Establish recursive property 2) Solve bottom-up. The 3rd step (construct optimal solution) is only for optimization problems.

---

**S58.** Why is DP more efficient than D&C for computing the Binomial Coefficient?
- A) DP uses less memory
- B) DP uses a greedy strategy
- C) **D&C recomputes the same subproblems exponentially many times; DP computes each only once ✅**
- D) DP uses a different recurrence

> Same recurrence B[i][j] = B[i-1][j-1] + B[i-1][j], but D&C recalculates overlapping calls.

---

**S59.** Given a complete weighted graph with 5 vertices, the brute-force TSP checks ________ tours.
- A) 5! = 120
- B) **4! = 24 ✅**
- C) 2⁵ = 32
- D) 5² = 25

> (n-1)! = 4! = 24 tours (fixing the starting city).

---

**S60.** Given the same 5-vertex TSP, the Held-Karp DP has time complexity proportional to:
- A) 4! = 24
- B) **5² · 2⁵ = 800 ✅**
- C) 5³ = 125
- D) 5 · log 5

> O(n² · 2ⁿ) = 25 · 32 = 800. Compare to brute force's 24 — DP's advantage shows at larger n.

---

## Cross-Unit / Comparison Questions <a name="cross-unit"></a>

> These are the "surprise" questions professors love — comparing algorithms across units.

---

**S61.** Which of the following algorithms has an **every-case** time complexity?
- A) Binary Search
- B) Quick Sort
- C) Sequential Search
- D) **Matrix Multiplication (standard) ✅**

> Also: Add Array Members, Floyd's algorithm. They always do the same number of operations regardless of input values.

---

**S62.** Which of the following algorithms does NOT have an every-case complexity?
- A) Floyd's algorithm
- B) Add Array Members
- C) Standard Matrix Multiplication
- D) **Quick Sort ✅**

> Quick Sort depends on pivot selection → different cases.

---

**S63.** Match the approach:

| Algorithm | Approach |
|-----------|---------|
| Merge Sort | ? |
| Floyd's Algorithm | ? |
| Dijkstra's Algorithm | ? |

- A) All are Divide & Conquer
- B) All are Dynamic Programming
- C) **Merge Sort = D&C, Floyd's = DP, Dijkstra's = Greedy ✅**
- D) Merge Sort = Greedy, Floyd's = D&C, Dijkstra's = DP

---

**S64.** Which algorithm has O(n log n) time complexity in ALL cases?
- A) Quick Sort and Merge Sort
- B) **Merge Sort only (among the listed) ✅** — Quick Sort is O(n²) worst case
- C) Binary Search and Merge Sort
- D) Quick Sort and Binary Search

---

**S65.** A professor asks: "Compare Floyd's algorithm and Dijkstra's algorithm." Which statement is INCORRECT?
- A) Floyd finds all-pairs shortest paths; Dijkstra finds single-source shortest paths
- B) Floyd allows negative edge weights; Dijkstra does not
- C) Floyd is O(n³); Dijkstra is O(n²) or O((V+E) log V) with a priority queue
- D) **Floyd uses a Greedy approach; Dijkstra uses Dynamic Programming ✅**

> It's the opposite: Floyd = DP, Dijkstra = Greedy.

---

**S66.** Which of the following is TRUE?
- A) Merge Sort is in-place and Quick Sort is not
- B) Both Merge Sort and Quick Sort are in-place
- C) Neither is in-place
- D) **Quick Sort is in-place and Merge Sort (Alg 2.2) is NOT in-place ✅**

---

**S67.** An algorithm with T(n) = 2ⁿ is ________ than an algorithm with T(n) = n⁵ for large n.
- A) Faster
- B) The same
- C) **Slower (less efficient) ✅**
- D) Cannot be determined

> Exponential (2ⁿ) always eventually exceeds any polynomial (n⁵).

---

**S68.** Which of the following correctly describes the relationship?
- A) O(n²) ⊂ O(n) — every O(n²) function is also O(n)
- B) **O(n) ⊂ O(n²) — every O(n) function is also O(n²) ✅**
- C) O(n) = O(n²)
- D) They are unrelated

> If g(n) ≤ cn for large n, then certainly g(n) ≤ cn² for large n. O(n) is a subset of O(n²).

---

**S69.** If an algorithm is Θ(n log n), which of the following is TRUE?
- A) It is NOT in O(n²)
- B) It is NOT in Ω(n)
- C) **It IS in both O(n²) and Ω(n) ✅**
- D) It is in O(n) and Ω(n²)

> Θ(n log n) → O(n log n) ⊂ O(n²) ✓, and Ω(n log n) ⊃ Ω(n) ✓.

---

**S70.** A problem is called ________ if no polynomial-time algorithm is known for it, and finding one would prove P = NP.
- A) Trivial
- B) Decidable
- C) **NP-hard / NP-complete ✅**
- D) Galactic

> TSP (decision version) is a classic NP-complete problem.

---

## Tricky True/False — "Exam Traps" Edition <a name="traps"></a>

---

**S71.** Merge Sort's worst case is better than Quick Sort's worst case. (True/False)
- **True ✅** — Merge Sort worst = O(n log n); Quick Sort worst = O(n²).

---

**S72.** Quick Sort's average case is better than Merge Sort's average case. (True/False)
- **False ✅** — Both are Θ(n log n) on average. However, Quick Sort often has smaller constants in practice due to being in-place (better cache performance), but asymptotically they're equal.

---

**S73.** Floyd's algorithm can detect negative-weight cycles. (True/False)
- **True ✅** — If D[i][i] < 0 after running Floyd's, there's a negative-weight cycle through vertex i.

---

**S74.** Strassen's algorithm is a Divide and Conquer algorithm. (True/False)
- **True ✅** — It divides matrices into 4 submatrices and recursively multiplies.

---

**S75.** In Floyd's algorithm, we can skip updating D[i][j] when i = k or j = k. (True/False)
- **True ✅** — D(k)[i][k] = D(k-1)[i][k] and D(k)[k][j] = D(k-1)[k][j]. The row k and column k don't change in iteration k.

---

**S76.** The Binomial Coefficient B[n][0] = 0 for all n. (True/False)
- **False ✅** — B[n][0] = **1** for all n. (There's exactly 1 way to choose 0 items from n.)

---

**S77.** B[n][n] = n. (True/False)
- **False ✅** — B[n][n] = **1**. (There's exactly 1 way to choose all n items from n.)

---

**S78.** DP is always more efficient than Divide and Conquer. (True/False)
- **False ✅** — DP is more efficient only when there are **overlapping subproblems**. For problems without overlapping subproblems (e.g., Merge Sort), D&C is perfectly fine.

---

**S79.** An algorithm with O(n² · 2ⁿ) is polynomial. (True/False)
- **False ✅** — The 2ⁿ factor makes it exponential. The n² multiplier doesn't change that.

---

**S80.** If algorithm A is O(n²) and algorithm B is O(n log n), then B is always faster than A for any input. (True/False)
- **False ✅** — Big-O describes **asymptotic** behavior. For small n, A could be faster due to smaller constants. B is only guaranteed faster for **sufficiently large** n.

---

*Combined with the original 80 questions, you now have 140 MCQs. No surprises on quiz day!* 🔥
