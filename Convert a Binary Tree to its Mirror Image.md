## Solution

```
Write a function to convert a binary tree into its mirror image and return the root node of the mirrored tree. 

public TreeNode mirror(TreeNode root) {
    if(root==null) return null;
    
    TreeNode temp = root.right;
    root.right = root.left;
    root.left = temp;
    
    mirror(root.left);
    mirror(root.right);
    
    return root;                    
}
```

## Notes

