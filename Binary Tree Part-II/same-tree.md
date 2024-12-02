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
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        """
        Determines whether two binary trees are identical.

        Args:
            - p (Optional[TreeNode]): The root node of the first binary tree.
            - q (Optional[TreeNode]): The root node of the second binary tree.

        Returns:
            bool: True if the trees are identical, False otherwise.
        """
        # If both trees are empty then they are identical
        if not p and not q:
            return True

        # Else if one of the trees is empty then they are not identical
        elif not p or not q:
            return False

        else:
            # If the values of the nodes are equal then check the left and right subtrees
            if p.val == q.val:
                return self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)

            # Else return False
            else:
                return False
```
