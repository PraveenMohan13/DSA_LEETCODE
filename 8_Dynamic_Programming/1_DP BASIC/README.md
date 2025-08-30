
<!-- problem:start -->

# 1D_DP_Program_Flow


## 1D Dynamic Programming LeetCode Problems - Practice Flow
________________________________________
📄 Beginner Level (Basic 1D DP Pattern)
1. 70. Climbing Stairs
•	Concept: Basic DP with dp[i] = dp[i-1] + dp[i-2]
•	Goal: Ways to climb n stairs taking 1 or 2 steps.
•	Focus: Base cases, recursion + memoization or bottom-up.
2. 198. House Robber
•	Concept: Rob or skip house.
•	Transition: dp[i] = max(dp[i-1], dp[i-2] + nums[i])
3. 746. Min Cost Climbing Stairs
•	Concept: Similar to Climbing Stairs but with cost array.
•	Transition: dp[i] = cost[i] + min(dp[i-1], dp[i-2])
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
Let me know if you want code templates or solutions in Java/C++.


<!-- description:start -->

<p>Given the <code>head</code> of a singly linked list, return <em>the middle node of the linked list</em>.</p>

<p>If there are two middle nodes, return <strong>the second middle</strong> node.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://fastly.jsdelivr.net/gh/doocs/leetcode@main/solution/0800-0899/0876.Middle%20of%20the%20Linked%20List/images/lc-midlist1.jpg" style="width: 544px; height: 65px;" />
<pre>
<strong>Input:</strong> head = [1,2,3,4,5]
<strong>Output:</strong> [3,4,5]
<strong>Explanation:</strong> The middle node of the list is node 3.
</pre>

<p><strong class="example">Example 2:</strong></p>
<img alt="" src="https://fastly.jsdelivr.net/gh/doocs/leetcode@main/solution/0800-0899/0876.Middle%20of%20the%20Linked%20List/images/lc-midlist2.jpg" style="width: 664px; height: 65px;" />
<pre>
<strong>Input:</strong> head = [1,2,3,4,5,6]
<strong>Output:</strong> [4,5,6]
<strong>Explanation:</strong> Since the list has two middle nodes with values 3 and 4, we return the second one.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the list is in the range <code>[1, 100]</code>.</li>
	<li><code>1 &lt;= Node.val &lt;= 100</code></li>
</ul>

<!-- description:end -->

## Solutions

<!-- solution:start -->

### Solution 1

<!-- tabs:start -->

#### Python3

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: ListNode) -> ListNode:
        slow = fast = head
        while fast and fast.next:
            slow, fast = slow.next, fast.next.next
        return slow
```


<!-- tabs:end -->

<!-- solution:end -->

<!-- problem:end -->
