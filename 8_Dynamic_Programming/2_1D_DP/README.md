
<!-- problem:start -->

# 1D_DP_Program_Flow


## 1D Dynamic Programming LeetCode Problems - Practice Flow
________________________________________
📄 Beginner Level (Basic 1D DP Pattern)<br>
1) 70. Climbing Stairs<br>
•	Concept: Basic DP with dp[i] = dp[i-1] + dp[i-2]<br>
•	Goal: Ways to climb n stairs taking 1 or 2 steps.<br>
•	Focus: Base cases, recursion + memoization or bottom-up.<br>
2.198. House Robber<br>
•	Concept: Rob or skip house.<br>
•	Transition: dp[i] = max(dp[i-1], dp[i-2] + nums[i])<br>
3. 746. Min Cost Climbing Stairs<br>
•	Concept: Similar to Climbing Stairs but with cost array.<br>
•	Transition: dp[i] = cost[i] + min(dp[i-1], dp[i-2])<br>
________________________________________
🔁 Intermediate Level (Space Optimization, Variants)
4. 1137. N-th Tribonacci Number
•	Concept: Extended Fibonacci.
•	Transition: dp[i] = dp[i-1] + dp[i-2] + dp[i-3]
5. 62. Unique Paths
•	Concept: Combinatorics and space-optimized DP.
•	Transition: dp[j] = dp[j] + dp[j-1]
6. 121. Best Time to Buy and Sell Stock
•	Concept: Track min_price and update max_profit.
________________________________________
🧠 Advanced Level (Complex State)
7. 213. House Robber II
•	Concept: Circular array variant of House Robber.
•	Note: Use 1D DP twice (exclude first or last).
8. 91. Decode Ways
•	Concept: DP with strings and encoding combinations.
•	Transition: dp[i] = dp[i-1] + dp[i-2] if valid.
9. 300. Longest Increasing Subsequence
•	Concept: For each i, find max dp[j] + 1 where j < i && nums[j] < nums[i]
•	Time: O(n^2) or optimized O(n log n)
10. 877. Stone Game
•	Concept: Game theory, greedy and DP.
________________________________________
📊 Practice Flow Summary
Phase	Problems	Skills Learned
Step 1	70, 746	Basic transition, bottom-up
Step 2	198, 1137	Max/min problems, space optimize
Step 3	62, 121	Greedy + DP, edge cases
Step 4	213, 91	DP with strings, multiple states
Step 5	300, 877	Advanced LIS, game strategies
________________________________________

<!-- problem:end -->
