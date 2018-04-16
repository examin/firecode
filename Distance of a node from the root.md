## Solution

```
public int pathLengthFromRoot(TreeNode root, int n1) {
   class TreeDepthNode{
        TreeNode node;
        int depth;
        TreeDepthNode(TreeNode node, int depth)
        {
            this.node = node;
            this.depth = depth;
        }
   }
   
   if(root==null) return -1;
   Queue<TreeDepthNode> q= new LinkedList<TreeDepthNode>();
   q.add(new TreeDepthNode(root, 1));
   while(!q.isEmpty())
   {
       TreeDepthNode t_node = q.remove();
       TreeNode t = t_node.node;
       if(t.data==n1) return t_node.depth;
       if(t.left!=null) q.add(new TreeDepthNode(t.left, t_node.depth+1));
       if(t.right!=null) q.add(new TreeDepthNode(t.right, t_node.depth+1));
   }
   
   return -1;
}
```

## Notes
```
public int pathLengthFromRoot(TreeNode root, int n1) {
   return helper(root, n1, 0);
}

public int helper(TreeNode root, int n1, int depth)
{
    if(root==null) return Integer.MAX_VALUE;
    if(root.data == n1) return depth+1;
    int right = helper(root.right, n1, depth+1);
  
    return right<Integer.MAX_VALUE?right:helper(root.left, n1, depth+1);
}
```


