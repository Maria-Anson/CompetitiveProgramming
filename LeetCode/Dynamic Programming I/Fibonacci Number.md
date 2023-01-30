> The **Fibonacci numbers**, commonly denoted `F(n)` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,
> 
> <pre>F(0) = 0, F(1) = 1
> F(n) = F(n - 1) + F(n - 2), for n > 1.
> </pre>
> 
> Given `n`, calculate `F(n)`.
> 
> **Example 1:**
> 
> <pre>**Input:** n = 2
> **Output:** 1
> **Explanation:** F(2) = F(1) + F(0) = 1 + 0 = 1.
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** n = 3
> **Output:** 2
> **Explanation:** F(3) = F(2) + F(1) = 1 + 1 = 2.
> </pre>
> 
> **Example 3:**
> 
> <pre>**Input:** n = 4
> **Output:** 3
> **Explanation:** F(4) = F(3) + F(2) = 2 + 1 = 3.</pre>
>
```
class Solution:
    def fib(self, n: int) -> int:
        # A base case.
        if n==0:
            return 0
        elif n==1 or n==2:
            return 1
        else:
            f0 = 0
            f1 = 1
            # A for loop that iterates n-1 times.
            for _ in range(1,n):
                # Adding the previous two numbers in the sequence.
                temp = f0+f1
                # Updating the values of f0 and f1.
                f0 = f1
                f1 = temp
            return f1
```
> -- https://leetcode.com/problems/fibonacci-number/description/?envType=study-plan&id=dynamic-programming-i#qd-content
