# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(N)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(N)$$
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
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:

        # If root is None then return
        if root is None:
            return

        # If root is the only node then return the root value
        if not root.left and not root.right:
            return [[root.val]]

        # Initialising the queue with root
        queue = deque([root])
        res = []

        # Traverse the tree level by level
        while queue:

            # Initialising the level array and the length of the queue
            level, l= [], len(queue)

            for _ in range(l):
                # Pop the leftmost element from the queue and append it to the level array
                node = queue.popleft()
                level.append(node.val)

                # If left child of that node exist then append it to the queue
                if node.left:
                    queue.append(node.left)

                # If right child of that node exist then append it to the queue
                if node.right:
                     queue.append(node.right)

            # Append the level array to the res array
            res.append(level)

        return res

```
