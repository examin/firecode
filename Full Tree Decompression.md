## Solution

```
public TreeNode decompressTree(String str){
    if(str==null) return null;
    
    ArrayList<String> list = new ArrayList<String>(Arrays.asList(str.split(",")));
    return helper(list, 0);
    
}

public TreeNode helper(ArrayList<String> list, int i)
{
    if(i>list.size()-1||list.get(i).equals("*")) 
       return null;
    
    TreeNode node = new TreeNode();
    node.data = Integer.valueOf(list.get(i));
    int left_index = 2*i+1;
    int right_index = left_index+1;
    node.left = helper(list, left_index);
    node.right = helper(list, right_index);
    
    return node;
}
```

## Notes

