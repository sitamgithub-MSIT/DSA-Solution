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
    def insertIntoBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
        """
        Inserts a node with the given value into a binary search tree.

        Args:
            root (Optional[TreeNode]): The root of the binary search tree.
            val (int): The value to be inserted.

        Returns:
            Optional[TreeNode]: The root of the modified binary search tree.
        """

        # Base case
        if root is None:
            node = TreeNode(val)
            return node

        # If the value is less than the root value, traverse the left subtree
        elif root.val > val:
            root.left = self.insertIntoBST(root.left, val)
            return root

        # If the value is greater than the root value, traverse the right subtree
        else:
            root.right = self.insertIntoBST(root.right, val)
            return root
```
