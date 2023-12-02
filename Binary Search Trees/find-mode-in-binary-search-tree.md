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
    def findMode(self, root: Optional[TreeNode]) -> List[int]:

        # Define a dictionary to store the count of each node
        dic = {}
        ans = []

        # Define a recursive function to traverse the tree
        def dfs(node):

            # Base case
            if node is None:
                return

            # If the node value is already in the dictionary, increment the count
            else:
                dic[node.val] = 1 + dic.get(node.val, 0)

            # Traverse the left and right subtrees
            dfs(node.left)
            dfs(node.right)

        # Call the recursive function
        dfs(root)

        # Find the maximum count
        count_list = list(dic.values())
        max_count = max(count_list)

        # Find the keys with the maximum count
        for key, val in dic.items():
            if val == max_count:
                ans.append(key)

        # Return the answer
        return ans

```
