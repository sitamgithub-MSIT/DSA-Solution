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
    def maxProfit(self, prices: List[int]) -> int:

        # Initialize the left pointer and the max profit as -inf 
        l = 0
        max_profit = float('-inf')

        # Iterate through the array starting from the second element
        for r in range(1, len(prices)):

            # If the left pointer is less than the right pointer
            if(prices[l] <= prices[r]):

                # Update the max profit
                profit = prices[r] - prices[l]

                max_profit = max(max_profit, profit)

            # Else update the left pointer to the right pointer
            else:
                l = r

        # If the max profit is less than or equal to 0 return 0
        if max_profit <= 0:
            return 0

        # Else return the max profit
        else:
            return max_profit
            
```
