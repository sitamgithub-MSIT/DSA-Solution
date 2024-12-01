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
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isValidBST(self, root: Optional[TreeNode], minimum=float('-inf'), maximum=float('inf')) -> bool:
        """
        Determines whether a binary search tree is valid.

        Args:
            root (Optional[TreeNode]): The root node of the binary search tree.
            minimum (float): The minimum value that a node can have.
            maximum (float): The maximum value that a node can have.

        Returns:
            bool: True if the binary search tree is valid, False otherwise.
        """

        # If the root is None then return True
        if root is None:
            return True

        # If the value of the root is less than the minimum or greater than the maximum then return False
        elif root.val < minimum or root.val > maximum:
            return False

        # Recursively check the left and right subtrees
        return self.isValidBST(root.left, minimum, root.val-1) and self.isValidBST(root.right, root.val+1, maximum)
```
