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
    def maxScore(self, cardPoints: List[int], k: int) -> int:

        # Initialize the left and right pointers
        l = 0
        r = len(cardPoints) - k

        # Initialize the total and res as the sum of the last k elements
        res = total = sum(cardPoints[r:])

        # Iterate through the cardPoints array until the right pointer reaches the end of the array
        while(r < len(cardPoints)):

            # Update the total substracting the right and adding the left
            total = total + cardPoints[l] - cardPoints[r]

            # Update the left and right pointers
            l += 1
            r += 1

            # Take the max of res and total
            res = max(res, total)

        # Return the result
        return res
             
```
