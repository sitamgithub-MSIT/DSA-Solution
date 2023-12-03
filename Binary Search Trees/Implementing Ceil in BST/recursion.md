# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(logN)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(logN)$$
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
    def findCeil(self,root, inp):
        
        # Base case
        if root is None:
            return -1
        
        # If the root value is equal to the input, return the root value
        elif root.key == inp:
            return root.key

        # If the root value is less than the input, traverse the right subtree 
        elif root.key < inp:
            return(self.findCeil(root.right, inp))

        # If the root value is greater than the input, traverse the left subtree  
        else:
            val = self.findCeil(root.left, inp)

            # If the value returned by the left subtree is greater than or equal to the input, return the value
            if(val >= inp and val != -1):
                return(val)

            # If the value returned by the left subtree is less than the input, return the root value  
            else:
                return(root.key)

```
