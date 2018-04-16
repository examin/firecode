## Solution

```
You are given an n x n square 2D matrix that represents the pixels of an image.
Rotate it by 90 degrees in the clockwise direction.


public static int[][] rotate(int[][] matrix) {
    if(matrix==null||matrix.length==0) return null;
    
    int rows = matrix.length;
    int cols = matrix[0].length;
    
    int[][] output = new int[rows][cols];
    for(int i=0; i<cols; i++)
    {
        for(int j=0; j<rows; j++)
        {
            output[i][j] = matrix[cols-1-j][i];
        }
    }
    
    return output;
}
```

## Notes

