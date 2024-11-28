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
    def partition(self, s: str) -> List[List[str]]:
        """
        This function partitions a given string `s` into all possible palindrome partitions.

        Args:
            s (str): The input string to be partitioned.

        Returns:
            List[List[str]]: A list of lists, where each inner list contains strings that are palindromic partitions of the input string.
        """
        res=[]
        sub=[]

        # backtracking function
        def backtrack(i):
            # base case
            if i >= len(s):
                res.append(sub.copy())
                return

            for j in range(i, len(s)):
                # check if the substring is a palindrome
                if self.palindrome(s, i, j):
                    # add the substring to the current partition
                    sub.append(s[i : j+1])

                    # recursively call the function for the next index
                    backtrack(j+1)

                    # backtrack by removing the last element
                    sub.pop()

        # start the backtracking from index 0
        backtrack(0)

        # return the result
        return res

    # check if the substring is a palindrome
    def palindrome(self, s, l, r):
        while(l <=r ):
            # if the characters at the left and right pointers are not equal, return False
            if s[l] != s[r]:
                return False

            # move the pointers towards the center
            l, r = l+1, r-1

        # return True if the substring is a palindrome
        return True
```
