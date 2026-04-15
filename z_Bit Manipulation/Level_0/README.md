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

print(a & b)   # 1  -> 0001  (AND)
print(a | b)   # 7  -> 0111  (OR)
print(a ^ b)   # 6  -> 0110  (XOR)
print(~a)      # -6  (flips all bits including sign bit)
print(a << 1)  # 10  -> 1010  (left shift = *2)
print(a >> 1)  # 2   -> 0010  (right shift = /2)
```

### Examples

#### 1. AND (`&`)

```text
  0101  (5)
& 0011  (3)
------  (both must be 1)
  0001  (1)  →   5 & 3 = 1
```

#### 2. OR (`|`)

```text
  0101  (5)
| 0011  (3)
------  (at least one is 1)
  0111  (7)  →   5 | 3 = 7
```

#### 3. XOR (`^`)

```text
  0101  (5)
^ 0011  (3)
------  (exactly one is 1)
  0110  (6)  →   5 ^ 3 = 6
```

#### 4. NOT (`~`)

```text
~5 = -6  6     (-(n+1) in two's complement)
```

#### 5. Left Shift (`<<`)

```text
5 << 1 = 10  (0101 → 1010)
5 << 2 = 20  (0101 → 10100)
```

#### 6. Right Shift (`>>`)

```text
20 >> 1 = 10   (10100 → 01010)
20 >> 2 = 5    (10100 → 00101)
```

---

## 🟡 Level 2 — Intermediate: Core Tricks

In bit manipulation, a <br>
•	“set bit” means a bit whose value is 1.<br>
•	“Unset bit or Clear bit” means a bit whose value is 0.<br>
So when someone says:<br>
•	“Set the 3rd bit” → make that bit 1<br>
•	“Count set bits” → count how many 1s are in the binary representation<br>
•	“Check if a bit is set” → check if that bit is 1<br>

### Bit Indexing

Bits are indexed from right to left, starting at `0`.

```text
Number: 13
Binary: 1101

Position: 3 2 1 0
Bits:     1 1 0 1
```
•	Bit 0 → Rightmost bit (Least Significant Bit — LSB) <br>
•	Bit 3 → Leftmost bit (Most Significant Bit — MSB in this 4-bit example)

### Multiply / Divide by Powers of 2

```python
n << k   # n * 2^k (fast multiply)
n >> k   # n / 2^k (fast divide)
```

```python
5 << 3   # 5 x 8 = 40
40 >> 3  # 40 / 8 = 5
```

### XOR Properties

```python
a ^ a = 0          -> same number cancels out
a ^ 0 = a          -> XOR with 0 = itself
a ^ b ^ a = b      -> order does not matter
```

### Set, Check, Clear, Toggle Bits

#### Set a Bit
To set the kth bit, use OR | with a left shift:

```python
n = n | (1 << k)
```
##### Example
Set bit 1 (0-based index) in number 8:<br>
n = 8        → 1000<br>
1 << 1       → 0010<br>
Result       → 1010 (10)<br>

#### Check a Bit

```python
if n & (1 << k):
    print("Bit is set")
```
If result ≠ 0 → bit is set.<br>
•  1 << k creates a number where only the k-th bit is 1<br>
•  AND (&) with n keeps only that bit<br>
•  If result ≠ 0 → bit was set<br>

#### Check if a bit is SET at position i
```python
def is_bit_set(n, i):
    return ((n >> i) & 1) == 1
```
 n=5 (0101), i=2  →  0101 >> 2 = 0001, & 1 = 1

•  Shift the i-th bit to the last position
•  Then check if last bit is 1 using & 1

#### Clear a Bit (Make it 0)
To clear the kth bit, use:
```python
n = n & ~(1 << k)
```
##### Why this works
•	(1 << k) creates a number with only the kth bit set.<br>
•	~ inverts it (so kth bit becomes 0, others 1).<br>
•	& keeps all bits same except kth bit becomes 0.<br>

Example
Clear bit 1 in n = 10
10       = 1010
1 << 1   = 0010
~(0010)  = 1101

----------------
Result   = 1000 (8)
Bit 1 is now cleared ✅

#### Toggle a Bit (Flip 0 ↔ 1)
To toggle the kth bit, use XOR:
```python
n = n ^ (1 << k)
```
Why this works
•	XOR with 1 flips the bit
•	XOR with 0 keeps it same

Example
Toggle bit 1 in n = 10
10       = 1010
1 << 1   = 0010

----------------
Result   = 1000 (8)
If you toggle again:
1000 ^ 0010 = 1010 (10)
It flips back 

### Quick Summary

| Operation  | Formula             |
| ---------- | ------------------- |
| Set bit    | n = n I (1 << k)    |
| Clear bit  | `n = n & ~(1 << k)` |
| Toggle bit | `n = n ^ (1 << k)`  |
| Check bit  | `n & (1 << k)`      |


### Even / Odd

```python
n & 1 == 0   # Even (last bit is 0)
n & 1 == 1   # Odd  (last bit is 1)
```

### Power of 2
Powers of 2 have exactly ONE set bit. So n & (n-1) equals zero for them.<br>
8 = 1000, 8-1 = 0111 -> AND = 0 -> True<br>
```python
def is_power_of_2(n):
    return n > 0 and (n & (n - 1)) == 0
```
 n=8  →  1000 & 0111 = 0000  ✓<br>
 n=6  →  0110 & 0101 = 0100  ✗
 
### Isolate the Lowest Set Bit

```python
lowest_bit = n & (-n)    # Isolates rightmost set bit
# Because -n = ~n + 1 in two's complement

n = 12     # 1100
-n = -12   # 0100  (two's complement)
n & -n     # 0100 = 4  -> the lowest set bit

```

### Clear Lowest Set Bit

```python
n & (n - 1)    # Removes rightmost 1-bit<br>
# 1100 & 1011 = 1000
```
### Extract lowest set bit
n & (-n)       # Isolates rightmost 1-bit<br>

n=12 (1100): 1100 & 0100 = 0100 (4)

## 🟠 Level 3 — Intermediate-Advanced: Classic Problems

### Count Set Bits 
#### (Hamming Weight) — O(k)
int count = 0;
while (n) {
    count += n & 1;
    n >>= 1;
}
#### Brian Kernighan’s algorithm (faster):
```text
while (n) {
    n = n & (n - 1);	# Clear lowest bit each time
    count++;
}
```
n=7 (111)  →  110  →  100  →  000 = 3 iterations

### Single Number Using XOR
In an array where every element appears twice except one — find it.
[1, 2, 3, 2, 1] -> answer is 3
All duplicates cancel via XOR!

```python
def single_number(nums):
    result = 0
    for n in nums:
        result ^= n  # Same numbers cancel: a ^ a = 0
    return result
```
[2, 3, 2]  →  0^2^3^2 = 3

### Swap Without Temp Variable

```text
a = 5; b = 3<br>
a ^= b   # a = 5^3 = 6	# a = a XOR b<br>
b ^= a   # b = 3^6 = 5	# b = b XOR (a XOR b) = a<br>
a ^= b   # a = 6^5 = 3	# a = (a XOR b) XOR a = b<br>
# Now a=3, b=5 ✓<br>
```
Why it works
Remember these XOR properties:
•	x ^ x = 0
•	x ^ 0 = x
•	XOR is commutative and associative

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
n=0b11101100, i=2, j=5  →  extracts bits 2-5

### Two's Complement(How Negatives Work)

```text
Positive 5:  00000101
Flip bits:   11111010
Add 1:       11111011   = -5
So: ~n = -(n+1)  ->  ~5 = -6
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
Counts set bits by only iterating over set bits, not all 32 bits.<br>
The key insight: n & (n-1) removes the LOWEST set bit from n.<br>

```python
def count_set_bits(n):
    count = 0
    while n:
        n &= n - 1
        count += 1
    return count
```

### Bitmask DP Example (Traveling Salesman)
Used when state = subset of elements. Each bit represents whether a city has been visited.
```text
n = 4
dp = [[float('inf')] * n for _ in range(1 << n)]
dp[1][0] = 0   # Start at city 0, visited = {0} = 0001

for mask in range(1 << n):
    for u in range(n):
        if not (mask >> u) & 1: continue
        for v in range(n):
            if (mask >> v) & 1: continue
            new_mask = mask | (1 << v)
            dp[new_mask][v] = min(dp[new_mask][v],
            dp[mask][u] + dist[u][v])
```

### Find Two Unique Numbers(XOR)

```python
def find_two_singles(nums):
    xor = 0
    for n in nums:   # xor = a^b
        xor ^= n

    diff_bit = xor & (-xor)  # Rightmost differing bit

    a = b = 0
    for n in nums:
        if n & diff_bit:
            a ^= n
        else:
            b ^= n
    return a, b
```

### Bit Trie - Maximum XOR Using Trie

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
#### Bitmask — Store Sets Efficiently
Instead of a list of booleans, use an integer as a set of flags:<br>
mask = 0<br>
mask |= (1 << 2)   # Add element 2   -> mask = 00100<br>
mask |= (1 << 4)   # Add element 4   -> mask = 10100<br>
(mask >> 2) & 1    # Check element 2 -> 1 (exists)<br>
mask &= ~(1 << 2)  # Remove element 2 -> mask = 10000<br>

Iterate all subsets of n elements<br>
n = 4<br>
for mask in range(1 << n):        # 0 to 2^n - 1<br>
    print(bin(mask))              # Every possible subset<br>

---

## 📋 Quick Reference Cheat Sheet

| Operation         | Code               | Use Case        |
| ----------------- | ------------------ | --------------  |
| Is odd?           | `n & 1`            | Parity check    |
| Power of 2?       | `n & (n - 1) == 0` | Validation      |
| Set bit i         | n I (1 << i)       | Flag setting    |
| Clear bit i       | `n & ~(1 << i)`    | Flag clearing   |
| Toggle bit i      | `n ^ (1 << i)`     | Toggle flags    |
| Low bit           | `n & -n`           | Fenwick tree    |
| Drop low bit      | `n & (n - 1)`      | Count set bits  |
| Multiply by `2^n` | `n << k`           | Fast math       |
| Divide by `2^n`   | `n >> k`           | Fast math       |
| Swap a,b          | `a^=b; b^=a; a^=b` | No temp variable|

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
