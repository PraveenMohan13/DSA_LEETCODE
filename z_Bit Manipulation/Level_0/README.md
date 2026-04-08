# Bit Manipulation Guide

Beginner to Advanced — Complete Guide

---

## 🟢 Level 1 — Beginner: Binary Basics

Computers store everything as binary (`0` and `1`). Bit manipulation means directly operating on these bits for speed, efficiency, and elegant solutions.

### Binary Number Table

| Decimal | Binary | Description           |
| ------- | ------ | --------------------- |
| 0       | `0000` | Zero                  |
| 1       | `0001` | One                   |
| 2       | `0010` | One Two               |
| 5       | `0101` | One 4 + one 1         |
| 8       | `1000` | One 8                 |
| 15      | `1111` | One 8 + one 4 + one 1 |

### The 6 Bitwise Operators

| Operator    | Symbol | Meaning                         |
| ----------- | ------ | ------------------------------- |
| AND         | `&`    | 1 only if BOTH bits are 1       |
| OR          | I      | 1 if EITHER bit is 1            |
| XOR         | `^`    | 1 if bits are DIFFERENT         |
| NOT         | `~`    | Flips all bits                  |
| Left Shift  | `<<`   | Shift bits left (multiply by 2) |
| Right Shift | `>>`   | Shift bits right (divide by 2)  |

```python
a = 5   # binary: 0101
b = 3   # binary: 0011

print(a & b)   # 1
print(a | b)   # 7
print(a ^ b)   # 6
print(~a)      # -6
print(a << 1)  # 10
print(a >> 1)  # 2
```

### Examples

#### 1. AND (`&`)

```text
  0101  (5)
& 0011  (3)
------
  0001  (1)
```

#### 2. OR (`|`)

```text
  0101  (5)
| 0011  (3)
------
  0111  (7)
```

#### 3. XOR (`^`)

```text
  0101  (5)
^ 0011  (3)
------
  0110  (6)
```

#### 4. NOT (`~`)

```text
~5 = -6
```

#### 5. Left Shift (`<<`)

```text
5 << 1 = 10
5 << 2 = 20
```

#### 6. Right Shift (`>>`)

```text
20 >> 1 = 10
20 >> 2 = 5
```

---

## 🟡 Level 2 — Intermediate: Core Tricks

### Bit Indexing

Bits are indexed from right to left, starting at `0`.

```text
Number: 13
Binary: 1101

Position: 3 2 1 0
Bits:     1 1 0 1
```

### Multiply / Divide by Powers of 2

```python
n << k   # n * 2^k
n >> k   # n / 2^k
```

```python
5 << 3   # 40
40 >> 3  # 5
```

### XOR Properties

```python
a ^ a = 0
a ^ 0 = a
a ^ b ^ a = b
```

### Set, Check, Clear, Toggle Bits

#### Set a Bit

```python
n = n | (1 << k)
```

#### Check a Bit

```python
if n & (1 << k):
    print("Bit is set")
```

```python
def is_bit_set(n, i):
    return ((n >> i) & 1) == 1
```

#### Clear a Bit

```python
n = n & ~(1 << k)
```

#### Toggle a Bit

```python
n = n ^ (1 << k)
```

### Quick Summary

| Operation  | Formula             |           |
| ---------- | ------------------- | --------- |
| Set bit    | `n = n              | (1 << k)` |
| Clear bit  | `n = n & ~(1 << k)` |           |
| Toggle bit | `n = n ^ (1 << k)`  |           |
| Check bit  | `n & (1 << k)`      |           |

### Even / Odd

```python
n & 1 == 0   # Even
n & 1 == 1   # Odd
```

### Power of 2

```python
def is_power_of_2(n):
    return n > 0 and (n & (n - 1)) == 0
```

### Lowest Set Bit

```python
lowest_bit = n & (-n)
```

### Clear Lowest Set Bit

```python
n & (n - 1)
```

---

## 🟠 Level 3 — Intermediate-Advanced: Classic Problems

### Count Set Bits

```python
def count_set_bits(n):
    count = 0
    while n:
        n &= n - 1
        count += 1
    return count
```

### Single Number Using XOR

```python
def single_number(nums):
    result = 0
    for n in nums:
        result ^= n
    return result
```

### Swap Without Temp Variable

```python
a ^= b
b ^= a
a ^= b
```

### Reverse Bits

```python
def reverse_bits(n):
    result = 0
    for _ in range(32):
        result = (result << 1) | (n & 1)
        n >>= 1
    return result
```

### Get a Range of Bits

```python
def get_bits(n, i, j):
    mask = ((1 << (j - i + 1)) - 1) << i
    return (n & mask) >> i
```

### Two's Complement

```text
Positive 5:  00000101
Flip bits:   11111010
Add 1:       11111011   = -5
```

---

## 🔴 Level 4 — Advanced Techniques

### Fast Multiplication / Division

```python
n * 4  == n << 2
n / 8  == n >> 3
n * 7  == (n << 3) - n
```

### Brian Kernighan's Algorithm

```python
def count_set_bits(n):
    count = 0
    while n:
        n &= n - 1
        count += 1
    return count
```

### Bitmask DP Example (Traveling Salesman)

```python
n = 4
dp = [[float('inf')] * n for _ in range(1 << n)]
dp[1][0] = 0
```

### Find Two Unique Numbers

```python
def find_two_singles(nums):
    xor = 0
    for n in nums:
        xor ^= n

    diff_bit = xor & (-xor)

    a = b = 0
    for n in nums:
        if n & diff_bit:
            a ^= n
        else:
            b ^= n
    return a, b
```

### Maximum XOR Using Trie

```python
class TrieNode:
    def __init__(self):
        self.children = {}

def max_xor(nums):
    root = TrieNode()

    for n in nums:
        node = root
        for i in range(31, -1, -1):
            bit = (n >> i) & 1
            if bit not in node.children:
                node.children[bit] = TrieNode()
            node = node.children[bit]

    max_val = 0

    for n in nums:
        node, curr_xor = root, 0
        for i in range(31, -1, -1):
            bit = (n >> i) & 1
            want = 1 - bit

            if want in node.children:
                curr_xor |= (1 << i)
                node = node.children[want]
            else:
                node = node.children[bit]

        max_val = max(max_val, curr_xor)

    return max_val
```

---

## 📋 Quick Reference Cheat Sheet

| Operation         | Code               | Use Case       |              |
| ----------------- | ------------------ | -------------- | ------------ |
| Is odd?           | `n & 1`            | Parity check   |              |
| Power of 2?       | `n & (n - 1) == 0` | Validation     |              |
| Set bit i         | `n                 | (1 << i)`      | Flag setting |
| Clear bit i       | `n & ~(1 << i)`    | Flag clearing  |              |
| Toggle bit i      | `n ^ (1 << i)`     | Toggle flags   |              |
| Low bit           | `n & -n`           | Fenwick tree   |              |
| Drop low bit      | `n & (n - 1)`      | Count set bits |              |
| Multiply by `2^n` | `n << k`           | Fast math      |              |
| Divide by `2^n`   | `n >> k`           | Fast math      |              |

---

## 🧭 Learning Path

* Week 1: Operators + basic tricks
* Week 2: Set / Clear / Toggle bits
* Week 3: XOR tricks + Count bits
* Week 4: Bitmask DP + Trie + Competitive Programming

### Suggested LeetCode Problems

| Difficulty | Problems                       | Focus             |
| ---------- | ------------------------------ | ----------------- |
| Easy       | `#136`, `#191`, `#190`, `#338` | XOR, Count Bits   |
| Medium     | `#137`, `#260`, `#318`, `#421` | Bitmasks, Max XOR |
| Hard       | `#42`, `#805`, `#1434`         | Bitmask DP        |
