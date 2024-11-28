# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(logn)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(logn)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def myPow(self, x: float, n: int) -> float:
        """
        This function calculates x raised to the power n (x^n).

        Args:
            - x (float): The base number.
            - n (int): The exponent.

        Returns:
            float: The result of x raised to the power n.
        """
        def power(x,n):
            # Base cases
            if n == 0:
                return 1

            if n == 1:
                return x

            # Recursively calculate the power of x raised to n/2
            temp = power(x, n//2)
            res = temp*temp

            # If n is odd, return the result multiplied by x
            if(n%2 != 0):
                return(res*x)

            # If n is even, return the result
            if(n%2 == 0):
                return res

        # Calculate the power of x raised to the absolute value of n
        ans = power(x, abs(n))

        # If n is positive, return the answer
        if(n>0):
            return ans

        # If n is negative, return the reciprocal of the answer
        else:
            return(1/ans)
```
