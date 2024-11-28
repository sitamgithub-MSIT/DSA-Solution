# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        """
        Calculates the maximum profit that can be obtained by buying and selling stocks.

        Args:
            prices (List[int]): A list of stock prices.

        Returns:
            int: The maximum profit that can be obtained.
        """
        # Initialize l, max_profit to 0 and negative infinity
        l = 0
        max_profit = float('-inf')

        # Iterate through the list of prices
        for r in range(1, len(prices)):

            # If the price at l is less than or equal to the price at r, calculate the profit and update max_profit
            if(prices[l] <= prices[r]):
                profit = prices[r] - prices[l]
                max_profit = max(max_profit, profit)

            # Otherwise, update l to r
            else:
                l = r

        # If max_profit is less than or equal to 0, return 0
        if max_profit <= 0:
            return 0

        # Otherwise, return max_profit
        else:
            return max_profit
```
