# CMPS 2200 Recitation 06
## Answers

**Name:**__Raymond Liu_______________________


Place all written answers from `recitation-07.md` here for easier grading.



- **2)**
The recurrence for the work `W(n)` of a naive recursive algorithm to compute the `n`th Fibonacci number is:
W(n) = W(n-1) + W(n-2) + O(1)
with base cases:
W(0) = O(1), W(1) = O(1)

The solution to this recurrence is exponential, which means that `W(n)` is `O(2^n)`.
- **3)**
The recurrence for the span `S(n)` of this algorithm is:
S(n) = S(n-1) + O(1)
with base cases:
S(0) = O(1), S(1) = O(1)

This is because the computation of `F_n` depends only on the computation of `F_(n-1)` and `F_(n-2)`, and at each step, you only continue with one of those computations. The solution to this recurrence is linear, `S(n)` is `O(n)`.
- **4)**
By inspecting the `counts` list from the recursive function, an interesting pattern emerges: each Fibonacci number is computed a number of times equal to the Fibonacci sequence itself. This indicates that there is significant redundant computation. For example, `F_2` is computed once, `F_3` is computed twice, `F_4` three times, and so on, leading to the exponential growth in the total number of computations as `n` increases.
- **6)**
In the `fib_top_down` dynamic programming approach, each subproblem `F_i` for `0 <= i <= n` is solved exactly once due to memoization. The work done by the algorithm is `O(n)`, as it performs a constant amount of work for each Fibonacci number computation.

The span of the algorithm is also `O(n)`, since the longest sequence of dependent computations would be the series of additions from `F_1` up to `F_n`.
- **8)**
In the `fib_bottom_up` approach, each Fibonacci number `F_i` is computed exactly once, and each `F_i` is read exactly twice for the computation of subsequent numbers. The work for this algorithm is `O(n)`, as it involves a single loop performing a constant amount of work for each `i` from `1` to `n`.

The span is also `O(n)`, due to the sequential dependency of the computations from `F_0` up to `F_n`, even though each step depends only on the previous two computed values.