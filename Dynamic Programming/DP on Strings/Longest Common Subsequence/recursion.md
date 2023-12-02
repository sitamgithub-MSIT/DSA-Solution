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
    def longestCommonSubsequence(self, text1: str, text2: str) -> int:

        # Define a recursive function to solve the problem
        def dfs(ind1, ind2):

            # Base case
            if(ind1 < 0 or ind2 < 0):
                return 0

            # If the characters match, add 1 to the result of the subproblem
            if(text1[ind1] == text2[ind2]):
                return 1 + dfs(ind1-1, ind2-1)

            # If the characters do not match, take the maximum of the results of the subproblems
            else:
                return 0 + max(dfs(ind1-1, ind2), dfs(ind1, ind2-1))

        # Call the recursive function
        return(dfs(len(text1)-1, len(text2)-1))

```
