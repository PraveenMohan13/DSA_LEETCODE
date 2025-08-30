
<!-- problem:start -->

# 🌱 Stage 1: Foundation (Subsets & Permutations)


## LeetCode Practice Flow

________________________________________
🧠 Understanding Focus
•	Longest Subsequence & Substring
•	Edit Operations (Insert/Delete/Replace)
•	Palindromic Patterns
•	Pattern Matching
________________________________________
✅ Level-wise Practice Plan
________________________________________
1. 78. Subsets

👉 Hint:

Choices → include or exclude each element.

Goal → reached the end of the array.

Constraints → none (duplicates not present).

💡 Trick: Think of it as binary tree of decisions (yes/no).
Example for [1,2]:

Path [] → then [1] → [1,2]

Or skip → [2].
________________________________________
2. 90. Subsets II

👉 Hint:

Problem is same as Subsets, but duplicates must be avoided.

Sort array first → duplicates will sit next to each other.

While looping: if (i > start && nums[i] == nums[i-1]) continue;
This ensures you don’t start a new branch with the same duplicate twice.
________________________________________
3. 46. Permutations

👉 Hint:

Choices → pick any unused element.

Constraints → don’t pick same element twice.

Goal → when path length == n.

💡 Trick: Use boolean[] used array or temporary removal from list.
________________________________________
4. 47. Permutations II

👉 Hint:

Same as permutations, but duplicates present.

Sort the array first.

Skip rule:

if (used[i]) continue; 
if (i > 0 && nums[i] == nums[i-1] && !used[i-1]) continue;
________________________________________
5. 77. Combinations

👉 Hint:

Choices → numbers from 1 to n.

Constraints → must choose exactly k numbers.

Goal → when path size == k.

💡 Trick: Pruning → if remaining numbers < needed numbers → stop early.
E.g., if you need 3 numbers but only 2 left, stop recursion.
________________________________________
Extra Practice Tip

For every problem in this stage:

Draw recursion tree for small input (n=3).

Print your recursion path while coding → see how the algorithm explores.

Focus on “choose → recurse → un-choose” pattern.
________________________________________

<!-- problem:end -->
