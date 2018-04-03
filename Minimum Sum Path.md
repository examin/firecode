## Solution

```
public static int minWeightedPath(int[][] grid) {
    if(grid==null||grid.length==0) return 0;
    
    int rows = grid.length;
    int cols = grid[0].length;
    
    int[][] res = new int[rows][cols];
    helper(grid, 0, 0, res);
    
    return res[0][0];
}

public static int helper(int[][] grid, int row, int col, int[][] res)
{
    int rows = grid.length;
    int cols = grid[0].length;
    if(row==rows-1&&col==cols-1) return grid[row][col];
    if(row>rows-1||col>cols-1) return Integer.MAX_VALUE;
    
    if(res[row][col]!=0) return res[row][col];
    
    res[row][col] = grid[row][col] + Math.min(helper(grid, row+1, col, res), helper(grid, row, col+1, res));
    return res[row][col];
}
```

## Notes
A little different than max sum:

1) if(row>rows-1||col>cols-1) return Integer.MAX_VALUE; (rather than return 0)

2) extra line: if(row==rows-1&&col==cols-1) return grid[row][col];


