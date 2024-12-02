# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(logN)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def floor(self, root, x):
        """
        Finds the floor value of a given input 'x' in a binary search tree.

        Args:
            - root: The root node of the binary search tree.
            - x: The input value for which the floor value needs to be found.

        Returns:
            The floor value of 'x' in the binary search tree.
        """
        floor = -1

        # Traverse the tree
        while root:

            # If the root value is equal to the input, return the root value
            if root.val == inp:
                return root.val

            # If the root value is greater than the input, traverse the left subtree
            elif root.val > inp:
                root = root.left

            # If the root value is less than the input, traverse the right subtree
            else:
                floor = root.val
                root = root.right

        # Return the floor
        return floor
```
