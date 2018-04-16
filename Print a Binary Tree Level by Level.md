## Solution

```
public ArrayList<ArrayList<Integer>> printLevelByLevel(TreeNode root) {
        ArrayList<ArrayList<Integer>> output = new ArrayList<ArrayList<Integer>>();

        if(root==null) return output;
        
        Queue<TreeNode> q1 = new LinkedList<TreeNode>();
        Queue<TreeNode> q2 = new LinkedList<TreeNode>();
        q1.add(root);
        
        ArrayList<Integer> list1 = new ArrayList<Integer>();
        while(!q1.isEmpty())
        {
            TreeNode node = q1.remove();
            list1.add(node.data);
            if(node.left!=null) q2.add(node.left);
            if(node.right!=null) q2.add(node.right);
            
            if(q1.isEmpty())
            {
                output.add(list1);
                q1 = q2;
                q2 = new LinkedList<TreeNode>();
                list1 = new ArrayList<Integer>();
            }
        }
        
        return output;
}
```

## Notes

