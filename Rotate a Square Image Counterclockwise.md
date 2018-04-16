## Solution

```
public static void rotateSquareImageCCW(int[][] matrix) {
    if(matrix==null) return;
    
    int rows = matrix.length;
    int cols = matrix[0].length;
    
    for(int i=0; i<cols; i++)
    {
        for(int j=i+1; j<rows; j++)
        {
            int temp = matrix[j][i];
            matrix[j][i] = matrix[i][j];
            matrix[i][j] = temp;
        }
    }
    
    int mid = (cols-1)/2;
    
    for(int k=0; k<=mid; k++)
    {
        int[] temp = matrix[k];
        matrix[k] = matrix[cols-1-k];
        matrix[rows-1-k] = temp;
    }
    
}
```

## Notes

