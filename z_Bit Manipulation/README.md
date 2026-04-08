
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

What you learn:

* Counting set bits
* Removing bits
* XOR basics
* Binary thinking

---

# Stage 3 – XOR Pattern Questions

These Level is most important.

Key concepts:

```text
x ^ x = 0
0 ^ x = x
```

Whenever every element appears twice except one, think XOR immediately.

---

# Stage 4 – Set Bit Tricks

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

Now you will see:

* Per-bit reasoning
* Greedy + bits
* XOR maximization

---

# Stage 7 – Trie + XOR Problems (Pro Level)

Concept:

* Binary Trie
* Store bits from MSB to LSB
* Greedy maximize XOR

---

# Stage 8 – Bitmask Dynamic Programming (Expert Level)

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
