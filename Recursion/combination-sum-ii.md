# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(2^n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(k*x)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        """
        This function finds all unique combinations in `candidates` where the candidate numbers sum to `target`.

        Args:
            - candidates (List[int]): A list of integers representing the candidate numbers.
            - target (int): The target sum for the combinations.

        Returns:
            List[List[int]]: A list of lists, where each inner list is a unique combination of numbers that add up to `target`.
        """
        # Sort the candidates list
        candidates.sort()
        res = []
        def rec_backtrack(i, curr, total):
            # If the total sum is equal to the target, add the current combination to the result
            if total == target:
                res.append(curr.copy())
                return

            # If the total sum exceeds the target or we have reached the end of the candidates list, return
            if i >= len(candidates) or total > target:
                return

            # Include the current candidate in the combination and recursively call the function
            curr.append(candidates[i])
            rec_backtrack(i+1, curr, total + candidates[i])

            # Exclude the current candidate from the combination and recursively call the function
            curr.pop()

            # Skip the duplicates
            while(i+1 < len(candidates) and candidates[i] == candidates[i+1]):
                i += 1

            rec_backtrack(i+1, curr, total)

        # Call the recursive function with the initial values
        rec_backtrack(0, [], 0)

        # Return the result
        return res
```
