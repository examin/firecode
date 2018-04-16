## Solution

```
Given a Binary Search Tree, return the node with the maximum data. 

public TreeNode findMax(TreeNode root) {
    if(root==null) return null;
    
    if(root.right==null) return root;
    
    return findMax(root.right);   
}
```

## Notes

