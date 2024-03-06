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
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def distanceK(self, root: TreeNode, target: TreeNode, k: int) -> List[int]:
        """
        Returns a list of all nodes that are at a distance of k from the target node in a binary tree.

        Parameters:
        - root (TreeNode): The root node of the binary tree.
        - target (TreeNode): The target node from which the distance is calculated.
        - k (int): The distance from the target node.

        Returns:
        - List[int]: A list of node values that are at a distance of k from the target node.
        """

        dic = {root : None}  # Dictionary to store the parent node of each node

        # Create a queue to traverse the tree and store the parent of each node
        queue1 = deque()
        queue1.append(root)

        # While the queue is not empty, traverse the tree and store the parent of each node
        while queue1:

            # Pop the leftmost node from the queue
            node = queue1.popleft()

            # If the left child of the node exists then store the parent of the left child in the dictionary and append the left child to the queue
            if node.left:
                dic[node.left] = node
                queue1.append(node.left)

            # If the right child of the node exists then store the parent of the right child in the dictionary and append the right child to the queue
            if node.right:
                dic[node.right] = node
                queue1.append(node.right)


        visited = set()  # Set to keep track of visited nodes
        res = []  # List to store the result

        # Create a queue to traverse the tree and find the nodes at a distance of k from the target node
        queue2 = deque()
        queue2.append([0, target])

        # While the queue is not empty, traverse the tree and find the nodes at a distance of k from the target node
        while queue2:

            # Pop the leftmost node from the queue
            dis, node = queue2.popleft()
            visited.add(node)

            # If the distance of the node from the target node is equal to k then append the node value to the result list
            if dis == k:
                res.append(node.val)

            # If the distance of the node from the target node is less than k and the left child of the node exists then append the left child to the queue
            if node.left and node.left not in visited:
                queue2.append([dis + 1, node.left])

            # If the distance of the node from the target node is less than k and the right child of the node exists then append the right child to the queue
            if node.right and node.right not in visited:
                queue2.append([dis + 1, node.right])

            # If the distance of the node from the target node is less than k and the parent of the node exists then append the parent to the queue
            if dic[node] and dic[node] not in visited:
                queue2.append([dis + 1, dic[node]])

        # Return the result list
        return res
```
