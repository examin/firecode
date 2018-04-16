## Solution

```
public ArrayList<Integer> inorderItr(TreeNode root) {
    ArrayList<Integer> list = new ArrayList<>();
    if(root==null) return list;
    
    Stack<TreeNode> st = new Stack<>();
    TreeNode node = root;
    while(node!=null)
    {
        st.push(node);
        node = node.left;
    }

    while(!st.isEmpty())
    {
        TreeNode n = st.pop();
        list.add(n.data);
        
        n = n.right;
        while(n!=null)
        {
            st.push(n);
            n = n.left;
        }
    }
    
    return list;
}
```

## Notes
https://www.geeksforgeeks.org/inorder-tree-traversal-without-recursion/

https://articles.leetcode.com/binary-search-tree-in-order-traversal/
