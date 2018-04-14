## Solution

```
public static ArrayList<Integer> findSpiral(int[][] arr) {
    if (arr==null|| arr.length==0) return null;
    ArrayList<Integer> list = new ArrayList<Integer>();
    int rows = arr.length;
    int cols = arr[0].length;
    getRect(list, arr, 0, 0, cols-1, rows-1);
    return list;
}

public static void getRect(ArrayList<Integer> list, int[][] arr, int x1, int y1, int x2, int y2)
{
    if(x1>x2|| y1>y2) return;
    
    if(y1==y2)
    {
        for(int i=x1; i<=x2; i++)
        {
            list.add(arr[y1][i]);
        }
        return;
    }
    
    if(x1==x2)
    {
        for(int i=y1; i<=y2; i++)
        {
            list.add(arr[i][x2]);
        }
        return;
    }
    
    for(int i=x1; i<x2; i++)
        list.add(arr[y1][i]);
    
    for(int j=y1; j<y2; j++)
        list.add(arr[j][x2]);
    
    for(int k=x2; k>x1; k--)
        list.add(arr[y2][k]);
    
    for(int h=y2; h>y1; h--)
        list.add(arr[h][y1]);
    
    getRect(list, arr, x1+1, y1+1, x2-1, y2-1);
}
```

## Notes

