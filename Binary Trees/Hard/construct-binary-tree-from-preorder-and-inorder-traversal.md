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
    def buildTree(self, preorder: List[int], inorder: List[int]) -> Optional[TreeNode]:
        """
        Constructs a binary tree from given preorder and inorder traversals.

        Args:
            preorder (List[int]): The preorder traversal of the binary tree.
            inorder (List[int]): The inorder traversal of the binary tree.

        Returns:
            Optional[TreeNode]: The root node of the constructed binary tree.
        """

        # If either of the lists is empty then return None
        if not preorder or not inorder:
            return None

        # Create a dictionary to store the index of each value in the inorder list
        dic = {v:i for i,v in enumerate(inorder)}

        def helper(l, r):
            """
            Recursive helper function to construct the binary tree.

            Args:
                l (int): The left index of the current subtree.
                r (int): The right index of the current subtree.

            Returns:
                TreeNode: The root node of the current subtree.
            """

            # If the left index is greater than the right index then return None
            if l > r:
                return None

            # Pop the first element from the preorder list
            root = TreeNode(preorder.pop(0))
            idx = dic[root.val]

            # Construct the left and right subtrees
            root.left = helper(l, idx-1)
            root.right = helper(idx+1, r)

            # Return the root node
            return root

        # Call the helper function
        return helper(0, len(inorder)-1)
```
