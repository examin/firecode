## Solution

```
public static int matrixMaxSumDP(int[][] grid) {
    if(grid==null||grid.length==0) return 0;
    int rows = grid.length;
    int cols = grid[0].length;
    int[][] results = new int[rows][cols];
    return helper(grid, 0, 0, results);
    
}

public static int helper(int[][] grid, int x, int y, int[][] results)
{
    int rows = grid.length;
    int cols = grid[0].length;
    if(x>cols-1||y>rows-1) return 0;
    
    if(results[y][x]!=0) return results[y][x];
    
    results[y][x] = grid[y][x] + Math.max(helper(grid, x+1, y, results), helper(grid, x, y+1, results));
    
    return results[y][x];
}
```

## Notes

