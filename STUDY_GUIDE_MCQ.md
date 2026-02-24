# CMPS323 – Algorithms MCQ Study Guide
## Units 1, 2 & 3 — Quiz Preparation

> All questions below are drawn from lecture slides, past quiz documents, and exercises in this repository. Answers are revealed below each question. ✅ = Correct

---

## TABLE OF CONTENTS
1. [Unit 1 — Algorithm Efficiency, Analysis & Order](#unit-1)
2. [Unit 2 — Divide and Conquer](#unit-2)
3. [Unit 3 — Dynamic Programming](#unit-3)
4. [Quick Reference Cheat Sheet](#cheat-sheet)

---

## UNIT 1 — Algorithm Efficiency, Analysis & Order <a name="unit-1"></a>

### Key Concepts
| Term | Definition |
|------|-----------|
| **T(n)** | Number of times the basic operation is done for an instance of size n |
| **W(n)** | **Worst-case** time complexity — maximum number of times the basic operation is ever done |
| **B(n)** | **Best-case** time complexity — minimum number of times |
| **A(n)** | **Average-case** time complexity |
| **Every-case** | Algorithm always does the same number of basic operations for every instance of size n |
| **O(f(n))** | Big-O = **upper bound** — g(n) ≤ c·f(n) for all n ≥ N |
| **Ω(f(n))** | Omega = **lower bound** — g(n) ≥ c·f(n) for all n ≥ N |
| **Θ(f(n))** | Theta = **tight bound** = O(f(n)) ∩ Ω(f(n)) — c₁·f(n) ≤ g(n) ≤ c₂·f(n) |

### Complexity Order (Best → Worst)
```
Θ(1) < Θ(log n) < Θ(n) < Θ(n log n) < Θ(n²) < Θ(n³) < Θ(aⁿ) < Θ(n!)
```

---

### MCQ — Unit 1

**Q1.** Variables are called ________ to the problem.  
- A) Instances  
- B) **Parameters ✅**  
- C) Algorithms  
- D) Complexities  

---

**Q2.** Each specific assignment of values to the parameters is called an ________ of the problem.  
- A) Algorithm  
- B) Function  
- C) **Instance ✅**  
- D) Parameter  

---

**Q3.** The step-by-step procedure to solve a problem is called a(n):  
- A) Program  
- B) Instance  
- C) **Algorithm ✅**  
- D) Complexity  

---

**Q4.** A problem can be solved by only one algorithm. (True/False)  
- **False ✅** — Multiple algorithms can solve the same problem.

---

**Q5.** Sequential search appears to be much more efficient than binary search. (True/False)  
- **False ✅** — Binary search is more efficient (O(log n) vs O(n)).

---

**Q6.** Algorithm analysis measures the efficiency of an algorithm as the ________ becomes large.  
- A) Output size  
- B) Constant  
- C) **Input size ✅**  
- D) Number of loops  

---

**Q7.** T(n) is defined as:  
- A) Worst-case complexity  
- B) Best-case complexity  
- C) **Number of times the algorithm does the basic operation for an instance of size n ✅**  
- D) The average input size  

---

**Q8.** W(n) is defined as the **minimum** number of times the algorithm will ever do its basic operation for an input size of n. (True/False)  
- **False ✅** — W(n) is the **MAXIMUM** (worst-case). B(n) is the minimum.

---

**Q9.** A(n) is called the average-case time complexity of the algorithm. (True/False)  
- **True ✅**

---

**Q10.** Algorithms with time complexities such as n and 100n are called ________ algorithms.  
- A) Quadratic-time  
- B) Cubic-time  
- C) **Linear-time ✅**  
- D) Logarithmic-time  

---

**Q11.** Algorithms with time complexities such as n² are called quadratic-time algorithms. (True/False)  
- **True ✅**

---

**Q12.** Any quadratic-time algorithm is eventually more efficient than any linear-time algorithm. (True/False)  
- **False ✅** — Any **linear-time** algorithm is eventually more efficient than any quadratic-time algorithm.

---

**Q13.** Functions such as 5n² and 5n² + 100 are called ________ functions.  
- A) Complete-quadratic  
- B) **Pure-quadratic ✅**  
- C) Linear  
- D) Cubic  

> 💡 *Pure-quadratic*: no linear term. *Complete-quadratic*: has a linear term (e.g., 0.1n² + n + 100).

---

**Q14.** ________ assumes something is true, then does manipulations that lead to a result that is not true.  
- A) Mathematical induction  
- B) Direct proof  
- C) **Proof by contradiction ✅**  
- D) Proof by substitution  

---

**Q15.** Big-O notation provides a(n) ________ bound on a function.  
- A) Lower  
- B) Tight  
- C) **Upper ✅**  
- D) Average  

---

**Q16.** Omega (Ω) notation provides a(n) ________ bound on a function.  
- A) Upper  
- B) Tight  
- C) **Lower ✅**  
- D) Average  

---

**Q17.** Theta (Θ) notation provides a(n) ________ bound on a function.  
- A) Upper  
- B) Lower  
- C) **Tight ✅**  
- D) Average  

---

**Q18.** Which of the following is the correct mathematical definition of Big-O?  
- A) g(n) ≥ c·f(n) for all n ≥ N  
- B) c·f(n) ≤ g(n) ≤ d·f(n) for all n ≥ N  
- C) **g(n) ≤ c·f(n) for all n ≥ N ✅**  
- D) g(n) = c·f(n) for all n ≥ N  

---

**Q19.** Is n² + 10n ∈ O(n²)? (True/False)  
- **True ✅** — Because n² + 10n ≤ 11n² for n ≥ 1. Use c = 11, N = 1.

---

**Q20.** Is 5n² ∈ Ω(n²)? (True/False)  
- **True ✅** — Because 5n² ≥ 1·n². Use c = 1, N = 0.

---

**Q21.** Which complexity function grows faster: Θ(n log n) or Θ(n²)?  
- **Θ(n²) ✅** — n² grows faster than n log n for large n.

---

**Q22.** For Add Array Members, what is T(n)?  
- A) n²  
- B) n³  
- C) **n ✅**  
- D) log n  

---

**Q23.** For Matrix Multiplication (standard), what is T(n)?  
- A) n  
- B) n²  
- C) **n³ ✅**  
- D) n log n  

> Basic operation: multiplication in the innermost loop. Three nested loops → n³.

---

**Q24.** For Sequential Search, what is the worst-case time complexity W(n)?  
- A) 1  
- B) log n  
- C) n log n  
- D) **n ✅**  

---

**Q25.** For Sequential Search, what is the best-case time complexity B(n)?  
- A) n  
- B) log n  
- C) **1 ✅**  
- D) n²  

---

**Q26.** Θ(f(n)) = O(f(n)) ∩ Ω(f(n)). (True/False)  
- **True ✅**

---

**Q27.** Which of the following is NOT in O(n²)?  
- A) n  
- B) 5n² + 100  
- C) n log n  
- D) **n³ ✅**  

> n³ grows faster than n² and is not O(n²).

---

## UNIT 2 — Divide and Conquer <a name="unit-2"></a>

### Key Concepts
| Algorithm | Time Complexity | Notes |
|-----------|----------------|-------|
| **Binary Search** | O(log n) worst-case | Recursive uses more memory/slower than iterative |
| **Merge Sort** | Θ(n log n) all cases | In-place? No (uses extra arrays U and V) |
| **Quick Sort** | O(n²) worst, Θ(n log n) avg | Worst case: array already sorted |
| **Standard Matrix Mult.** | Θ(n³) | n multiplications per row × row × col |
| **Strassen Matrix Mult.** | Θ(n^2.81) multiplications | 7 multiplications, 18 add/sub per 2×2 split |
| **Large Integer Mult.** | Divide until threshold | Uses n/2 digit splits |

### Divide-and-Conquer Pattern
- **Top-down** approach
- Divides into **two or more smaller** instances of the **same type**
- Steps: **Divide → Conquer → Obtain (Combine)**

---

### MCQ — Unit 2

**Q28.** Iterative algorithms execute faster than recursive ones because no ________ needs to be maintained.  
- A) Queue  
- B) Array  
- C) **Stack ✅**  
- D) Tree  

---

**Q29.** Divide and conquer divides an instance of a problem into ________ instances.  
- A) One larger  
- B) **Two or more smaller ✅**  
- C) Exactly two equal  
- D) Three or more larger  

---

**Q30.** Bottom-up is to get a solution to a top-level instance by going down and obtaining solutions to smaller instances. (True/False)  
- **False ✅** — This describes **top-down**. Bottom-up solves smaller instances first and builds up.

---

**Q31.** Divide-conquer-obtain are the main steps of the divide and conquer strategy. (True/False)  
- **True ✅**

---

**Q32.** A sorting algorithm that does not use any extra space beyond that needed to store the input is called a(n) ________.  
- A) Recursive sort  
- B) Merge sort  
- C) **In-place sort ✅**  
- D) Stable sort  

---

**Q33.** In Quick Sort, all items smaller than the pivot are placed on the **right** of it. (True/False)  
- **False ✅** — Items smaller than the pivot are placed on the **LEFT**.

---

**Q34.** In Quick Sort, the partitioning of the array is done by the ________ procedure.  
- A) Merge  
- B) Split  
- C) **Partition ✅**  
- D) Divide  

---

**Q35.** In the good condition (average-case) performance of Quick Sort we get O(n log n). (True/False)  
- **True ✅**

---

**Q36.** The average-case time complexity of Quick Sort is Θ(n log n). (True/False)  
- **True ✅**

---

**Q37.** The worst case of Quick Sort is O(n²). (True/False)  
- **True ✅** — Occurs when the array is already sorted and we always pick the first element as pivot.

---

**Q38.** When does the worst case of Quick Sort occur?  
- A) When the array is in random order  
- B) When the array is reversed  
- C) **When the array is already sorted (in non-decreasing order) ✅**  
- D) When all elements are equal  

---

**Q39.** The time complexity of Merge Sort is O(n log n) in:  
- A) Best case only  
- B) Average case only  
- C) Worst case only  
- D) **All cases ✅**  

> Quick Sort is O(n log n) **on average**; Merge Sort is O(n log n) in **all cases**.

---

**Q40.** Strassen's method works best only for 2×2 matrices. (True/False)  
- **False ✅** — Strassen is more efficient for **large** matrices. For 2×2 it is not impressive.

---

**Q41.** In Strassen's method, large matrices are usually divided into ________ sub-matrices.  
- A) Two  
- B) Three  
- C) **Four ✅**  
- D) Eight  

---

**Q42.** Strassen's algorithm is always more efficient than the standard multiplication algorithm in terms of additions/subtractions. (True/False)  
- **False ✅** — Only for **large values of n**. Standard 2×2 multiplication uses 8 multiplications and 4 additions/subtractions, while Strassen uses 7 multiplications and 18 additions/subtractions. For small matrices Strassen's extra additions make it slower.

---

**Q43.** Strassen's algorithm is always more efficient than standard multiplication in terms of multiplications. (True/False)  
- **True ✅** — Strassen uses 7 multiplications per level instead of 8, yielding Θ(n^2.81) vs. Θ(n³).

---

**Q44.** In the multiplication of large integers, the division process is continued until ________ value is reached.  
- A) Zero  
- B) Maximum  
- C) **Threshold ✅**  
- D) Base  

---

**Q45.** Two-way merging means combining two sorted arrays into one sorted array. (True/False)  
- **True ✅**

---

**Q46.** ________ is a sorting technique that sequences a list by continually dividing the list and then moving lower items to one side and higher items to the other.  
- A) Merge Sort  
- B) Bubble Sort  
- C) Binary Search  
- D) **Quick Sort ✅**  

---

**Q47.** ________ divides the array into two halves, which are re-sorted recursively and then merged to create a sorted whole.  
- A) Quick Sort  
- B) Bubble Sort  
- C) **Merge Sort ✅**  
- D) Selection Sort  

---

**Q48.** ________ is a defined data type to mean an array big enough to represent integers that exceed the computer's hardware limit.  
- A) BigArray  
- B) SuperInt  
- C) **Large integer ✅**  
- D) HugeNumber  

---

**Q49.** What is the worst-case time complexity of Binary Search?  
- A) O(n)  
- B) O(n²)  
- C) O(n log n)  
- D) **O(log n) ✅**  

---

**Q50.** Does Binary Search have an every-case time complexity?  
- **No ✅** — The number of comparisons depends on where the search key is in the array. Worst-case is O(log n).

---

**Q51.** The complexity of Strassen's algorithm for matrix multiplication is:  
- A) Θ(n²)  
- B) Θ(n³)  
- C) **Θ(n^2.81) ✅**  
- D) Θ(n log n)  

---

**Q52.** What is the recurrence relation for Strassen's algorithm (multiplications only)?  
- A) T(n) = 8T(n/2)  
- B) **T(n) = 7T(n/2), T(1) = 1 ✅**  
- C) T(n) = 4T(n/2)  
- D) T(n) = 2T(n/2) + n  

---

**Q53.** The divide-and-conquer technique is a ________ technique.  
- A) Bottom-up  
- B) **Top-down ✅**  
- C) Iterative  
- D) Greedy  

---

**Q54.** Merge Sort Algorithm 2.2 (as described in the textbook) is an in-place sort. (True/False)  
- **False ✅** — It uses extra arrays U and V. It is NOT in-place.

---

**Q55.** In Quick Sort, the pivot item determines the partition. Which item is typically chosen as the pivot?  
- A) Last element  
- B) Middle element  
- C) Random element  
- D) **First element (by convention in the textbook algorithm) ✅**  

---

## UNIT 3 — Dynamic Programming <a name="unit-3"></a>

### Key Concepts
| Concept | Description |
|---------|-------------|
| **Dynamic Programming** | Bottom-up approach; solves small instances first, saves results, retrieves later |
| **vs. Divide & Conquer** | DP is bottom-up; D&C is top-down. DP avoids recomputation of sub-problems |
| **Steps in DP** | 1) Establish recursive property 2) Solve bottom-up |
| **DP for Optimization** | Extra step: 3) Construct optimal solution |
| **Principle of Optimality** | Optimal solution includes optimal solutions to all sub-problems |
| **Binomial Coefficient** | D&C: O(2ⁿ) → DP: O(nk) |
| **Floyd's Algorithm** | Shortest paths all-pairs; O(n³); uses D(k) matrix recurrence |
| **TSP (Held-Karp)** | O(n²·2ⁿ); much better than brute-force O((n-1)!) |

### Floyd's Recurrence
```
D(k)[i][j] = min( D(k-1)[i][j],  D(k-1)[i][k] + D(k-1)[k][j] )
```
- D(0) = adjacency matrix W
- D(n) = final shortest-path matrix

### Binomial Coefficient Recurrence
```
B[i][j] = 1                           if j = 0 or j = i
B[i][j] = B[i-1][j-1] + B[i-1][j]    if 0 < j < i
```

---

### MCQ — Unit 3

**Q56.** Dynamic Programming is a ________ approach.  
- A) Top-down  
- B) Greedy  
- C) **Bottom-up ✅**  
- D) Recursive  

---

**Q57.** Dynamic Programming solves smaller instances first and saves results for later reuse instead of recomputing them. (True/False)  
- **True ✅**

---

**Q58.** Dynamic programming is similar to divide-and-conquer in that:  
- A) Both are top-down approaches  
- B) Both recompute subproblems multiple times  
- C) **Both find a recursive property that divides a problem into smaller instances ✅**  
- D) Both use greedy selection  

---

**Q59.** The key difference between Dynamic Programming and Divide-and-Conquer is:  
- A) D&C solves smaller instances first  
- B) DP is always faster  
- C) **DP iteratively solves each smaller instance once and saves results; D&C may recompute ✅**  
- D) D&C cannot be applied to optimization problems  

---

**Q60.** The time complexity of computing the Binomial Coefficient using Divide-and-Conquer (recursive) is:  
- A) O(nk)  
- B) O(n²)  
- C) **O(2ⁿ) ✅**  
- D) O(n log n)  

---

**Q61.** The time complexity of computing the Binomial Coefficient using Dynamic Programming is:  
- A) O(2ⁿ)  
- B) O(n²)  
- C) O(n log n)  
- D) **O(nk) ✅**  

---

**Q62.** In Pascal's Triangle / Binomial Coefficient DP, what is B[4][2]?  
- A) 4  
- B) 8  
- C) **6 ✅**  
- D) 3  

> Pascal's Triangle build-up: B[2][1]=2, B[3][1]=3, B[3][2]=3, so B[4][2] = B[3][1] + B[3][2] = 3 + 3 = **6**

---

**Q63.** Floyd's algorithm computes:  
- A) Shortest path from one source to all nodes  
- B) Minimum spanning tree  
- C) **Shortest paths between all pairs of vertices ✅**  
- D) Topological ordering  

---

**Q64.** The time complexity of Floyd's algorithm is:  
- A) O(n²)  
- B) O(n log n)  
- C) **O(n³) ✅**  
- D) O(n² log n)  

---

**Q65.** In Floyd's algorithm, D(0) is initialized to:  
- A) All zeros  
- B) All infinity  
- C) **The adjacency/weight matrix W ✅**  
- D) The identity matrix  

---

**Q66.** The recurrence for Floyd's algorithm is:  
- A) D(k)[i][j] = D(k-1)[i][k] + D(k-1)[k][j]  
- B) **D(k)[i][j] = min(D(k-1)[i][j], D(k-1)[i][k] + D(k-1)[k][j]) ✅**  
- C) D(k)[i][j] = max(D(k-1)[i][j], D(k-1)[i][k] + D(k-1)[k][j])  
- D) D(k)[i][j] = D(k-1)[i][j] + D(k-1)[i][k]  

---

**Q67.** In Floyd's algorithm, P[i][j] stores:  
- A) The weight of edge (i,j)  
- B) The number of vertices on the path  
- C) **The highest-index intermediate vertex on the shortest path from vi to vj ✅**  
- D) The destination vertex  

---

**Q68.** The Principle of Optimality states that an optimal solution to a problem always includes optimal solutions to all sub-problems. (True/False)  
- **True ✅**

---

**Q69.** Does the Principle of Optimality apply to the Longest Path problem?  
- **No ✅** — The longest path from v1 to v4 may not contain the longest path between intermediate vertices.

---

**Q70.** The Traveling Salesperson Problem (TSP) requires a tour that:  
- A) Visits some cities at least once  
- B) **Starts and ends at the same city, visiting each other city exactly once ✅**  
- C) Finds the shortest path between two cities  
- D) Visits all cities in alphabetical order  

---

**Q71.** The brute-force (trivial) algorithm for TSP has a complexity of:  
- A) O(n²)  
- B) O(2ⁿ)  
- C) O(n³)  
- D) **O((n-1)!) ✅**  

---

**Q72.** The Held-Karp dynamic programming algorithm for TSP has a time complexity of:  
- A) O(n³)  
- B) O(n!)  
- C) **O(n² · 2ⁿ) ✅**  
- D) O(n log n)  

> Still exponential, but much better than O((n-1)!).

---

**Q73.** Dynamic Programming for optimization problems requires ________ steps.  
- A) 1  
- B) 2  
- C) **3 ✅**  
- D) 4  

> Steps: 1) Establish recursive property 2) Compute optimal solution bottom-up 3) Construct optimal solution

---

**Q74.** Floyd's algorithm allows negative edge weights. (True/False)  
- **True ✅** — Unlike Dijkstra's algorithm.

---

**Q75.** Dijkstra's algorithm finds:  
- A) Shortest path between all pairs  
- B) **Shortest path from one node to all nodes (no negative edges) ✅**  
- C) Minimum spanning tree  
- D) Topological sort  

---

**Q76.** Which of the following uses a Greedy approach?  
- A) Floyd-Warshall  
- B) Bellman-Ford  
- C) **Dijkstra's Algorithm ✅**  
- D) Held-Karp  

---

**Q77.** Dynamic programming sometimes provides an efficient solution to a problem for which divide-and-conquer produces an ________ runtime.  
- A) Linear  
- B) Polynomial  
- C) **Exponential ✅**  
- D) Logarithmic  

---

**Q78.** In the TSP, what is D[vi][A]?  
- A) Distance from v1 to vi  
- B) Number of edges in set A  
- C) **Length of the shortest path from vi to v1 passing through each vertex in A exactly once ✅**  
- D) The weight matrix  

---

**Q79.** What is a "galactic algorithm"?  
- A) An algorithm used in space navigation  
- B) **An algorithm with excellent asymptotic behavior but impractical due to large constants ✅**  
- C) An algorithm that runs in O(n) time  
- D) Any algorithm with O(n log n) complexity  

---

**Q80.** Which approach is NOT suitable for large TSP instances (n > 20)?  
- A) Genetic Algorithms  
- B) Simulated Annealing  
- C) Greedy Algorithms  
- D) **Dynamic Programming (Held-Karp) ✅** *(too slow due to O(n² · 2ⁿ))*  

---

## QUICK REFERENCE CHEAT SHEET <a name="cheat-sheet"></a>

### Algorithm Complexities at a Glance
```
Sequential Search   : W(n) = n,        B(n) = 1
Binary Search       : W(n) = O(log n), B(n) = 1
Add Array Members   : T(n) = n         (every-case)
Matrix Mult (std)   : T(n) = n³        (every-case)
Merge Sort          : T(n) = n log n   (all cases)
Quick Sort          : W(n) = n²,       A(n) = n log n
Strassen Mult       : T(n) = n^2.81    (multiplications)
Binomial (D&C)      : O(2ⁿ)
Binomial (DP)       : O(nk)
Floyd's Shortest    : T(n) = n³        (every-case)
TSP Brute Force     : O((n-1)!)
TSP Held-Karp       : O(n²·2ⁿ)
```

### Common True/False Traps
| Statement | Answer | Why |
|-----------|--------|-----|
| W(n) = minimum times basic op is done | **FALSE** | W(n) = **MAXIMUM** (worst-case); B(n) = minimum |
| Any quadratic-time alg. is eventually more efficient than linear | **FALSE** | It's the **opposite**: linear > quadratic for large n |
| Quick Sort all items < pivot go RIGHT | **FALSE** | They go **LEFT** |
| Strassen is always better in additions/subtractions | **FALSE** | Only for **large** n |
| Merge Sort is in-place (Alg. 2.2) | **FALSE** | Uses extra arrays U and V |
| Bottom-up = top-down | **FALSE** | Top-down goes from large → small; Bottom-up goes small → large |
| Binary Search has every-case complexity | **FALSE** | Depends on input values (where x is located) |
| Principle of Optimality holds for longest path | **FALSE** | Counter-example exists |
| Floyd allows negative edges | **TRUE** | Unlike Dijkstra |
| TSP Held-Karp is polynomial | **FALSE** | Still exponential O(n²·2ⁿ), just better than brute force |

### Big-O Membership Examples
- n² + 10n ∈ **O(n²)** and **Ω(n²)** → therefore ∈ **Θ(n²)**
- n ∈ **O(n²)** (upper bound, but not tight)
- n³ ∈ **Ω(n²)** (lower bound, but not tight)
- 5n + 7 ∉ Ω(n²) and 4n³ + 3n² ∉ O(n²) → neither is in **Θ(n²)**

### Proof of Big-O: What You Need
To show g(n) ∈ O(f(n)), find **c > 0** and **N ≥ 0** such that **g(n) ≤ c·f(n)** for all n ≥ N.

### Floyd's Algorithm — Step by Step
1. Set D = W (weight matrix)  
2. For k = 1 to n: for i = 1 to n: for j = 1 to n:  
   `D[i][j] = min(D[i][j], D[i][k] + D[k][j])`
3. To get paths, maintain P[i][j] = k when shortest path through k is found

### Dynamic Programming — When to Use
✅ When D&C leads to exponential time due to **overlapping sub-problems**  
✅ When the **Principle of Optimality** holds  
✅ For optimization problems (shortest path, TSP, binomial, Fibonacci)

---

*Good luck on your quiz! Focus especially on the True/False traps in the cheat sheet — those are the most common mistakes!* 🎯
