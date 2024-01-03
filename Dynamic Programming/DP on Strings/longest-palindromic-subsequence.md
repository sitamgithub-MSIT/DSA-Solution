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
    def longestPalindromeSubseq(self, s: str) -> int:
        """
        Calculates the length of the longest palindromic subsequence in a given string.

        Args:
            s (str): The input string.

        Returns:
            int: The length of the longest palindromic subsequence.

        """

        # Actual string and its reverse
        text1, text2 = s, s[::-1]

        # length of text1 and text2
        n, m = len(text1), len(text2)

        # dp array to store the results of the subproblems
        dp = [[0]*(m+1) for _ in range(n+1)]

        # Iterate over the dp array
        for i in range(1, n+1):
            for j in range(1, m+1):

                # If the characters match, add 1 to the result of the subproblem
                if(text1[i-1] == text2[j-1]):
                    dp[i][j] = 1 + dp[i-1][j-1]

                # If the characters do not match, take the maximum of the results of the subproblems
                else:
                    dp[i][j] = max(dp[i-1][j], dp[i][j-1])

        # Return the result
        return dp[n][m]
```
