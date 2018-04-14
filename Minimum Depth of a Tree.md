## Solution

```
public int minTreeDepth(TreeNode root) {
    if(root==null) return 0;
    
    Queue<TreeNode> q1 = new LinkedList<TreeNode>();
    Queue<TreeNode> q2 = new LinkedList<TreeNode>();

    q1.add(root);
    int depth = 1;
    
    while(!q1.isEmpty())
    {
        TreeNode node = q1.remove();
        if(node.right==null&&node.left==null) 
           return depth;
        if(node.right!=null)
           q2.add(node.right);
        if(node.left!=null)
           q2.add(node.left);

        if(q1.isEmpty()) 
        {
            q1 = q2;
            q2 = new LinkedList<TreeNode>();
            depth++;
        }
    }
    
    return depth;   
}
```

## Notes
Solution 1: Use Level Order Traversal, two queue version, one queue version

Soltuion 2: create two queues, but the other queue to store corresponding depth https://www.programcreek.com/2013/02/leetcode-minimum-depth-of-binary-tree-java/

Solution 3: create another class or hashmap/dic, node->depth https://www.geeksforgeeks.org/find-minimum-depth-of-a-binary-tree/

Solution 4: recursion
