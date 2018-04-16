## Solution

```
Given a binary tree, write a method to find and return its deepest node. Return null for an empty tree. 

public TreeNode findDeepest(TreeNode root) {
    class TreeDNode{
        TreeNode node;
        int depth;
        TreeDNode(TreeNode node, int depth)
        {
            this.node = node;
            this.depth = depth;
        }
    }
    if(root==null) return null;
    
    Queue<TreeDNode> q = new LinkedList<>();
    TreeDNode td = new TreeDNode(root, 0);
    q.add(td);
    
    TreeDNode max = td;
    while(!q.isEmpty())
    {
        td = q.remove();
        if(td.depth>max.depth) max = td;
        TreeNode tn = td.node;
        if(tn.right!=null) q.add(new TreeDNode(tn.right, td.depth+1));
        if(tn.left!=null) q.add(new TreeDNode(tn.left, td.depth+1));
    }
    
    return max.node;

}
```

## Notes
Simple solution: Traverse the tree level by level. The last node at the last level of the tree is the deepest node
