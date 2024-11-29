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

```python3 []
class Solution:
    def subsetsWithDup(self, nums: List[int]) -> List[List[int]]:
        """
        Generates all possible subsets of a list of numbers, must not contain duplicates.

        Args:
            nums (List[int]): The list of integers which may contain duplicates.

        Returns:
            List[List[int]]: A list of lists, where each inner list is a unique subset
            of the input list.
        """
        # Sort the array to handle duplicates
        nums.sort()
        res, subset = [], []

        def rec_backtrack(i):
            # Base case
            if(i == len(nums)):
                res.append(subset.copy())
                return

            # Decision all subsets that includes nums[i]
            subset.append(nums[i])
            rec_backtrack(i+1)

            # Decision all subsets that not includes nums[i]
            subset.pop()
            while(i+1 < len(nums) and nums[i] == nums[i+1]):
                i += 1
            rec_backtrack(i+1)

        # Call the recursive function
        rec_backtrack(0)

        # Return the result
        return res
```
