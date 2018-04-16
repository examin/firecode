## Solution

```
Given a binary search tree and an integer k, implement a method to find and return the kth smallest node. 

public TreeNode findKthSmallest(TreeNode root, int k) {
    List<TreeNode> list = new ArrayList<TreeNode>();
    helper(root, list);
    if(k<=list.size()) 
      return list.get(k-1);
    else
      return null;
}

public void helper(TreeNode root, List<TreeNode> list)
{
    if(root==null) return;
    helper(root.left, list);
    list.add(root);
    helper(root.right, list);
}
```

## Notes

