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
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:

        # If root is None then return
        if root is None:
            return []

        # Stack consists of the root node and a boolean value
        stack = [(root,False)]
        res = []

        # While stack is not empty
        while stack:

            # Pop the node and the boolean value from the stack
            node,visited = stack.pop()

            # If node is not None
            if node:

                # If visited is True then append the node value to the res array
                if visited:
                    res.append(node.val)

                # Else append the right child, node and left child to the stack
                else:
                    stack.append((node.right,False))
                    stack.append((node,True))
                    stack.append((node.left,False))

        # Return the res array
        return res
```
