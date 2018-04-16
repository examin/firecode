## Solution

```
static int max = -1;
public static int matrixMaxSumDfs(int[][] grid) {
    if(grid==null) return -1;
    max = -1;
    helper(grid, 0, 0, 0);
    return max;
}

public static void helper(int[][] grid, int x1, int y1, int sum) {
    int rows = grid.length;
    int cols = grid[0].length;
    
    if((x1==cols&&y1==rows-1)||(x1==cols-1&&y1==rows)) 
    {
        max = sum>max?sum:max;
        return;
    }
    
    if(x1>=cols||y1>=rows) 
        return;

    helper(grid, x1+1, y1, sum+grid[y1][x1]);
    helper(grid, x1, y1+1, sum+grid[y1][x1]);
}
```

## Notes

