## Solution

```
public int getNodeDistance(TreeNode root, int n1, int n2) {
    if(root==null) return -1;
    TreeNode node = getLowestCommonNode(root, n1, n2);
    int depth1 = getDepth(root, node.data);
    int depth2 = getDepth(root, n1);
    int depth3 = getDepth(root, n2);
    
    return (depth2-depth1) + (depth3 - depth1);
}

//key: You can assume that the given keys exist in the tree
public TreeNode getLowestCommonNode(TreeNode root, int n1, int n2)
{
    if(root==null) return null;
    
    if(root.data==n1||root.data==n2) return root;
    
    TreeNode left = getLowestCommonNode(root.left, n1, n2);
    TreeNode right = getLowestCommonNode(root.right, n1, n2);
    
    if(left==null&&right==null) return null;
    if(left!=null&&right!=null) return root;
    if(left!=null) 
       return left;
    else 
       return right;
}

public int getDepth(TreeNode root, int n)
{
    if(root==null) return -1;
    
    Queue<TreeNode> q = new LinkedList<>();
    q.add(root);
    int count = 1;
    
    while(!q.isEmpty())
    {
        int size = q.size();
        for(int i=0; i<size; i++)
        {
            TreeNode node = q.remove();
            if(node.data==n)
               return count;
            if(node.left!=null) q.add(node.left);
            if(node.right!=null) q.add(node.right);
        }
        
        if(!q.isEmpty()) count++;
    }
    
    return -1;
}
```

## Notes
https://www.geeksforgeeks.org/lowest-common-ancestor-binary-tree-set-1/

Another easy-to-understand way is to find the path to each node and find the first mismatch (but requires extra space)

https://www.youtube.com/watch?v=13m9ZCB8gjw
