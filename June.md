# May LeetCoding Challenge

1) https://leetcode.com/problems/invert-binary-tree/ </br>
Invert a binary tree.

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: TreeNode) -> TreeNode:

        def invert_binary_tree(root):
            if root:
                if root.left or root.right:
                    root.left, root.right = root.right, root.left
                    invert_binary_tree(root.left)
                    invert_binary_tree(root.right)

        invert_binary_tree(root)

        return root  
```

### Complexity: O(n) , space: O(n)
----------------------
2) https://leetcode.com/problems/delete-node-in-a-linked-list/ </br>
Write a function to delete a node (except the tail) in a singly linked list, given only access to that node..

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def deleteNode(self, node):
        """
        :type node: ListNode
        :rtype: void Do not return anything, modify node in-place instead.
        """
        node.val = node.next.val
        node.next = node.next.next

```
### Complexity: O(1) , space: O(1)
-----------------------
2) https://leetcode.com/problems/two-city-scheduling/ </br>
- There are 2N people a company is planning to interview. The cost of flying the i-th person to city A is costs[i][0], and the cost of flying the i-th person to city B is costs[i][1].
- Return the minimum cost to fly every person to a city such that exactly N people arrive in each city.
```python
class Solution:
    def twoCitySchedCost(self, costs: List[List[int]]) -> int:

        length = len(costs)
        costs = sorted(costs, key=lambda x: x[0]-x[1])

        minimum_to_A = minimum_to_B = 0

        for i in range(length//2):
            minimum_to_A += costs[i][0]

        for i in range(length//2, length):
            minimum_to_B += costs[i][1]

        return minimum_to_A + minimum_to_B
```
### Complexity: O(nlog(n)) , space: O(1)