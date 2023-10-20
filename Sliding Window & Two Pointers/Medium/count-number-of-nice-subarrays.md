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
    def numberOfSubarrays(self, nums: List[int], k: int) -> int:

        # Initialize the array num
        num = []

        # Convert the array to an array of 0s and 1s where 0 is even and 1 is odd 
        for n in nums:
            if n % 2 == 0:
                num.append(0)

            else:
                num.append(1)

        # Initialize the dictionary, the total and the result
        dic = {0:1}
        total = 0
        res = 0

        # Iterate through the array
        for r in range(len(num)):

            # Update the total with the current number
            total += num[r]

            # If the total - k is in the dictionary, update the result with the value of the dictionary
            if(total -  k) in dic:
                res += dic[total -k]

            # Update the dictionary with the current total
            dic[total] = 1 + dic.get(total, 0)

        # Return the result
        return res
        
```
