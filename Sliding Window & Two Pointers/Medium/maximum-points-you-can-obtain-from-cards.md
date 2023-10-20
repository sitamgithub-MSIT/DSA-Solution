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

        l = 0
        r = len(cardPoints) - k
        res = total = sum(cardPoints[r:])

        while(r < len(cardPoints)):

            total = total + cardPoints[l] - cardPoints[r]

            l += 1
            r += 1

            res = max(res, total)

        return res
             
```