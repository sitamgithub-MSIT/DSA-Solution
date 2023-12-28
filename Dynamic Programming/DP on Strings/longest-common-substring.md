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
    def lcs(str1: str, str2: str) -> int:
        """
        Calculates the length of the longest common substring between two strings.

        Args:
            str1 (str): The first string.
            str2 (str): The second string.

        Returns:
            int: The length of the longest common substring.
        """

        # length of text1 and text2 and the answer variable
        n, m = len(str1), len(str2)
        ans = float('-inf')

        # dp array to store the results of the subproblems
        dp = [[0]*(m+1) for _ in range(n+1)]

        # Iterate over the dp array
        for i in range(1, n+1):
            for j in range(1, m+1):

                # If the characters match, add 1 to the result of the subproblem and update the answer
                if(str1[i-1] == str2[j-1]):
                    dp[i][j] = 1 + dp[i-1][j-1]
                    ans = max(ans, dp[i][j])

                # If the characters do not match, put 0 in the dp array
                else:
                    dp[i][j] = 0

        # Return the result
        return ans
```
