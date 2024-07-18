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
    def longestConsecutive(self, nums: List[int]) -> int:
        """
        Calculates the length of the longest consecutive sequence in a list of integers.

        Args:
            nums (List[int]): The list of integers.

        Returns:
            int: The length of the longest consecutive sequence.
        """

        # Initialize a set to store the elements of the list
        num_set = set(nums)
        res = 0

        # Iterate through the list of integers
        for r in nums:

            # If the current element minus 1 is not in the set, calculate the length of the consecutive sequence
            if (r - 1) not in num_set:

                # Initialize length to 1
                length = 1

                # While the current element plus the length is in the set, increment the length
                while (r + length) in num_set:
                    length += 1

                # Update the result to the maximum of the current result and the length
                res = max(res, length)

        # Return the result
        return res
```
