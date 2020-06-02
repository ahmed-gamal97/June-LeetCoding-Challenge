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