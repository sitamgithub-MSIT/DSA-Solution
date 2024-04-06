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
    def singleNonDuplicate(self, nums: List[int]) -> int:
        """
        Finds the single non-duplicate element in a sorted array.

        Args:
            nums (List[int]): The input array of integers.

        Returns:
            int: The single non-duplicate element in the array.
        """

        # Initialize res variable as 0
        res = 0

        # Iterating through all over the nums array
        for n in nums:

            # Performing XOR operation
            res = res ^ n

        # Return res
        return res
```
