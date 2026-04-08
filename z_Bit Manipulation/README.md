
<!-- problem:start -->

# Bit Manipulation Practice Flow


## LeetCode Practice Flow

________________________________________
# Bit Manipulation Mastery Pathway (LeetCode) – Beginner to Pro

Bit manipulation becomes easy when you learn it in layers. Do not jump directly to hard questions.

---

# Stage 1 – Learn the Core Operators

Understand these operators first:

* `&` → AND
* `|` → OR
* `^` → XOR
* `~` → NOT
* `<<` → Left Shift
* `>>` → Right Shift

Important patterns:

```text
x & 1        -> check if odd/even
x << 1       -> multiply by 2
x >> 1       -> divide by 2
x & (x - 1)  -> remove last set bit
x & -x       -> get lowest set bit
x ^ x        -> 0
x ^ 0        -> x
```

Practice these manually for numbers from 1 to 15.

Example:

```text
13 = 1101
13 & (13-1)
1101 & 1100 = 1100
```

---

# Stage 2 – Very Easy LeetCode Questions

Solve in this order:

1. LeetCode 191 – Number of 1 Bits
2. LeetCode 231 – Power of Two
3. LeetCode 338 – Counting Bits
4. LeetCode 190 – Reverse Bits
5. LeetCode 461 – Hamming Distance
6. LeetCode 476 – Number Complement
7. LeetCode 136 – Single Number

What you learn:

* Counting set bits
* Removing bits
* XOR basics
* Binary thinking

---

# Stage 3 – XOR Pattern Questions

These are the most important.

Solve in order:

1. LeetCode 268 – Missing Number
2. LeetCode 389 – Find the Difference
3. LeetCode 260 – Single Number III
4. LeetCode 137 – Single Number II
5. LeetCode 540 – Single Element in a Sorted Array

Key concepts:

```text
x ^ x = 0
0 ^ x = x
```

Whenever every element appears twice except one, think XOR immediately.

---

# Stage 4 – Set Bit Tricks

Solve:

1. LeetCode 201 – Bitwise AND of Numbers Range
2. LeetCode 342 – Power of Four
3. LeetCode 693 – Binary Number with Alternating Bits
4. LeetCode 762 – Prime Number of Set Bits
5. LeetCode 1009 – Complement of Base 10 Integer

You should learn:

* How to isolate bits
* How to turn off bits
* How to compare bit patterns

---

# Stage 5 – Intermediate Bitmask Problems

Now start using masks.

Important idea:

```text
mask = 1 << i
```

Questions:

1. LeetCode 78 – Subsets
2. LeetCode 784 – Letter Case Permutation
3. LeetCode 1239 – Maximum Length of a Concatenated String with Unique Characters
4. LeetCode 1863 – Sum of All Subset XOR Totals
5. LeetCode 78 again – solve using bitmask approach only

Learn:

* Represent subset using bits
* Iterate through all subsets
* Bitmask DP basics

Example:

```text
n = 3
000 -> {}
001 -> {0}
010 -> {1}
011 -> {0,1}
100 -> {2}
```

---

# Stage 6 – Become Strong in Advanced Bit Manipulation

Solve:

1. LeetCode 1318 – Minimum Flips to Make a OR b Equal to c
2. LeetCode 2419 – Longest Subarray With Maximum Bitwise AND
3. LeetCode 2275 – Largest Combination With Bitwise AND Greater Than Zero
4. LeetCode 1829 – Maximum XOR for Each Query
5. LeetCode 1707 – Maximum XOR With an Element From Array

Now you will see:

* Per-bit reasoning
* Greedy + bits
* XOR maximization

---

# Stage 7 – Trie + XOR Problems (Pro Level)

These are asked in top companies.

Solve in order:

1. LeetCode 421 – Maximum XOR of Two Numbers in an Array
2. LeetCode 1707 – Maximum XOR With an Element From Array
3. LeetCode 1803 – Count Pairs With XOR in a Range
4. LeetCode 1938 – Maximum Genetic Difference Query

Concept:

* Binary Trie
* Store bits from MSB to LSB
* Greedy maximize XOR

---

# Stage 8 – Bitmask Dynamic Programming (Expert Level)

Questions:

1. LeetCode 698 – Partition to K Equal Sum Subsets
2. LeetCode 847 – Shortest Path Visiting All Nodes
3. LeetCode 1434 – Number of Ways to Wear Different Hats
4. LeetCode 1125 – Smallest Sufficient Team
5. LeetCode 1494 – Parallel Courses II

These teach:

* DP over subsets
* State compression
* Competitive programming style bitmasking

---

# Daily Practice Plan

## Week 1

* Learn operators
* Solve 191, 231, 338, 136, 268

## Week 2

* Solve XOR and set-bit problems
* Solve 389, 260, 137, 201, 342

## Week 3

* Learn bitmask subsets
* Solve 78, 784, 1863, 1239

## Week 4

* Solve advanced XOR + Trie questions
* Solve 421, 1707, 1803

## Week 5+

* Practice Bitmask DP problems

---

# Golden Bit Manipulation Patterns

```text
1. Check ith bit:
   (n >> i) & 1

2. Set ith bit:
   n | (1 << i)

3. Clear ith bit:
   n & ~(1 << i)

4. Toggle ith bit:
   n ^ (1 << i)

5. Remove last set bit:
   n & (n - 1)

6. Count set bits:
   while (n) {
       n &= (n - 1)
       count++
   }
```

---

# Best Order If You Have Limited Time

Must solve these 15 questions:

1. 191
2. 231
3. 136
4. 268
5. 389
6. 260
7. 137
8. 201
9. 78
10. 784
11. 1318
12. 421
13. 1707
14. 698
15. 1125

If you can solve these confidently, your bit manipulation level becomes strong enough for most interviews including product companies like Rocketlane, Zoho, Freshworks, Amazon, and Microsoft.
<!-- problem:end -->
