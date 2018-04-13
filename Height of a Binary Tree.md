## Solution

```
public int findHeight(TreeNode root) { 
    if (root==null) return 0;
    
    if(root.right==null && root.left==null)
       return 1;

    int left = findHeight(root.left);
    int right = findHeight(root.right);
    
    int max = left>right ? left:right;
    
    return max + 1;

}
```

## Notes
Level order traversal: find out the depth of the last node