## Solution

```
public static int maxSumPath(TreeNode root) {
    if (root==null) return 0;
    
    int leftsum = maxSumPath(root.left);
    int rightsum = maxSumPath(root.right);
    int rootsum = findRootMax(root.left) + findRootMax(root.right) + root.data;
    
    return Math.max(Math.max(leftsum, rightsum), rootsum);
    
}


public static int findRootMax(TreeNode root) {
    if (root==null) return 0;
    
    int left = findRootMax(root.left);
    int right = findRootMax(root.right);
    return Math.max(left, right) + root.data;
}
```

