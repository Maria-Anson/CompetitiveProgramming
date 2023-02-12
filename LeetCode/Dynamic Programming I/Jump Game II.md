> You are given a **0-indexed** array of integers `nums` of length `n`. You are initially positioned at `nums[0]`.
> 
> Each element `nums[i]` represents the maximum length of a forward jump from index `i`. In other words, if you are at `nums[i]`, you can jump to any `nums[i + j]` where:
> 
> *   `0 <= j <= nums[i]` and
> *   `i + j < n`
> 
> Return _the minimum number of jumps to reach_ `nums[n - 1]`. The test cases are generated such that you can reach `nums[n - 1]`.
> 
> **Example 1:**
> 
> <pre>**Input:** nums = [2,3,1,1,4]
> **Output:** 2
> **Explanation:** The minimum number of jumps to reach the last index is 2\. Jump 1 step from index 0 to 1, then 3 steps to the last index.
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** nums = [2,3,0,1,4]
> **Output:** 2
> </pre>
> 
> **Constraints:**
> 
> *   `1 <= nums.length <= 104`
> *   `0 <= nums[i] <= 1000`
> *   It's guaranteed that you can reach `nums[n - 1]`.
>
```
class Solution:
    def jump(self, nums: List[int]) -> int:
        goal = len(nums)-1
        dp = [0 for val in nums[:-1]]

        if len(dp)==0:
            return 0
        
        # Iterating loop in top down approach
        for i in range(len(nums)-2,-1,-1):
            if i==len(nums)-2:
                if i+nums[i] >= goal :
                    dp[i] = 1
                else:
                    dp[i] = 0
            else:
                if i+nums[i]>= goal:
                    dp[i] = 1
                else:
                    # Checking for possible jump positions and taking a min of them. Avoiding position where jump is not possible
                    array_to_look = [val+1 for val in dp[i+1:nums[i]+i+1] if val>0]
                    if len(array_to_look) ==0:
                        dp[i]=0
                    else:
                        dp[i] = min(array_to_look)
        return dp[0]
```
> -- https://leetcode.com/problems/jump-game-ii/description/?envType=study-plan&id=dynamic-programming-i#qd-content
