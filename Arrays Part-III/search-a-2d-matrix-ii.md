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
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        """
        Searches for a target value in a 2D matrix.

        Args:
            matrix (List[List[int]]): The input 2D matrix.
            target (int): The target value to search for.

        Returns:
            bool: True if the target value is found in the matrix, False otherwise.
        """

        # Row and column of the matrix
        row, col = len(matrix), len(matrix[0])
        l,  r = 0, col-1

        # While the pointer is within the matrix
        while(l < row and r >= 0):

            # If the target is greater than the current element
            if matrix[l][r] > target:
                r -= 1

            # If the target is less than the current element
            elif matrix[l][r] < target:
                l += 1

            # If the target is equal to the current element
            else:
                return True

        # If the target is not found
        return False
```
