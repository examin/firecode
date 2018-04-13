## Solution

```
//Populate the list of ancestors from bottom to top in the below list.
public ArrayList<Integer> ancestorsList = new ArrayList<Integer>();
public boolean printAncestors(TreeNode root, int nodeData) {
    if (root==null) return false;
    
    if(root.data == nodeData) return true;

    if(printAncestors(root.left, nodeData)||printAncestors(root.right, nodeData))
    {
        ancestorsList.add(root.data);
        return true;
    }
    
    return false;
}
```

## Notes
