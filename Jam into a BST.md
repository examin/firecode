## Solution

```
public TreeNode insert(TreeNode root, int data) { 
    TreeNode node = new TreeNode(data);
    
    if(root==null) return node;
    
    if(data>root.data)
    {
        if(root.right!=null)
          insert(root.right, data);
        else
          root.right = node;
    }
    
    if(data<root.data)
    {
        if(root.left!=null)
          insert(root.left, data);
        else
          root.left = node;
    }
    
    return root;
}
```

## Notes
1. Recursion
2. Iterative 
public TreeNode insert(TreeNode root, int data) { 
    if(root == null) {
        return new TreeNode(data);
    }
    
    TreeNode current = root;
    while(true) {
        if(data <= current.data) {
            if(current.left != null) {
                current = current.left;
            } else {
                current.left = new TreeNode(data);
                return root;
            }
        } else {
            if(current.right != null) {
                current = current.right;
            } else {
                current.right = new TreeNode(data);
                return root;
            }
        }
    }
}