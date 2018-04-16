## Solution

```
public ArrayList<Integer> levelorder(TreeNode root) {
    if(root==null) return null;
    
    ArrayList<Integer> list = new ArrayList<Integer>();
    Queue<TreeNode> q1 = new LinkedList<TreeNode>();
    Queue<TreeNode> q2 = new LinkedList<TreeNode>();
    q1.add(root);
    
    while(!q1.isEmpty())
    {
        TreeNode node = q1.remove();
        list.add(node.data);
        if(node.left!=null) q2.add(node.left);
        if(node.right!=null) q2.add(node.right);
        
        if(q1.isEmpty())
        {
            q1 = q2;
            q2 = new LinkedList<TreeNode>();
        }
    }
    
    return list;
}

```

## Notes
Doesn't have to use 2 queues. Same as BSF
