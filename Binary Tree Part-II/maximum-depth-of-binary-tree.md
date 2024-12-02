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
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        """
        Calculates the maximum depth of a binary tree.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.

        Returns:
            int: The maximum depth of the binary tree.
        """
        # If root is None then return 0 base case
        if root is None:
            return 0

        # Else return 1 + the maximum depth of the left and right subtree
        else:
            return( 1 + max(self.maxDepth(root.right), self.maxDepth(root.left)))
```
