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
    def amountOfTime(self, root: Optional[TreeNode], start: int) -> int:
        """
        Calculates the amount of time for a binary tree to be infected starting from a given node.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.
            start (int): The value of the node to start the infection from.

        Returns:
            int: The amount of time for the binary tree to be infected.

        """

        dic = defaultdict(list)  # Dictionary for the adjacency list

        def dfs(node):
            """
            Depth-first search to populate the adjacency list.

            Args:
                node: The current node being visited.

            """

            # Base case
            if node is None:
                return

            # Add the current node to the adjacency list
            if node.left:
                dic[node.left.val].append(node.val)
                dic[node.val].append(node.left.val)

            if node.right:
                dic[node.right.val].append(node.val)
                dic[node.val].append(node.right.val)

            # Recurse on the left and right children
            dfs(node.left)
            dfs(node.right)

        # Populate the adjacency list
        dfs(root)

        # Queue for the breadth-first search
        queue2 = deque()
        queue2.append(start)
        ans = -1
        visited = set() # Set to keep track of the visited nodes

        # While the queue is not empty
        while queue2:

            # Increment the time
            ans += 1
            l  = len(queue2)

            for _ in range(l):

                # Pop the node from the queue and add it to the visited set
                node = queue2.popleft()
                visited.add(node)

                # For each neighbor of the node
                for j in dic[node]:

                    # If the neighbor has not been visited, add it to the queue
                    if j not in visited:
                        queue2.append(j)

        # Return the answer
        return ans
```
