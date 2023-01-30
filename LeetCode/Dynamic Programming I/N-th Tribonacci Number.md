> The Tribonacci sequence Tn is defined as follows: 
> 
> T0 = 0, T1 = 1, T2 = 1, and Tn+3 = Tn + Tn+1 + Tn+2 for n >= 0.
> 
> Given `n`, return the value of Tn.
> 
> **Example 1:**
> 
> <pre>**Input:** n = 4
> **Output:** 4
> **Explanation:**
> T_3 = 0 + 1 + 1 = 2
> T_4 = 1 + 1 + 2 = 4
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** n = 25
> **Output:** 1389537
> </pre>
> 
> **Constraints:**
> 
> *   `0 <= n <= 37`
> *   The answer is guaranteed to fit within a 32-bit integer, ie. `answer <= 2^31 - 1`.
>
```
class Solution:
    def tribonacci(self, n: int) -> int:
        array = [0,1,1]
        # If n is 0, then we return 0.
        if n==0:
            return 0
        # If n is 1 or 2, then we return the sum of the first two elements of the array.
        elif n==1 or n==2:
            return sum(array[0:2])
        else:
            for _ in range(2,n):
                # Summing the first three elements of the array.
                temp = sum(array[0:3])
                # Shifting the array to the left by one.
                array[0:2] = array[1:3]
                array[2] = temp
            return array[2]
```
> -- https://leetcode.com/problems/n-th-tribonacci-number/description/?envType=study-plan&id=dynamic-programming-i#qd-content
