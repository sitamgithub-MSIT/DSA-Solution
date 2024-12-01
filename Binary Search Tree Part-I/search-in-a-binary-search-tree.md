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
    def searchBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
        """
        Searches for a value in a binary search tree.

        Args:
            - root (Optional[TreeNode]): The root node of the binary search tree.
            - val (int): The value to search for in the binary search tree.

        Returns:
            Optional[TreeNode]: The node with the value 'val' if found, None otherwise.
        """
        # If the root is None, return None
        if root is None:
            return

        # If the root value is equal to the input value, return the root
        elif root.val == val:
            return root

        # Recursively search the left and right subtrees
        return(self.searchBST(root.left, val) or self.searchBST(root.right, val))
```
