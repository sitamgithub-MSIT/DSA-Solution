# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(2*(m*n)) = O(m*n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Sets the rows and columns of the matrix to 0 if any element in the matrix is 0.

        Args:
            matrix (List[List[int]]): The input matrix.

        Returns:
            None: This function does not return anything. It modifies the input matrix in-place.
        """

        # Rows and columns of the matrix
        row, col = len(matrix), len(matrix[0])
        rowzero = False

        # Iterate through the matrix
        for r in range(row):
            for c in range(col):

                # If the element is 0, set the first element of the row and column to 0
                if(matrix[r][c] == 0):
                    matrix[0][c] = 0
                    if r > 0:
                        matrix[r][0] = 0
                    else:
                        rowzero = True

        # Iterate through the matrix and set the elements to 0
        for r in range(1,row):
            for c in range(1,col):
                if matrix[r][0] == 0 or matrix[0][c] == 0:
                    matrix[r][c] = 0

        # Set the first row to 0
        if matrix[0][0] == 0:
            for r in range(row):
                matrix[r][0] = 0

        # Set the first column to 0
        if rowzero == True:
            for c in range(col):
                matrix[0][c] = 0
```
