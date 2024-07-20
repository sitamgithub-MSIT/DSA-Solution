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
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        """
        Determines whether a binary tree is balanced or not.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.

        Returns:
            bool: True if the binary tree is balanced, False otherwise.
        """

        def height(node):
            """
            Calculates the height of a binary tree.

            Args:
                node: The current node of the binary tree.

            Returns:
                int: The height of the binary tree.
            """

            # Base case
            if node is None:
                return 0

            # Calculate the height of the left and right subtrees
            left_height = height(node.left)
            right_height = height(node.right)

            # If the height of the left or right subtree is -1, then the binary tree is not balanced
            if left_height == -1 or right_height == -1:
                return -1

            # If the difference between the height of the left and right subtrees is greater than 1, then the binary tree is not balanced
            if abs(left_height - right_height) > 1:
                return -1

            # Return the height of the binary tree
            return 1 + max(left_height, right_height)

        # Return True if the height of the binary tree is not -1, False otherwise
        return height(root) != -1
```
