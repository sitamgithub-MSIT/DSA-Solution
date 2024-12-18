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
    def generate(self, numRows: int) -> List[List[int]]:
        """
        Generates Pascal's triangle up to the given number of rows.

        Args:
            numRows (int): The number of rows to generate in Pascal's triangle.

        Returns:
            List[List[int]]: A 2-D list representing Pascal's triangle.
        """
        # Initializing the 2-D array ans with value 1
        ans = [[1]]

        # Running the loop for (length of numRows array - 1) time
        for i in range(numRows-1):

            # Making a temporary array to make the math work
            temp = [0] + ans[-1] + [0]
            res = []

            # Again a for loop to traverse the temp array
            for j in range(len(ans[-1])+1):
                res.append(temp[j] + temp[j+1])

            # Appending every level result to our ans array
            ans.append(res)

        # Returning the final ans array
        return ans
```
