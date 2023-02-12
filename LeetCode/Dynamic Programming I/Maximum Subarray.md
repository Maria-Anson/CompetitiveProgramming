> Given an integer array `nums`, find the
> 
> subarray
> 
> with the largest sum, and return _its sum_.
> 
> **Example 1:**
> 
> <pre>**Input:** nums = [-2,1,-3,4,-1,2,1,-5,4]
> **Output:** 6
> **Explanation:** The subarray [4,-1,2,1] has the largest sum 6.
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** nums = [1]
> **Output:** 1
> **Explanation:** The subarray [1] has the largest sum 1.
> </pre>
> 
> **Example 3:**
> 
> <pre>**Input:** nums = [5,4,-1,7,8]
> **Output:** 23
> **Explanation:** The subarray [5,4,-1,7,8] has the largest sum 23.
> </pre>
> 
> **Constraints:**
> 
> *   `1 <= nums.length <= 105`
> *   `-104 <= nums[i] <= 104`
> 
> **Follow up:** If you have figured out the `O(n)` solution, try coding another solution using the **divide and conquer** approach, which is more subtle.
>
> -- https://leetcode.com/problems/maximum-subarray/description/?envType=study-plan&id=dynamic-programming-i#qd-content
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        dp = [-10e5 for _ in range(len(nums))]
        if len(dp)==1:
            return nums[0]

        for i in range(len(dp)):
            if i==0:
                dp[i] = nums[i]
                max_so_far = dp[0]
            else:
                # Inluding current value to sum or starting from the new value
                dp[i] = max(nums[i], nums[i]+dp[i-1])
                if dp[i]> max_so_far:
                    max_so_far = dp[i]

        return max_so_far
```
