- notes
    - ugh, recursion headache
    - [[review]]
- Q:
    - Given the root of a binary tree, flatten the tree into a "linked list":
        - The "linked list" should use the same TreeNode class where the right child pointer points to the next node in the list and the left child pointer is always null.
        - The "linked list" should be in the same order as a [**pre-order**** traversal**](https://en.wikipedia.org/wiki/Tree_traversal#Pre-order,_NLR) of the binary tree.
- sol 1: brute force, linear space and time
    - ```python
        # edge case
        if root is None:
            return []
        
        # pre populate
        stack = [root]
        dummy = TreeNode() # avoid prepolutaing
        head, cur = dummy, dummy
                
        while stack:
            node = stack.pop()
            if node.right is not None:
                stack.append(node.right)                
            if node.left is not None:
                stack.append(node.left)
            # add self
            cur.left, cur.right = None, node
            cur = cur.right
        return dummy.right```
- sol 2: reversed preorder reorder: more efficient for sparse trees, constant space, move at branch joints
    - https://leetcode.com/problems/flatten-binary-tree-to-linked-list/discuss/940394/Python3-Iterative-Solution-With-Explanation
- 
