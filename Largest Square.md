## Solution

```
public static int largestSquare(char[][] matrix) {
    if(matrix==null||matrix.length==0) return -1;
    int rows = matrix.length;
    int cols = matrix[0].length;
    int[][] res = new int[rows][cols];
    
    int max = Integer.MIN_VALUE;
    for(int i=0; i<rows; i++)
    {
        for(int j=0; j<cols; j++)
        {
            if(Integer.valueOf(matrix[i][j]+"")==0)
            {
               res[i][j] = 0; 
            }else if(i==0||j==0)
            {
               res[i][j] = Integer.valueOf(matrix[i][j]+"");
               
            }else{
               res[i][j] = 1 + Math.min(Math.min(res[i-1][j], res[i][j-1]), res[i-1][j-1]);
            }
            
            max = Math.max(max, res[i][j]);
        }
    }
    
    return max*max;
}
```

## Notes
https://www.youtube.com/watch?v=FO7VXDfS8Gk

1. Treat each cell as the lower right corner of a square
2. if it's 0, then do nothing
3. if it's 1, then find the min value of the top, left, and top-left


