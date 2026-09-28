# Lab 3: Asymptotic Analysis

This lab focuses on understanding and analyzing the asymptotic behavior of algorithms. We will explore concepts such as Big-O, Big-$\Theta$, and Big-$\Omega$ notations, and apply them to various algorithmic problems to determine their efficiency and scalability.

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Once you have completed the lab, push your changes to your forked repository.

## Problem 1

Suppose $T(n)$ is the worst case running time of an algorithm with input size $n$, and we know that $T(n)$ is $\mathcal{O}(n^3)$ and $\Omega(n^2)$. For each of the following statements, determine whether it must be true, must be false, or could be either true or false. Give a brief justification for each. 

1. $T(n)$ is $\mathcal{O}(n^2)$.
Answer:
We are given that the T(n) grows at least as fast as Ω(n^3) and not as much as O(n^2). 
(True): If T(n)=n^2, it satisfies the given conditions and is O(n ^2).
(False): If T(n)=n^3, it satisfies the given conditions but is not O(n^2) (since n^3grows faster than n^2).

2. $T(n)$ is $\Theta(n^3)$.
Answer:
Could be either true or false: T(n) could equal n^3 (which is Θ(n^3)) or n^2 (which is not Θ(n^3)), and both satisfy being O(n^3) and Ω(n^2).

3. $T(n)$ is $\Omega(n)$.
Answer:
Must be true: Since T(n) grows at least as fast as n^2 (Ω(n^2)), it automatically grows at least as fast as n (Ω(n)).

4. $T(n)$ is $\Theta(n^{1.5})$.
Answer:
Must be false. Since T(n) grows at least as fast as n^2 (Ω(n^2)), it grows strictly faster than n^1.5 and can never be Θ(n^1.5).

5. $T(n)$ is $\mathcal{O}(n)$.
Answer:
Must be false. T(n) grows at least as fast as n^2   (Ω(n^2)), meaning it grows strictly faster than linear time and cannot be upper-bounded by O(n).

6. $T(n)$ is $\Theta(n^2 \log n)$.
Answer:
Could be either true or false. T(n) could equal n^2.logn (which makes the statement true) or n^2 (which makes it false), as both functions satisfy being Ω(n^2) and O(n^3).


## Problem 2
Consider the following algorithm where $f(A, i, j)$ is an unknown algorithm that takes as input an array $A$ and two indicies $i$ and $j$ and returns a number. 

```
Mystery Algorithm
Input: An array of int $A$ of length $n$.
Output: int sum
    n = |A|
    sum = 0
    for i = 1 to n:
        for j = 1 to n:
            sum += f(A, i, j)
```

Without knowing anything about $f$, what can we say about the running time of the Mystery Algorithm in terms of $n$? Justify your answer. 

Answer: We only can know that the best running time of the algorithm is Ω(n^2) because of the nested loops and both of them running for n times. So the Mystery Algorithm's running time is Ω(n²): the double loop forces at least n² calls to f, each taking at least constant time. No tighter or upper bound is possible without knowing f's running time.