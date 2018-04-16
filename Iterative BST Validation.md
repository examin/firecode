## Solution

```
public static boolean validateBSTItr(TreeNode root) {
    if(root==null) return true;
    class TreeBoundNode
    {
        TreeNode node;
        int leftB;
        int rightB;
        TreeBoundNode(TreeNode node, int leftB, int rightB)
        {
           this.node = node;
           this.leftB = leftB;
           this.rightB = rightB; 
        }
    }
    
    Queue<TreeBoundNode> q = new LinkedList<TreeBoundNode>();
    q.add(new TreeBoundNode(root, Integer.MIN_VALUE, Integer.MAX_VALUE));
    while(!q.isEmpty())
    {
        TreeBoundNode t_node = q.remove();
        TreeNode t = t_node.node;
        if(t.data<=t_node.leftB || t.data>=t_node.rightB) return false;
        if(t.left!=null) 
          q.add(new TreeBoundNode(t.left, t_node.leftB, t.data));
        if(t.right!=null) 
          q.add(new TreeBoundNode(t.right, t.data, t_node.rightB));
    }
    
    return true;
}
```

## Notes
```
Solution: recursvie 1, O(n2)
public static boolean validateBSTItr(TreeNode root) {
    if(root==null) return true;
    int left = findMax(root.left);
    int right = findMin(root.right);
    
    if(left<root.data && right>root.data && validateBSTItr(root.left) && validateBSTItr(root.right))
       return true;
    
    return false;
}

public static int findMax(TreeNode root)
{
    if(root==null) return Integer.MIN_VALUE;
    int left = findMax(root.left);
    int right = findMax(root.right);
    
    return Math.max(Math.max(left,right),root.data);
}

public static int findMin(TreeNode root)
{
    if(root==null) return Integer.MAX_VALUE;
    int left = findMin(root.left);
    int right = findMin(root.right);
    
    return Math.min(Math.min(left,right),root.data);
}

Solution 2: in-order traversal to see if it is always increasing

Solution 3: 
IsValidBST(root,-infinity,infinity);

bool IsValidBST(BinaryNode node, int MIN, int MAX) 
{
     if(node == null)
         return true;
     if(node.element > MIN 
         && node.element < MAX
         && IsValidBST(node.left,MIN,node.element)
         && IsValidBST(node.right,node.element,MAX))
         return true;
     else 
         return false;
}
```
