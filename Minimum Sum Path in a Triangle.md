## Solution

```
public static int minTriangleDepth(ArrayList<ArrayList<Integer>> input) {
    int[] min = new int[1];
    min[0] = Integer.MAX_VALUE;
    if(input==null||input.size()==0) return min[0];
    
    helper(input, 0, 0, 0, min);

    return min[0];
}

public static void helper(ArrayList<ArrayList<Integer>> input, int depth, int index, int sum, int[] min) {
    if(depth==input.size()) 
    {
        min[0] = Math.min(min[0], sum);
        return;
    }
    
    helper(input, depth+1, index, sum+input.get(depth).get(index), min);
    helper(input, depth+1, index+1, sum+input.get(depth).get(index), min);
}
```

## Notes
Trick: moving from bottom to top. (from top to bottom also works

https://www.youtube.com/watch?v=6zcFB1nIoq8

https://medium.com/@davidjgrey/triangle-min-sum-algorithm-4848d778eef
