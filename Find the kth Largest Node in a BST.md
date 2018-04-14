## Solution

```
public TreeNode findKthLargest(TreeNode root, int k) {
    if (root==null) return null;
    
    List<TreeNode> list = new ArrayList<>();
    
    search(root, list, k);
    
    return list.get(k-1);
}

public static void search(TreeNode root, List<TreeNode> list, int k)
{
    if(list.size()==k) return;

    if(root.right!=null)
       search(root.right, list, k);
       
     list.add(root);
       
    if(root.left!=null) 
       search(root.left, list, k);
}
```

## Notes
Hard to do (revers) in-order search with stack https://www.geeksforgeeks.org/inorder-tree-traversal-without-recursion/
