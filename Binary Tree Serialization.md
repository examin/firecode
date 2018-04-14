## Solution

```
public String serializeTree(TreeNode root){
    if(root==null) return null;
    StringBuilder sb = new StringBuilder();
    preOrderSearch(root, sb);
    return sb.toString();
}

public void preOrderSearch(TreeNode root, StringBuilder sb)
{
    if(root==null) 
    {
       sb.append("-1"+",");
       return;
    }
    sb.append(root.data + ",");
    preOrderSearch(root.left, sb);
    preOrderSearch(root.right, sb); 
}

public TreeNode restoreTree(String str){
    if(str==null) return null;
    Queue<String> q = new LinkedList<>(Arrays.asList(str.split(",")));
    return helper(q);
}

public TreeNode helper(Queue<String> q)
{
    if(q.isEmpty()) return null;

    String str = q.remove();
    if(!str.equals("-1"))
    {
        TreeNode node = new TreeNode(Integer.valueOf(str));
        node.left = helper(q);
        node.right = helper(q);
        return node;
    }else
        return null;
}
```

## Notes
https://www.geeksforgeeks.org/serialize-deserialize-binary-tree/

- pre-order search (root at the head)
- if we use post-order search, the root node would be at the end

https://www.geeksforgeeks.org/construct-complete-binary-tree-given-array/
