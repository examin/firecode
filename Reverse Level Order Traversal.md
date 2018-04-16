## Solution

```
public ArrayList<Integer> levelorderRev(TreeNode root) {
    ArrayList<Integer> list = new ArrayList<>();
    if(root==null) return list;
    
    Queue<TreeNode> q = new LinkedList<>();
    q.add(root);
    
    Stack<TreeNode> st = new Stack<>();
    
    while(!q.isEmpty())
    {
        TreeNode node = q.remove();
        st.push(node);
        
        if(node.right!=null) q.add(node.right);
        if(node.left!=null) q.add(node.left);
    }
    
    while(!st.isEmpty())
    {
        list.add(st.pop().data);
    }
    
    return list;
}
```

## Notes
Use both queue and stack.

use queue to do level order traversal, and store nodes into stack

