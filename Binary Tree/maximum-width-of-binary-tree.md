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
    def widthOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        """
        Calculates the maximum width of a binary tree.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.

        Returns:
            int: The maximum width of the binary tree.

        """

        # Initialising the queue with root, index and level
        queue = [[root,1,0]]
        pre_index, pre_level = 1, 0
        res = 0

        # Traverse the tree level by level
        while queue:

            # Pop the leftmost element from the queue
            node, index, level = queue.pop(0)

            # If the level is greater than the previous level then update the previous level and index
            if pre_level < level:
                pre_level = level
                pre_index = index

            # Update the maximum width
            res = max(res, index - pre_index + 1)

            # If left child of that node exist then append it to the queue
            if node.left:
                queue.append([node.left, 2*index, level + 1])

            # If right child of that node exist then append it to the queue
            if node.right:
                queue.append([node.right, 2*index + 1, level + 1])

        # Return the maximum width
        return res
```
