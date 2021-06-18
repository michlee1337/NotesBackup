- [[solution attributes]]
    - more of a pattern
    - [[optimal substructure]]
        - "max/ min under changing states when what you do now affects what you can do later"
    - [[extra states]]
        - identify what info you need for solving subsol. in this case, whether you have robbed the parent
- [[algo tricks]]
    - when faced with traversing under different "states", you have two options to avoid n*num_states complexity
        - memoize
        - [[return tuple and reconstruct]]
            - make helper return tuple of answers under all states, and reconstruct current sol before returning 
            - ```javascript
        dp = {}
        
        RobOptions = namedtuple("RobOptions", ["rob_self", "rob_children"])
        
        def helper(cur_node: TreeNode):
            if cur_node is None:
                return RobOptions(0,0)
            left = helper(cur_node.left)
            right = helper(cur_node.right)
            
            rob_self = cur_node.val + left.rob_children + right.rob_children
            rob_children = max(left) + max(right)  # best ans from children, either one

            return RobOptions(rob_self, rob_children)
        
        return max(helper(root))
```
