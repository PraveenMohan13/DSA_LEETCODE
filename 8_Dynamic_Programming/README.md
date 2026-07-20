
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
Memoization
•	Approach: Top-down (recursive).<br>
•	How it works: Uses recursion to solve the problem by breaking it into subproblems. Results of subproblems are stored (cached) in a data structure like a hash table or array.<br>
•	Execution: Solves subproblems on demand, only when needed.<br>
•	Advantages:<br>
o	Easier to implement if the problem has a natural recursive structure.<br>
o	Efficient if not all subproblems need to be solved (sparse subproblem space).<br>
•	Disadvantages:<br>
o	Recursive overhead can slow down the solution.<br>
o	Risk of stack overflow with deep recursion.<br>
•	Space usage: Requires extra space for recursion call stack and storage of results.<br>
Tabulation<br>
•	Approach: Bottom-up (iterative).<br>
•	How it works: Solves all subproblems iteratively starting from the smallest, building up solutions in a table or array until the full problem is solved.<br>
•	Execution: All subproblems are solved regardless of need, in a specific order.<br>
•	Advantages:<br>
o	Faster in practice due to no recursion overhead.<br>
o	No risk of stack overflow.<br>
o	Often more space efficient in terms of call stack.<br>
•	Disadvantages:<br>
o	Code can be more complex and less intuitive than memoization.<br>
o	Solves all subproblems even if some are unnecessary.<br>
•	Space usage: Only requires space for the DP table.<br>
Summary Comparison:<br>
•Aspect	Memoization	Tabulation<br>
•Approach	Top-down (recursive)	Bottom-up (iterative)<br>
•Execution Order	Solves on demand	Solves all subproblems systematically<br>
•Implementation	Easier with recursion	Iterative, sometimes more complex<br>
•Speed	Slower due to recursive overhead	Faster due to iteration<br>
•Space (call stack)	Uses extra space for recursion	No recursion stack space needed<br>
•Applicability	Useful for sparse subproblems	Useful when all subproblems needed<br>
•Risk	Stack overflow possible	No stack overflow risk<br>

•Both are ways to implement dynamic programming to avoid repeated computations and optimize recursive problems, but the choice depends on the problem's nature and environment constraints


<!-- problem:end -->
