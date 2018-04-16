## Solution

```
Write a method to check if the two given binary trees are the mirror images of each other. Return true if they are, false otherwise. What's a binary tree's mirror image? Hold it by the root and rotate all other nodes by 180 degrees! 

public boolean isMirror(TreeNode root1, TreeNode root2) {
    if(root1==null&&root2==null) return true;
    if(root1==null||root2==null) return false;
    
    Queue<TreeNode> q1 = new LinkedList<>();
    Queue<TreeNode> q2 = new LinkedList<>();
    q1.add(root1);
    q2.add(root2);
    
    while(!q1.isEmpty()&&!q2.isEmpty())
    {
        TreeNode n1 = q1.remove();
        TreeNode n2 = q2.remove();
        if(n1.data!=n2.data) return false;
        
        if(n1.left!=null) q1.add(n1.left);
        if(n1.right!=null) q1.add(n1.right);
        
        if(n2.right!=null) q2.add(n2.right);
        if(n2.left!=null) q2.add(n2.left);
    }
    
    if(!q1.isEmpty()||!q2.isEmpty()) return false;
    
    return true;
}
```

## Notes
Recursive solution:

if (root1 == null && root2 == null) return true;
    if (root1 == null || root2 == null) return false;
    if (root1.data != root2.data) return false;
    return isMirror(root1.left, root2.right) && isMirror(root2.left, root1.right);
