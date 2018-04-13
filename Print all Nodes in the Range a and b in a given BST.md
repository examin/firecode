## Solution

```
public  ArrayList<Integer> rangeList = new ArrayList<Integer>();
public void printRange(TreeNode root, int a, int b) {
    if(root==null) return;
    
    if(root.data < a) 
    {
        printRange(root.right, a, b);
    }
    if(root.data > b) {
        printRange(root.left, a, b);
    }
    
    if (root.data >= a && root.data <= b) {
        printRange(root.left, a, b);
        rangeList.add(root.data);
        printRange(root.right, a, b);
    } 
    
    // inorderSearch(root);
    
    // ArrayList<Integer> output = new ArrayList<Integer>();
    // for(Integer i: rangeList)
    // {
    //     if(i>=a && i<=b)
    //       output.add(i);
    // }
    // rangeList = output;
}

// public void inorderSearch(TreeNode root)
// {
//     if(root==null) return;
//     inorderSearch(root.left);
//     rangeList.add(root.data);
//     inorderSearch(root.right); 
// }
```

## Notes
