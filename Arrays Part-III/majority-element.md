# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        """
        Finds the majority element in a given list of integers.

        Args:
            nums (List[int]): The list of integers.

        Returns:
            int: The majority element.
        """
        # Initialize count and ele to 0 and None
        count, ele = 0, None

        # Iterate through the list of integers
        for i in range(len(nums)):

            # If count is 0, set ele to the current element
            if count == 0:
                ele = nums[i]

            # If the current element is equal to ele, increment count
            if ele == nums[i]:
                count += 1

            # Otherwise, decrement count
            else:
                count -= 1

        # Return the majority element
        return ele
```
