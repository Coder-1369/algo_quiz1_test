# CMPS323 — Extra MCQ Practice Bank
## 100+ New Sample Questions (Units 1, 2 & 3)

> These questions go **beyond** what appeared in the PDFs/slides — they test the same concepts from new angles. Answers follow each question. Use the 💡 hints on tricky ones.

---

## TABLE OF CONTENTS
1. [Unit 1 — Algorithm Efficiency, Analysis & Order (Q1–Q40)](#unit1)
2. [Unit 2 — Divide and Conquer (Q41–Q80)](#unit2)
3. [Unit 3 — Dynamic Programming (Q81–Q120)](#unit3)
4. [Mixed Review — All Units (Q121–Q140)](#mixed)

---

## UNIT 1 — Algorithm Efficiency, Analysis & Order <a name="unit1"></a>

---

**Q1.** The "basic operation" of an algorithm is:
- A) The first line of code executed
- B) **The operation that contributes most to the running time ✅**
- C) A loop counter increment
- D) The return statement

> 💡 For sorting it's a *comparison*; for matrix multiply it's a *multiplication*. The basic operation is what you count to measure efficiency.

---

**Q2.** For the Add Array Members algorithm, why is the time complexity T(n) = n and not T(n) = n + 1?
- A) Because the loop runs n + 1 times
- B) Because we count additions, not loop checks
- C) **Because the basic operation (addition) executes exactly n times, once per element ✅**
- D) Because the return statement adds one extra step

---

**Q3.** Which of the following has an **every-case** time complexity (T(n) exists, not just W/B/A)?
- A) Sequential Search
- B) Binary Search
- C) **Add Array Members ✅**
- D) Quick Sort

> 💡 Every-case means the number of basic operations is the *same* for every input of size n. Searching depends on *where* the key is, so it does NOT have every-case complexity.

---

**Q4.** In worst-case analysis of Sequential Search, what must be true about the search key x?
- A) x is the first element
- B) x is in the middle
- C) **x is not in the array, or x is the last element ✅**
- D) x appears multiple times

---

**Q5.** Best-case analysis B(n) is used:
- A) Always — it gives the most realistic estimate
- B) **Rarely — best-case rarely reflects typical performance ✅**
- C) Only for sorting algorithms
- D) Only when T(n) does not exist

---

**Q6.** Average-case analysis A(n) is most useful when:
- A) Safety is critical and we need guaranteed performance
- B) **The algorithm is used frequently across many different inputs ✅**
- C) The input is always sorted
- D) We need an upper bound

> 💡 Example: A(n) is used for web search engines, social-media image processing, and general sorting.  Worst-case is preferred for nuclear power plants and encryption.

---

**Q7.** Which complexity analysis is preferred for **safety-critical** systems (e.g., nuclear power plant)?
- A) Average-case
- B) Best-case
- C) **Worst-case ✅**
- D) Every-case

---

**Q8.** Given T₁(n) = n for Algorithm 1 and T₂(n) = n² for Algorithm 2, Algorithm 1 is *always* faster in practice. (True/False)
- **False ✅** — If Algorithm 1 has much higher overhead (e.g., initialization cost), Algorithm 2 may be faster for small n. The crossover occurs at some threshold n₀.

> 💡 From the slides: if Algorithm 1 takes 1000t per basic op and Algorithm 2 takes t, then n × 1000t > n² × t only when n > 1000.

---

**Q9.** The expression 0.1n² + n + 100 is a:
- A) Pure-quadratic function
- B) **Complete-quadratic function ✅**
- C) Linear function
- D) Cubic function

> 💡 *Complete-quadratic* has both n² AND a linear term (n). *Pure-quadratic* has n² but NO linear term.

---

**Q10.** Which term dominates 0.1n³ + 10n² + 5n + 25 for large n?
- A) 10n²
- B) 5n
- C) **0.1n³ ✅**
- D) 25

---

**Q11.** According to the order hierarchy, which of the following grows SLOWEST?
- A) Θ(n log n)
- B) Θ(n²)
- C) **Θ(log n) ✅**
- D) Θ(n)

---

**Q12.** According to the order hierarchy, arrange these from fastest to slowest growth:
n!, 2ⁿ, n³, n log n
- A) n log n < n³ < n! < 2ⁿ
- B) **n log n < n³ < 2ⁿ < n! ✅**
- C) n³ < n log n < 2ⁿ < n!
- D) 2ⁿ < n! < n³ < n log n

---

**Q13.** Is n ∈ O(n²)? (True/False)
- **True ✅** — n ≤ 1 · n² for all n ≥ 1. Use c = 1, N = 1. O(n²) is an *upper bound* — anything below n² is also in O(n²).

---

**Q14.** Is n³ ∈ O(n²)? (True/False)
- **False ✅** — n³ grows faster than n². There is no constant c such that n³ ≤ c·n² for all large n.

---

**Q15.** Is n² ∈ Ω(n)? (True/False)
- **True ✅** — n² ≥ 1·n for all n ≥ 1. n² is at least as large as n, so it satisfies the lower-bound condition.

---

**Q16.** Is 5n + 7 ∈ Θ(n²)?
- **No ✅** — 5n + 7 is NOT in Ω(n²) because for large n, n² grows much faster than 5n + 7. So 5n + 7 ∉ Θ(n²).

---

**Q17.** To prove g(n) ∈ O(f(n)), you must find:
- A) Only c > 0
- B) Only N ≥ 0
- C) **Both c > 0 AND N ≥ 0 such that g(n) ≤ c·f(n) for all n ≥ N ✅**
- D) The exact ratio g(n)/f(n)

---

**Q18.** Show that n² + 10n ∈ O(n²). Which c and N work?
- A) c = 1, N = 0
- B) c = 10, N = 5
- C) **c = 11, N = 1 ✅**
- D) c = 2, N = 100

> 💡 n² + 10n ≤ n² + 10n² = 11n² for n ≥ 1. So c = 11, N = 1 works. (c = 2, N = 10 also works from the original proof.)

---

**Q19.** The notation O(f(n)) describes:
- A) The exact running time
- B) A lower bound on running time
- C) **An upper bound on running time ✅**
- D) The average running time

---

**Q20.** If g(n) ∈ Θ(f(n)), which is ALWAYS true?
- A) g(n) ∈ O(f(n)) only
- B) g(n) ∈ Ω(f(n)) only
- C) **g(n) ∈ O(f(n)) AND g(n) ∈ Ω(f(n)) ✅**
- D) g(n) = f(n)

---

**Q21.** For which input does Sequential Search have **average-case** complexity A(n) = (n+1)/2?
- A) When x is always the last element
- B) When x is always not in the array
- C) **When x is equally likely to be in any position ✅**
- D) When the array is sorted

---

**Q22.** The time complexity of Matrix Multiplication (standard, 3 nested loops) is:
- A) n (linear)
- B) n² (quadratic)
- C) **n³ (cubic) ✅**
- D) n log n

> 💡 Basic operation: multiplication in innermost loop. Three loops each running n times → n × n × n = n³.

---

**Q23.** Which complexity grows FASTER for large n: Θ(n·log n) or Θ(n^1.5)?
- A) **Θ(n^1.5) ✅**
- B) Θ(n·log n)
- C) They grow at the same rate
- D) Depends on the specific constant

> 💡 log n grows slower than n^0.5, so n·log n < n·n^0.5 = n^1.5 for large n.

---

**Q24.** "Proof by contradiction" means:
- A) Proving by direct calculation
- B) Proving using induction
- C) **Assuming something is true and showing the assumption leads to a false result ✅**
- D) Substituting values to verify

---

**Q25.** Which of the following pairs are BOTH in Θ(n²)?
- A) n and n²
- B) **5n² + 3n and 0.1n² + 100 ✅**
- C) n³ and n²
- D) n log n and n²

> 💡 Both 5n² + 3n and 0.1n² + 100 have n² as the dominant term → same order → both in Θ(n²).

---

**Q26.** If T(n) = n for Algorithm 1 (with overhead cost 1000t per step) and T(n) = n² for Algorithm 2 (with overhead t per step), at what threshold n does Algorithm **1** (linear) become MORE efficient than Algorithm 2?
- A) n > 100
- B) n > 500
- C) **n > 1000 ✅**
- D) n > 10,000

> 💡 Algorithm 1 takes n×1000t; Algorithm 2 takes n²×t. Algorithm 1 is faster when n×1000t < n²×t → divide both sides by n×t → 1000 < n. So Algorithm 1 wins for **n > 1000**. For n < 1000, the quadratic Algorithm 2 is actually faster due to lower overhead.

---

**Q27.** Θ(n²) contains:
- A) Only functions equal to n²
- B) **All functions that grow at the same rate as n² (upper AND lower bounded by n²) ✅**
- C) All functions ≤ n²
- D) All functions ≥ n²

---

**Q28.** An algorithm is called a "linear-time algorithm" when its complexity is:
- A) T(n) = 1
- B) T(n) = log n
- C) **T(n) = cn for some constant c ✅**
- D) T(n) = n²

---

**Q29.** True or False: 4n³ + 3n² ∈ O(n²).
- **False ✅** — 4n³ + 3n² cannot be upper-bounded by c·n² for large n, because 4n³ grows faster than any constant multiple of n².

---

**Q30.** Which of the following is in O(n²) but NOT in Ω(n²)?
- A) n²
- B) 5n² + 1
- C) **n ✅**
- D) 0.1n² + 1000n

> 💡 n ∈ O(n²) since n ≤ 1·n², but n ∉ Ω(n²) because n grows much slower than n². So n ∉ Θ(n²).

---

**Q31.** The **input size** for Matrix Multiplication is defined as:
- A) The number of elements in a single row
- B) **n, the number of rows (or columns) of the n×n matrix ✅**
- C) n², the total number of matrix elements
- D) n³, the number of multiplications

---

**Q32.** Which algorithm does NOT have every-case complexity?
- A) Add Array Members
- B) Matrix Multiplication
- C) **Sequential Search ✅**
- D) Add Array Members OR Matrix Multiplication

---

**Q33.** If g(n) = 3n + 7, then g(n) ∈ O(n). To prove this, we need:
- A) c = 3, N = 7
- B) **c = 4, N = 7 ✅** *(since 3n + 7 ≤ 4n when n ≥ 7)*
- C) c = 1, N = 100
- D) c = 7, N = 3

> 💡 3n + 7 ≤ 4n iff 7 ≤ n. So c = 4, N = 7 works.

---

**Q34.** Which term can be "thrown away" when classifying 0.1n³ + 10n² + 5n + 25?
- A) 0.1n³ (leading term)
- B) **10n² + 5n + 25 (lower-order terms) ✅**
- C) Nothing — all terms matter
- D) Only the constant 25

---

**Q35.** A sorting algorithm that uses O(1) extra memory is called:
- A) Stable sort
- B) Recursive sort
- C) **In-place sort ✅**
- D) Linear sort

---

**Q36.** True or False: If g(n) ∈ O(f(n)) and g(n) ∈ Ω(f(n)), then g(n) ∈ Θ(f(n)).
- **True ✅** — This is the definition of Θ: it equals O ∩ Ω.

---

**Q37.** The growth order from slowest to fastest is:
- A) 1, n, log n, n log n, n², n³, 2ⁿ, n!
- B) **1, log n, n, n log n, n², n³, 2ⁿ, n! ✅**
- C) 1, log n, n log n, n, n², n³, n!, 2ⁿ
- D) log n, 1, n, n², n log n, n³, 2ⁿ, n!

---

**Q38.** An algorithm has T(n) = n². A Θ(n²) algorithm takes 31.7 years for n = 1 billion. Which is true?
- A) A Θ(n³) algorithm would be faster
- B) **A Θ(n log n) algorithm takes only ~30 seconds for the same input ✅**
- C) A Θ(2ⁿ) algorithm would be practical
- D) All algorithms take similar time for n = 1 billion

---

**Q39.** True or False: The variable used to measure input size can differ by algorithm.
- **True ✅** — For sorting arrays it's the array length n; for matrix operations it's the matrix dimension n; for graphs it might be number of vertices or edges.

---

**Q40.** If n² + 10n ∈ O(n²), which values of c and N satisfy the definition? (Select all that apply)
- A) **c = 2, N = 10 ✅**
- B) **c = 11, N = 1 ✅**
- C) c = 0.5, N = 100 *(this does NOT work since 0.5n² < n² + 10n)*
- D) **c = 100, N = 0 ✅**

> 💡 The definition just requires *some* valid c and N. Any c ≥ 11 with N = 1 works, or c = 2 with N = 10, etc. Multiple solutions are valid.

---

## UNIT 2 — Divide and Conquer <a name="unit2"></a>

---

**Q41.** The three main steps of Divide-and-Conquer are:
- A) Input, Process, Output
- B) Analyze, Design, Test
- C) **Divide, Conquer, Obtain (Combine) ✅**
- D) Search, Sort, Merge

---

**Q42.** A recursive algorithm uses more memory than an iterative one because:
- A) It uses more variables
- B) It reads the array multiple times
- C) **It maintains a call stack for each recursive invocation ✅**
- D) It requires additional arrays

---

**Q43.** Binary Search requires the input array to be:
- A) Randomized
- B) Partially sorted
- C) **Sorted ✅**
- D) Reversed

---

**Q44.** What is the worst-case number of comparisons in Binary Search for an array of size 8?
- A) 3
- B) **4 ✅** *(⌊log₂ 8⌋ + 1 = 3 + 1 = 4)*
- C) 8
- D) 2

> 💡 Worst-case Binary Search = ⌊log₂ n⌋ + 1 comparisons. For n=8: ⌊log₂ 8⌋ + 1 = 3 + 1 = 4.

---

**Q45.** In Binary Search, what happens when the search key is found at the midpoint on the very first comparison?
- A) Worst case
- B) Average case
- C) **Best case ✅**
- D) Every case

---

**Q46.** Merge Sort is stable. What does "stable" mean for a sorting algorithm?
- A) It never crashes
- B) **Equal elements maintain their original relative order ✅**
- C) It uses O(1) extra memory
- D) It always runs in Θ(n log n)

---

**Q47.** Which of the following sorting algorithms is NOT divide-and-conquer?
- A) Merge Sort
- B) Quick Sort
- C) **Bubble Sort ✅**
- D) Both A and B

---

**Q48.** In Quick Sort's partition step, after partitioning around a pivot, the pivot is:
- A) Compared again in subsequent recursive calls
- B) **In its final sorted position ✅**
- C) Moved to the beginning of the array
- D) Discarded

---

**Q49.** What is the recurrence relation for Merge Sort?
- A) T(n) = T(n-1) + n
- B) T(n) = 4T(n/2) + n
- C) **T(n) = 2T(n/2) + n, T(1) = 0 ✅**
- D) T(n) = 2T(n/2), T(1) = 1

> 💡 Merge Sort divides into 2 halves (2T(n/2)) and merges in O(n) time (+n).

---

**Q50.** The worst case of Quick Sort occurs when the pivot is always the:
- A) Median element
- B) Random element
- C) Middle element
- D) **Minimum or maximum element (already sorted input) ✅**

---

**Q51.** In Merge Sort, the "merge" step combines:
- A) All elements into a new array using a stack
- B) Two sorted sub-arrays into one sorted array by repeatedly taking the smaller front element
- C) **Two sorted sub-arrays (U and V) into the original array S ✅**
- D) The pivot with the remaining elements

---

**Q52.** Merge Sort Algorithm 2.2 (from the textbook) uses extra arrays named:
- A) A and B
- B) Left and Right
- C) **U and V ✅**
- D) P and Q

---

**Q53.** For n = 16, the depth (number of levels) of Merge Sort's recursion tree is:
- A) 2
- B) **4 ✅** *(log₂ 16 = 4)*
- C) 8
- D) 16

---

**Q54.** Standard matrix multiplication of two n×n matrices has time complexity:
- A) O(n²)
- B) **O(n³) ✅**
- C) O(n² log n)
- D) O(n^2.81)

---

**Q55.** Strassen's matrix multiplication splits each n×n matrix into ________ sub-matrices of size n/2 × n/2.
- A) Two
- B) **Four ✅**
- C) Six
- D) Eight

---

**Q56.** How many multiplications does Strassen's algorithm use per level (for 2×2 sub-matrices), compared to standard?
- A) Standard: 4, Strassen: 3
- B) **Standard: 8, Strassen: 7 ✅**
- C) Standard: 6, Strassen: 5
- D) Standard: 9, Strassen: 6

> 💡 Strassen saves one multiplication per level: 7 instead of 8. This compounds over recursion to give Θ(n^2.81) instead of Θ(n³).

---

**Q57.** Strassen's algorithm uses more ________ than the standard algorithm at each level.
- A) Multiplications
- B) **Additions/subtractions ✅** *(18 vs. 4)*
- C) Memory accesses
- D) Recursive calls

---

**Q58.** The recurrence relation for standard matrix multiplication is:
- A) T(n) = 7T(n/2)
- B) T(n) = 4T(n/2)
- C) **T(n) = 8T(n/2), T(1) = 1 ✅**
- D) T(n) = 2T(n/2) + n

---

**Q59.** Strassen's algorithm complexity Θ(n^2.81) is computed from:
- A) T(n) = 8T(n/2) → n^log₂8 = n³
- B) **T(n) = 7T(n/2) → n^log₂7 ≈ n^2.807 ✅**
- C) T(n) = 4T(n/2) → n²
- D) T(n) = 6T(n/2) → n^log₂6

---

**Q60.** For which values of n is Strassen's algorithm more efficient than standard matrix multiplication?
- A) For all n ≥ 1
- B) For small n (e.g., n = 2)
- C) **For large n ✅** *(Strassen's extra additions outweigh savings for small n)*
- D) For n that are prime

---

**Q61.** Large integer multiplication uses divide-and-conquer by splitting an n-digit number into:
- A) Four n/4-digit parts
- B) Three n/3-digit parts
- C) **Two n/2-digit parts (top and bottom halves) ✅**
- D) Single digits

---

**Q62.** What does "two-way merging" mean in the context of Merge Sort?
- A) Sorting using two pivots
- B) **Combining two sorted arrays into one sorted array ✅**
- C) Dividing the array into two equal halves
- D) Using two threads to sort

---

**Q63.** Quick Sort partitions using the first element as pivot. For input [3, 1, 4, 1, 5], what is the first pivot?
- A) 1
- B) 4
- C) **3 ✅**
- D) 5

---

**Q64.** After partitioning [3, 1, 4, 1, 5] with pivot = 3 (first element), the left partition contains elements:
- A) [4, 5]
- B) [1, 4, 1]
- C) **[1, 1] ✅** *(elements less than 3)*
- D) [1, 4, 1, 5]

---

**Q65.** In divide-and-conquer, the "conquer" step means:
- A) Divide the problem into sub-problems
- B) **Recursively solve each sub-problem ✅**
- C) Combine the sub-solutions
- D) Find the pivot element

---

**Q66.** Which is FALSE about Binary Search?
- A) It requires a sorted array
- B) It halves the search space each step
- C) **The iterative version is less efficient than the recursive version ✅**
- D) Its worst-case is O(log n)

> 💡 The iterative Binary Search is actually FASTER than recursive because it avoids the call stack overhead.

---

**Q67.** Given a sorted array of 1000 elements, how many comparisons does Binary Search need in the worst case?
- A) 1000
- B) 100
- C) **10 ✅** *(⌊log₂ 1000⌋ + 1 ≈ 9.97 + 1 ≈ 10)*
- D) 500

---

**Q68.** Quick Sort has every-case time complexity. (True/False)
- **False ✅** — Quick Sort has different performance depending on pivot selection: O(n²) worst case, Θ(n log n) average.

---

**Q69.** The "obtain" (combine) step in Merge Sort is:
- A) Selecting the pivot
- B) Recursively sorting sub-arrays
- C) **Merging two sorted sub-arrays back into the original ✅**
- D) Partitioning around the median

---

**Q70.** Why does the recursive Binary Search use more memory than iterative?
- A) It copies the array at each level
- B) **It maintains a call stack frame for each recursive call ✅**
- C) It allocates new arrays at each level
- D) It stores all comparisons in a list

---

**Q71.** Strassen's algorithm is a "galactic algorithm" for 2×2 matrices. True or False?
- **True ✅** — For 2×2, Strassen's 18 add/subtract operations make it SLOWER than standard 4 add/sub. Its advantage only appears for large n.

---

**Q72.** Which sorting algorithm has guaranteed O(n log n) in all cases?
- A) Quick Sort
- B) Bubble Sort
- C) **Merge Sort ✅**
- D) Selection Sort

---

**Q73.** The Divide-and-Conquer approach is categorized as:
- A) Bottom-up
- B) **Top-down ✅**
- C) Greedy
- D) Dynamic

---

**Q74.** In Quick Sort, items EQUAL to the pivot can go:
- A) Only to the left
- B) Only to the right
- C) **Either side — implementation dependent ✅**
- D) They are removed

---

**Q75.** What is the best-case time complexity of Quick Sort?
- A) O(n²)
- B) O(n)
- C) **O(n log n) ✅** *(when pivot always splits array perfectly in half)*
- D) O(1)

---

**Q76.** True or False: Merge Sort is always preferred over Quick Sort because of its guaranteed O(n log n).
- **False ✅** — Quick Sort is often faster in practice due to better cache performance and lower constant factors, even though Merge Sort has better worst-case guarantees.

---

**Q77.** In the context of Divide-and-Conquer for large integer multiplication, when does the division process stop?
- A) When the number has 1 digit
- B) When the number becomes negative
- C) **When the number reaches a predefined threshold ✅**
- D) After exactly log n recursive calls

---

**Q78.** The "Ternary Search" problem (dividing into 3 sub-lists of n/3) is an example of:
- A) Dynamic Programming
- B) Greedy Algorithm
- C) **Divide-and-Conquer ✅**
- D) Backtracking

---

**Q79.** Merge Sort is NOT in-place because it:
- A) Uses a stack for recursion
- B) Creates a temporary pivot variable
- C) **Requires extra arrays U and V of sizes proportional to the input ✅**
- D) Modifies the original array in unpredictable ways

---

**Q80.** Which of these statements about Strassen's algorithm is TRUE?
- A) It uses 8 multiplications and 4 additions per level
- B) It is always faster than standard matrix multiplication
- C) **It uses 7 multiplications and 18 additions/subtractions per level ✅**
- D) It has the same complexity as standard matrix multiplication

---

## UNIT 3 — Dynamic Programming <a name="unit3"></a>

---

**Q81.** The two main steps of Dynamic Programming (non-optimization) are:
- A) Divide and Conquer
- B) **1) Establish recursive property; 2) Solve bottom-up ✅**
- C) Recurse and Memoize
- D) Sort and Search

---

**Q82.** Why does the Divide-and-Conquer approach for computing C(n,k) have O(2ⁿ) complexity?
- A) It uses 2 nested loops
- B) **Each call branches into 2 more calls, and sub-problems are repeatedly solved ✅**
- C) It uses 2n memory
- D) The array is divided into 2 equal halves

> 💡 D&C for binomial coefficient: bin(n,k) = bin(n-1,k-1) + bin(n-1,k). This creates a binary tree where same sub-problems (like bin(n-2,k-1)) are solved multiple times.

---

**Q83.** The Dynamic Programming solution for C(n,k) has complexity O(nk) because:
- A) It uses k recursive calls
- B) **It fills a 2D table of size (n+1)×(k+1) once, reusing results ✅**
- C) It sorts an array of n elements k times
- D) It divides n by k at each step

---

**Q84.** In Pascal's Triangle, B[5][2] = ?
- A) 5
- B) 8
- C) **10 ✅**
- D) 15

> 💡 Build Pascal's triangle: B[5][2] = B[4][1] + B[4][2] = 4 + 6 = 10. (Or use C(5,2) = 10.)

---

**Q85.** In Pascal's Triangle, B[3][3] = ?
- A) 0
- B) 3
- C) **1 ✅**
- D) 6

> 💡 When j = i (k = n), B[i][j] = 1 always. C(3,3) = 1.

---

**Q86.** In Pascal's Triangle, B[0][0] = ?
- A) 0
- B) **1 ✅**
- C) Undefined
- D) ∞

---

**Q87.** Floyd's algorithm is used to find:
- A) Minimum Spanning Tree
- B) Topological Sort
- C) **All-pairs shortest paths ✅**
- D) Single-source shortest paths

---

**Q88.** In Floyd's algorithm, D(k)[i][j] represents:
- A) Weight of edge from vertex i to vertex j
- B) **Length of shortest path from vi to vj using only vertices {v1,...,vk} as intermediates ✅**
- C) Number of edges from vi to vj
- D) The kth row of the adjacency matrix

---

**Q89.** What is D(0) in Floyd's algorithm?
- A) A matrix of all zeros
- B) A matrix of all infinity
- C) **The weight/adjacency matrix W ✅**
- D) The identity matrix

---

**Q90.** What is D(n) in Floyd's algorithm?
- A) The weight matrix W
- B) A matrix of all zeros
- C) **The matrix of actual shortest-path lengths between all pairs ✅**
- D) The path matrix P

---

**Q91.** In Floyd's recurrence, D(k)[i][j] = min(D(k-1)[i][j], D(k-1)[i][k] + D(k-1)[k][j]).
The term D(k-1)[i][k] + D(k-1)[k][j] represents:
- A) The direct edge weight from vi to vj
- B) **The path from vi through vk to vj ✅**
- C) The weight of the kth edge
- D) The sum of all weights in row i

---

**Q92.** True or False: Floyd's algorithm can handle negative edge weights.
- **True ✅** — Unlike Dijkstra's algorithm, Floyd-Warshall handles negative weights (but NOT negative cycles).

---

**Q93.** The matrix P[i][j] in Floyd's algorithm stores:
- A) The direct edge weight
- B) The number of intermediate vertices
- C) **The highest-index intermediate vertex on the shortest path from vi to vj ✅**
- D) Whether a path exists

---

**Q94.** If P[i][j] = 0, what does it mean in Floyd's algorithm?
- A) There is no path from vi to vj
- B) **The shortest path from vi to vj has no intermediate vertices (direct edge) ✅**
- C) The shortest path has infinite length
- D) vi = vj

---

**Q95.** To reconstruct the path from v2 to v5 using Floyd's algorithm with P[2][5] = 4, P[2][4] = 3, P[3][4] = 0, P[4][5] = 0, the path is:
- A) v2 → v5
- B) v2 → v4 → v5
- C) **v2 → v3 → v4 → v5 ✅**
- D) v2 → v4 → v3 → v5

> 💡 P[2][5]=4 means go through v4. P[2][4]=3 means go through v3. P[3][4]=0 and P[4][5]=0 means direct edges. So: v2 → v3 → v4 → v5.

---

**Q96.** Floyd's algorithm time complexity is T(n) = n³. This is because:
- A) It uses two nested loops each of size n
- B) **It has three nested loops, each executing n times ✅**
- C) It solves n² sub-problems each taking O(n)
- D) It sorts n elements using O(n²) per pass

---

**Q97.** True or False: Floyd's algorithm has an every-case time complexity.
- **True ✅** — The three nested loops always execute exactly n³ times regardless of input values.

---

**Q98.** The Traveling Salesperson Problem (TSP) asks for:
- A) The shortest path from one city to another
- B) The minimum spanning tree connecting all cities
- C) **A Hamiltonian circuit (tour) of minimum total weight visiting each city exactly once ✅**
- D) The minimum number of roads to build

---

**Q99.** In TSP, a "tour" is:
- A) Any path between two cities
- B) A path that visits every city at least once
- C) **A cycle that starts and ends at the same city, visiting every other city exactly once ✅**
- D) The shortest path between the most distant cities

---

**Q100.** For TSP with n=4 cities, the brute-force algorithm evaluates how many tours?
- A) 4! = 24
- B) **3! = 6 ✅** *(n-1)! tours*
- C) 2^4 = 16
- D) 4² = 16

> 💡 Brute force TSP = (n-1)! tours. For n=4: (4-1)! = 3! = 6 tours.

---

**Q101.** For TSP with n=5, how many tours does brute force check?
- A) 5! = 120
- B) **4! = 24 ✅**
- C) 2⁵ = 32
- D) 5² = 25

---

**Q102.** The Held-Karp DP algorithm for TSP has complexity O(n²·2ⁿ), which for n=20 is approximately:
- A) 400 (very fast)
- B) 20 million (manageable)
- C) **400 million (borderline) ✅**
- D) Trillion (completely impractical)

> 💡 n²·2ⁿ for n=20: 400 · 1,048,576 ≈ 419 million. Compare to brute force (20-1)! ≈ 1.2 × 10¹⁷.

---

**Q103.** True or False: The Held-Karp DP algorithm for TSP runs in polynomial time.
- **False ✅** — O(n²·2ⁿ) is still exponential (the 2ⁿ term). It's just *much* better than (n-1)!.

---

**Q104.** D[vi][A] in the TSP DP formulation represents:
- A) Distance from v1 to vi
- B) **Length of shortest path from vi to v1 passing through each vertex in A exactly once ✅**
- C) Cost of the minimum spanning tree rooted at vi
- D) Total weight of edges in set A

---

**Q105.** The Principle of Optimality DOES apply to:
- A) Longest path problem
- B) **Shortest path problem ✅**
- C) Maximum clique problem
- D) Longest common subsequence *(trick question — it does apply here too)*

---

**Q106.** True or False: The Principle of Optimality applies to the longest path problem.
- **False ✅** — Counter-example: the longest path from v1 to v4 may pass through v2 and v3, but the sub-path from v1 to v3 might not be the longest path between those two vertices.

---

**Q107.** Dynamic Programming is preferred over Divide-and-Conquer for Binomial Coefficient because:
- A) D&C cannot compute it
- B) **D&C recomputes the same sub-problems exponentially many times ✅**
- C) DP is always faster than D&C
- D) Binomial Coefficient requires bottom-up traversal

---

**Q108.** In the DP table for binomial coefficient, B[i][0] = ________ for all i.
- A) 0
- B) i
- C) **1 ✅**
- D) i!

---

**Q109.** In the DP table for binomial coefficient, B[i][i] = ________ for all i.
- A) 0
- B) i
- C) **1 ✅**
- D) 2^i

---

**Q110.** Which approach does Floyd's Shortest Path algorithm use?
- A) Greedy
- B) Divide-and-Conquer
- C) **Dynamic Programming ✅**
- D) Backtracking

---

**Q111.** Which approach does Dijkstra's algorithm use?
- A) Dynamic Programming
- B) **Greedy ✅**
- C) Divide-and-Conquer
- D) Backtracking

---

**Q112.** A "simple path" in graph theory is:
- A) A path with the minimum number of edges
- B) **A path that never visits the same vertex twice ✅**
- C) A path with equal-weight edges
- D) A directed path

---

**Q113.** For the graph with adjacency matrix W, if W[i][j] = ∞, it means:
- A) There is an edge of weight ∞
- B) **There is no direct edge from vi to vj ✅**
- C) vi = vj
- D) The path is blocked

---

**Q114.** The Fibonacci sequence can be computed in O(n) using:
- A) Divide-and-Conquer
- B) **Dynamic Programming ✅**
- C) Greedy Algorithm
- D) Backtracking

> 💡 Naive recursive Fibonacci is O(2ⁿ) (same problem as binomial coefficient D&C). DP stores results in a table, computing each F(i) once → O(n).

---

**Q115.** In the TSP Held-Karp algorithm, D[vi][∅] (empty set) = ?
- A) 0
- B) ∞
- C) **W[i][1] — the direct edge weight from vi back to v1 ✅**
- D) The shortest path from v1 to vi

---

**Q116.** True or False: For large TSP instances (n > 20), Dynamic Programming (Held-Karp) is the most practical algorithm.
- **False ✅** — For n > 20, Held-Karp becomes too slow (O(n²·2ⁿ)). Approximation algorithms, greedy, or metaheuristics (genetic algorithms, simulated annealing) are used instead.

---

**Q117.** What is the time complexity of the trivial (brute-force) shortest-path algorithm that checks all possible paths?
- A) O(n²)
- B) O(n³)
- C) **Worse than exponential — O(n!) ✅**
- D) O(2ⁿ)

---

**Q118.** Dynamic programming for optimization problems requires 3 steps. The third step (not needed for non-optimization DP) is:
- A) Establishing the recursive property
- B) Computing the optimal value bottom-up
- C) **Constructing the optimal solution (e.g., finding the actual path, not just its length) ✅**
- D) Initializing the base cases

---

**Q119.** True or False: Bellman-Ford is a greedy algorithm.
- **False ✅** — Bellman-Ford uses Dynamic Programming. Dijkstra uses greedy. Bellman-Ford allows negative edge weights; Dijkstra does not.

---

**Q120.** The main advantage of Dynamic Programming over Divide-and-Conquer is:
- A) DP always runs in O(n log n)
- B) DP uses less memory
- C) **DP avoids recomputation by storing sub-problem results (memoization/tabulation) ✅**
- D) DP works on unsorted data

---

## MIXED REVIEW — All Units <a name="mixed"></a>

---

**Q121.** Arrange these algorithms from BEST to WORST time complexity:
Bubble Sort, Merge Sort, Binary Search, Matrix Multiplication (standard)
- A) Matrix Mult < Binary Search < Merge Sort < Bubble Sort
- B) **Binary Search < Merge Sort < Bubble Sort < Matrix Mult ✅**
  *(O(log n) < O(n log n) < O(n²) < O(n³))*
- C) Merge Sort < Bubble Sort < Binary Search < Matrix Mult
- D) All are the same complexity

---

**Q122.** Match each algorithm to its paradigm:
1. Floyd's Algorithm   A. Greedy
2. Quick Sort          B. Dynamic Programming
3. Dijkstra's          C. Divide-and-Conquer

- A) 1-C, 2-B, 3-A
- B) **1-B, 2-C, 3-A ✅**
- C) 1-A, 2-C, 3-B
- D) 1-B, 2-A, 3-C

---

**Q123.** Which of these algorithms has the BEST worst-case time complexity?
- A) Quick Sort — O(n²)
- B) Matrix Multiplication — O(n³)
- C) **Binary Search — O(log n) ✅**
- D) Merge Sort — O(n log n)

---

**Q124.** The "Principle of Optimality" is a requirement for which design technique?
- A) Divide-and-Conquer
- B) Greedy Algorithm
- C) **Dynamic Programming ✅**
- D) Backtracking

---

**Q125.** Which algorithm uses a STACK implicitly during execution?
- A) Floyd's Algorithm
- B) **Recursive Binary Search ✅**
- C) Iterative Binary Search
- D) Floyd's algorithm — it uses a stack

---

**Q126.** If you need to find the shortest path from ONE source to ALL other vertices, and there are NO negative edges, use:
- A) Floyd-Warshall
- B) Bellman-Ford
- C) **Dijkstra's Algorithm ✅**
- D) Held-Karp

---

**Q127.** If you need to find shortest paths between ALL pairs of vertices and negative edges are present, use:
- A) Dijkstra's Algorithm
- B) Held-Karp
- C) **Floyd-Warshall ✅**
- D) Merge Sort

---

**Q128.** Which of the following grows faster than n² but slower than n³?
- A) n log n
- B) n
- C) **n^2.81 (Strassen's complexity) ✅**
- D) 2ⁿ

---

**Q129.** Complete the analogy: "Divide-and-Conquer : Top-down :: Dynamic Programming : ________"
- A) Top-down
- B) **Bottom-up ✅**
- C) Greedy
- D) Recursive

---

**Q130.** A "Hamiltonian Circuit" is the formal graph theory name for:
- A) The shortest path between two vertices
- B) A tree spanning all vertices
- C) **A tour that visits every vertex exactly once and returns to the start ✅**
- D) A cycle of minimum weight

---

**Q131.** True or False: O(n²·2ⁿ) is polynomial time.
- **False ✅** — The 2ⁿ factor makes it exponential. Polynomial time means O(nᵏ) for some constant k.

---

**Q132.** In the context of algorithm analysis, "overhead" refers to:
- A) The basic operation count
- B) **Extra instructions (initialization, loop counters, etc.) not counted in the basic operation ✅**
- C) Memory usage
- D) The return value of the algorithm

---

**Q133.** Which is a better measure of practical performance — T(n), W(n), A(n), or B(n)?
- A) B(n) — best case is always achievable
- B) W(n) — guaranteed upper bound for critical systems
- C) **Depends on the application — W(n) for critical, A(n) for typical use ✅**
- D) T(n) — exact count is always best

---

**Q134.** True or False: 5n + 7 ∈ Ω(n).
- **True ✅** — 5n + 7 ≥ 5n ≥ 5·n for c = 5, N = 0. So it satisfies the lower bound condition.

---

**Q135.** Which algorithm is most suitable for finding all-pairs shortest paths in a weighted directed graph?
- A) Dijkstra (run n times)
- B) Quick Sort
- C) **Floyd-Warshall ✅**
- D) Merge Sort

---

**Q136.** The "galactic algorithm" term describes algorithms where:
- A) The algorithm works in outer space
- B) **The algorithm has excellent asymptotic complexity but impractically large constants ✅**
- C) The algorithm runs faster than light
- D) The algorithm solves NP-hard problems

---

**Q137.** Which sorting algorithm has the SAME complexity in best, average, AND worst case?
- A) Quick Sort
- B) Bubble Sort
- C) **Merge Sort ✅**
- D) Insertion Sort

---

**Q138.** Dynamic programming and divide-and-conquer both:
- A) Use bottom-up computation
- B) Avoid recursion
- C) **Find a recursive property dividing a problem into smaller instances ✅**
- D) Require sorting the input first

---

**Q139.** True or False: A(n) = n for Sequential Search when the search key x is always in the array and equally likely to be in any position.
- **False ✅** — A(n) = (n+1)/2, NOT n. The average position is the middle of the array, not the end.

---

**Q140.** Rank these for finding the shortest tour visiting 10 cities (TSP, n=10):
Brute Force vs. Held-Karp
- A) Brute Force is faster
- B) They are equal
- C) **Held-Karp is much faster: O(n²·2ⁿ) = 10,240 vs. (n-1)! = 362,880 ✅**
- D) Both are impractical for n=10

---

*🎯 Pro tip: Pay special attention to Q3 (every-case), Q9 (pure vs complete quadratic), Q40 (multiple valid c,N), Q56 (Strassen additions), Q82 (why D&C binomial is slow), Q92 (Floyd handles negatives), Q103 (Held-Karp still exponential), and Q106 (longest path fails optimality).*
