## Solution

```
public TreeNode findLCA(TreeNode root, TreeNode a, TreeNode b) {
    if(root==null) return null;
    if(root.data == a.data || root.data==b.data) return root;
    
    TreeNode left = findLCA(root.left, a, b);
    TreeNode right = findLCA(root.right, a, b);
    
    if(left==null&&right==null)
       return null;
    if(left!=null&&right!=null)
       return root;
    if(left==null||right==null)
       return left==null?right:left;

    return null;
}
```

## Notes
LSA with BST, find the first node from root that is between a and b: https://www.geeksforgeeks.org/lowest-common-ancestor-in-a-binary-search-tree/
