## Solution

```
public int countPaths(int m, int n){
    int[][] memo = new int[m][n];
    //Arrays.fill(memo, -1);
    //int rows = memo.length();
    //int cols = memo[0].length();
    return helper(memo, m, n);
}

public int helper(int[][] memo, int m, int n)
{
    if(memo[m-1][n-1]!=0) 
       return memo[m-1][n-1];
    
    if(m==1 || n==1) 
      return 1;
    else
    {
      memo[m-1][n-1] = helper(memo, m-1, n) + helper(memo, m, n-1);
      return memo[m-1][n-1];
    }
}
```

## Notes
```
Dynamic programming

Iterative solution
    int x = 1;
    int x0 = m+n-2;
    int i=0;
    while(i<n-1)
    {
       x = x * x0;
       x0--;
       i++;
    }
    
    int y= 1;
    int y0 = n-1;
    i=0;
    while(i<n-1)
    {
       y = y * y0;
       y0--;
       i++;
    }
    
    return x/y;
```
