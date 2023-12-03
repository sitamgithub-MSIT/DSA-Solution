# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(logN)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(logN)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, data=0, left=None, right=None):
#         self.data = data
#         self.left = left
#         self.right = right
class Solution:
    def floor(self, root, x):
        
        # Base case
        if root is None:
            return -1
        
        # If the root value is equal to the input, return the root value
        elif root.data == x:
            return(root.data)
        
        # If the root value is greater than the input, traverse the left subtree
        elif root.data > x:
            return(self.floor(root.left, x))
        
        # If the root value is less than the input, traverse the right subtree
        else:
            val = self.floor(root.right, x)

            # If the value returned by the right subtree is less than or equal to the input, return the value
            if val <= x and val != -1:
                return(val)

            # If the value returned by the right subtree is greater than the input, return the root value
            else:
                return(root.data)

```
