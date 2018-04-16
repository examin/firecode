## Solution

```
Given a binary tree, write a method to return the level that has the maximum sum. In case the tree is empty, return -1 

public int findMaxSumLevel(TreeNode root) { 
    class TreeDNode
    {
        int depth;
        TreeNode node;
        TreeDNode(int depth, TreeNode node)
        {
            this.depth = depth;
            this.node = node;
        }
    }
    if(root==null) return -1;
    int max_sum = Integer.MIN_VALUE;
    int max_depth = 0;
    int sum = 0;
    int cur_depth = 0;
    Queue<TreeDNode> q = new LinkedList<>();
    q.add(new TreeDNode(0, root));
    
    while(!q.isEmpty())
    {
        TreeDNode td = q.remove();
        TreeNode node = td.node;
        if(cur_depth==td.depth) 
           sum += node.data;
        else
        {
           if(sum>max_sum)
           {
               max_sum=sum;
               max_depth = cur_depth;
           }
           sum = node.data;
           cur_depth = td.depth;
        }
        
        if(node.left!=null) q.add(new TreeDNode(td.depth+1, node.left));
        if(node.right!=null) q.add(new TreeDNode(td.depth+1, node.right));
    }
    
    if(sum>max_sum) max_depth = cur_depth; //don't forget to check the last level
    
    return max_depth;
}
```

## Notes
```
1. One queue solution

while(!q.isEmpty()){
        int sum = 0;
        int total = q.size(); //key
        for(int i = 0; i < total; i++){
            TreeNode curr = q.remove();
            sum += curr.data;
            if(curr.left!=null) q.add(curr.left);
            if(curr.right != null) q.add(curr.right);
        }
        if(sum > maxSum){
            maxSum = sum;
            maxCount = count;
        }
        count++;
    }

2. Add "null" solution (official solution)

3. Two queue solution (check the stackflow)
```
