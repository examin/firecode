## Solution

```
class TreeNode2{
        TreeNode parent;
        TreeNode node;
        boolean left;
        TreeNode2(TreeNode parent,  TreeNode node, boolean left){
            this.parent = parent;
            this.node = node;
            this.left = left;
        }
    }

public TreeNode delete(TreeNode root, int data) {
    if(root==null) return null;
    TreeNode2 node2 = getNode(root, data);
    if(node2==null) return null;
    TreeNode node = node2.node;
   
    if(node.left==null&&node.right==null)
    {
        if(node2.parent==null) return null;
        if(node2.left==true) 
          node2.parent.left=null;
        else
          node2.parent.right = null;
    }
    
    if(node.left==null||node.right==null)
    {
        TreeNode child = node.left!=null?node.left:node.right;
        if(node2.parent==null) return child;
        if(node2.left==true) 
          node2.parent.left=child;
        else
          node2.parent.right = child;
    }
    
    if(node.left!=null&&node.right!=null)
    {
        TreeNode replace = getMinNode(node.right);
        replace.left = node.left;
        if(node2.left==true) 
          node2.parent.left=replace;
        else
          node2.parent.right = replace;
    }
    
    return root;
}

public TreeNode2 getNode(TreeNode root, int data)
{
    Stack<TreeNode2> st = new Stack<>();
    st.push(new TreeNode2(null, root, true));
    while(!st.isEmpty())
    {
        TreeNode2 node2 = st.pop();
        TreeNode node = node2.node;
        if(node.data == data) return node2;
        if(node.left!=null) st.push(new TreeNode2(node, node.left, true));
        if(node.right!=null) st.push(new TreeNode2(node, node.right, false));
    }
    
    return null;
}

public TreeNode getMinNode(TreeNode root)
{
    TreeNode cur = root;
    TreeNode pre = null;
    while(cur.left!=null)
    {
        pre = cur;
        cur = cur.left;
    }
    
    if(pre!=null) pre.left = null;
    return cur;
}
```

## Notes
https://www.quora.com/How-can-I-delete-node-from-binary-search-tree
check 3 conditions:
    if(node.left==null&&node.right==null)
    if(node.left==null||node.right==null)
    if(node.left!=null&&node.right!=null)
