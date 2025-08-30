
<!-- problem:start -->

# Dynamic Programming

________________________________________________________________________________________________________________________

Dynamic Programming (DP) is an algorithmic technique used to solve problems
by breaking them down into smaller overlapping subproblems and efficiently
solving each subproblem only once by storing the solutions.
________________________________________________________________________________________________________________________

Core Concepts of Dynamic Programming
Optimal Substructure: The problem's optimal solution can be constructed 
from the optimal solutions of its subproblems.
________________________________________________________________________________________________________________________
Overlapping Subproblems: 
The same smaller subproblems are solved multiple times during recursion or problem solving.
________________________________________________________________________________________________________________________
How DP Works
Divide the problem into smaller subproblems.

Solve each subproblem once and store the result (using a data structure like an array or table).

Use the stored results to build up solutions to bigger subproblems, ultimately reaching the final solution.
________________________________________________________________________________________________________________________

Approaches to DP
Top-Down (Memoization): 
Solve the problem recursively while storing results of subproblems to avoid recomputation.

Bottom-Up (Tabulation): 
Solve subproblems iteratively starting from the smallest, building up to the full problem.
________________________________________________________________________________________________________________________

Dynamic Programming optimizes recursive solutions by avoiding repeated calculations and
is widely used for problems such as Fibonacci numbers, shortest paths, knapsack, and many more.
________________________________________________________________________________________________________________________

Difference between tabulation and memoization:
Tabulation: Bottom-up approach, iterative, pre-fills solutions from smallest to largest subproblems.

Memoization: Top-down approach, recursive, stores results of recursive calls as they occur.

Thus, this solution is a classic example of tabulation in dynamic programming.
________________________________________________________________________________________________________________________

<!-- problem:end -->
