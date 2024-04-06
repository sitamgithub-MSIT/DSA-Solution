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
    def subarraySum(self, nums: List[int], k: int) -> int:
        """
        Calculates the number of subarrays in the given list of integers whose sum equals k.

        Args:
            nums (List[int]): The list of integers.
            k (int): The target sum.

        Returns:
            int: The number of subarrays whose sum equals k.
        """

        # Dictionary to store the total and the count
        dic = {0:1}
        total = 0
        count = 0

        # Iterate through the array
        for n in nums:

            # Calculate the total
            total += n

            # If the total - k is in the dictionary, increment the count
            if(total - k) in dic:
                count += dic[total-k]

            # If the total is not in the dictionary, add it
            if total not in dic:
                dic[total] = 1

            # If the total is in the dictionary, increment the count
            else:
                dic[total] += 1

        # Return the count
        return count
```
