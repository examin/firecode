## Solution

```
public int findMax(TreeNode root) {
    if (root==null) return Integer.MIN_VALUE;
    
    int val1 = findMax(root.right);
    int val2 = findMax(root.left);
    
    int max = root.data>val1?root.data:val1;
    
    
    return val2>max?val2:max;   
}
```

## Notes
