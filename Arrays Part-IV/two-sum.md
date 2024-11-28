# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(n)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        """
        Finds two numbers in the given list that add up to the target value.

        Args:
            - nums (List[int]): The list of integers.
            - target (int): The target value.

        Returns:
            List[int]: A list containing the indices of the two numbers that add up to the target value
        """
        # Dictionary to store the count of each element
        dic = Counter(nums)

        # Iterate through the list of integers
        for i in range(len(nums)):

            # Calculate the value to find in the dictionary
            val = target - nums[i]

            # If the value is in the dictionary and the index is not the same as the current index, return the indices
            if val in dic and i != nums.index(val):
                return [i, nums.index(val)]
```
