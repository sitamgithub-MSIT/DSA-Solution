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
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        """
        Calculates the diameter of a binary tree.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.

        Returns:
            int: The diameter of the binary tree.

        """
        # Variable to store the diameter of the binary tree
        diameter = float('-inf')

        def dfs(node):
            """
            Depth-first search function to calculate the height of each node.

            Args:
                node: The current node being visited.

            Returns:
                int: The height of the current node.

            """
            # Access the diameter variable
            nonlocal diameter

            # If node is None then return base case
            if node is None:
                return 0

            # Calculate the height of the left and right subtrees
            left_height = dfs(node.left)
            right_height = dfs(node.right)

            # Update the diameter
            diameter = max(diameter, left_height + right_height)

            # Return the height of the current node
            return 1 + max(left_height, right_height)

        # Call the dfs function on the root node
        dfs(root)

        # Return the diameter
        return diameter
```
