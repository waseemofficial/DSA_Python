---
meta: [Big-o, big-o, pyhon]
---
   [![GitHub tag](https://img.shields.io/github/tag/waseemofficial/DSA_Python.svg)](https://github.com/waseemofficial/DSA_Python/tags)
      [![GitHub issues](https://img.shields.io/github/issues/waseemofficial/DSA_Python.svg)](https://github.com/waseemofficial/DSA_Python/issues)

## Table of Contents

- [To find the Big-O notation #steps-to-find-big-o-notation](#to-find-the-big-o-notation-steps-to-find-big-o-notation)
  - [Report Generation](#report-generation)


# To find the Big-O notation #steps-to-find-big-o-notation
To find the Big-O notation of a program in Python, you need to analyze the time complexity of the program. Time complexity is a measure of how the execution time of an algorithm grows as the input size increases. It is usually expressed using Big-O notation, which provides an upper bound on the growth rate of the algorithm.

Here are the steps to find the Big-O notation of a program in Python:

1. Identify the elementary operations: Determine the operations that are repeated a significant number of times in the program. These operations are usually performed within loops or recursive calls.

2. Count the number of times the elementary operations are executed: Analyze the loops or recursive calls in the program and determine how many times the elementary operations are executed based on the input size.

3. Express the time complexity using Big-O notation: Once you have determined the number of times the elementary operations are executed, express the time complexity using Big-O notation. This notation provides an upper bound on the growth rate of the algorithm.

Let's take an example to illustrate this process. Consider the following Python program:

```python
a = 0
b = 0
N = 4
M = 4

# This loop runs for N time
for i in range(N):
    a = a + 10

# This loop runs for M time
for i in range(M):
    b = b + 40

print(a, b)
```

In this program, the elementary operations are the addition operations `a = a + 10` and `b = b + 40`. The number of times these operations are executed is determined by the values of `N` and `M`. In this case, both loops run `N` and `M` times respectively.

Therefore, the time complexity of this program can be expressed as O(N + M), which means the execution time grows linearly with the sum of `N` and `M`.

It's important to note that this is a simplified example, and in more complex programs, the time complexity may involve nested loops or recursive calls. In such cases, you would need to analyze the nested loops or recursive calls to determine the number of times the elementary operations are executed and express the time complexity accordingly.

```py title="Big-o"
 import big_o
 positive_int_generator = lambda n: big_o.datagen.integers(n, 0, 10000)
 best, others = big_o.big_o(find_max, positive_int_generator, n_repeats=100)
 print(best)
>>> Linear: time = -0.00035 + 2.7E-06*n (sec)

---------------

def fib_naive(n):
     if n < 0:
         return -1
     if n < 2:
         return n
     return fib_naive(n-1) + fib_naive(n-2)

>>> print(big_o.big_o(fib_naive, big_o.datagen.n_, n_repeats=20, min_n=2, max_n=25)[0])
Exponential: time = -11 * 0.47^n (sec)
```


## Report Generation
> [!info]
> ```
> >> best, others = big_o.big_o(heapify, > data_generator_heapify, max_n=10**7)
> >> print(big_o.reports.big_o_report(best, others))
> Best : Polynomial: time = 3.5E-06 * x^0.97 (sec)
> Constant: time = 0.13 (sec)                                     (res: 0.067)
> Linear: time = 0.0068 + 2.5E-06*n (sec)                         (res: 0.003)
> Quadratic: time = 0.053 + 2.2E-11*n^2 (sec)                     (res: 0.012)
> Cubic: time = 0.074 + 2.1E-16*n^3 (sec)                         (res: 0.02)
> Polynomial: time = 3.5E-06 * x^0.97 (sec)                       (res: 0.003)
> Logarithmic: time = -0.2 + 0.033*log(n) (sec)                   (res: 0.027)
> Linearithmic: time = 0.013 + 2.2E-07*n*log(n) (sec)             (res: 0.0035)
> Exponential: time = 0.007 * 1^n (sec)                           (res: 0.22)
> ```
> ![[og-image.png]]

