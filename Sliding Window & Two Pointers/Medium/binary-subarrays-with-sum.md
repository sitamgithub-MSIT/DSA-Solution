# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```
class Solution:
    def numSubarraysWithSum(self, nums: List[int], goal: int) -> int:

        # Initialize the dictionary and the result 
        dic = {0:1}

        res = 0
        total = 0

        # Iterate through the array 
        for r in range(len(nums)):

            # Update the total with the current number 
            total += nums[r]

            # If the total - goal is in the dictionary, update the result with the value of the dictionary
            if(total - goal) in dic:
                res += dic[total - goal]

            # Update the dictionary with the current total 
            dic[total] = 1 + dic.get(total, 0)

        # Return the result
        return res

```
