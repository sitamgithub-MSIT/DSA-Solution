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
    def findCeil(self, root, inp):
        """
        Finds the ceil value of a given input 'inp' in a binary search tree.

        Args:
            - root: The root node of the binary search tree.
            - inp: The input value for which the ceil value needs to be found.

        Returns:
            The ceil value of 'inp' in the binary search tree.
        """
        ceil = -1

        # Traverse the tree
        while root:

            # If the root value is equal to the input, return the root value
            if root.val == inp:
                return inp

            # If the root value is less than the input, traverse the right subtree
            elif root.val < inp:
                root = root.right

            # If the root value is greater than the input, traverse the left subtree
            else:
                ceil = root.val
                root = root.left

        # Return the ceil
        return ceil
```
