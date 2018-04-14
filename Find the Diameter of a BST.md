## Solution

```
public int diameter(TreeNode root) {
    if(root==null) return 0;
    
    int leftDiameter = diameter(root.left);
    int rightDiameter = diameter(root.right);
    int leftHeight = findHeight(root.left);
    int rightHeight = findHeight(root.right);
    return Math.max(leftDiameter, Math.max(rightDiameter, leftHeight+rightHeight+1));


}
```

## Notes
The diameter of a tree T is the largest of the following quantities:

* the diameter of T’s left subtree
* the diameter of T’s right subtree
* the longest path between leaves that goes through the root of T (this can be computed from the heights of the subtrees of T)
