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
    def findLCS(n: int, m: int, s1: str, s2: str) -> str:
        """
        Finds the longest common subsequence (LCS) between two strings.

        Args:
            n (int): Length of the first string.
            m (int): Length of the second string.
            s1 (str): First string.
            s2 (str): Second string.

        Returns:
            str: The longest common subsequence (LCS) string.

        """

        # length of text1 and text2
        n, m = len(s1), len(s2)

        # dp array to store the results of the subproblems
        dp = [[0]*(m+1) for _ in range(n+1)]

        # Iterate over the dp array
        for i in range(1, n+1):
            for j in range(1, m+1):

                # If the characters match, add 1 to the result of the subproblem
                if(s1[i-1] == s2[j-1]):
                    dp[i][j] = 1 + dp[i-1][j-1]

                # If the characters do not match, take the maximum of the results of the subproblems
                else:
                    dp[i][j] = max(dp[i-1][j], dp[i][j-1])

        # Return the result
        length = dp[n][m]

        # ans array to store the longest common subsequence string
        ans = ["$"] * length
        index = length-1

        i, j = n, m

        # Execute the loop while i and j are greater than 0
        while(i > 0 and j > 0):

            # If the characters match, store the character in the ans array and update the indices
            if(s1[i-1] == s2[j-1]):
                ans[index] = s1[i-1]
                index -= 1
                i -= 1
                j -= 1

            # Update the i index if the value of dp[i-1][j] is greater than dp[i][j-1]
            elif(dp[i-1][j] > dp[i][j-1]):
                i -= 1

            # Else update the j index
            else:
                j -= 1

        # Convert the ans array to a string
        string = "".join(ans)

        # Return the null string if the string contains "$"
        if "$" in string:
            return("")

        # Else return the longest common subsequence string
        else:
            return(string)
```
