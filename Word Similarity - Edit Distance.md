## Solution

```
public int editDistance(String a, String b){
    if(a==null&&b==null) return 0;
    int l1 = a.length();
    int l2 = b.length();
    int[][] memo = new int[l2+1][l1+1];
    for(int[] m:memo)
    {
        Arrays.fill(m, -1);
    }
    return helper(a, b, l2, l1, memo);
}

public int helper(String a, String b, int x, int y, int[][] memo)
{
    if(memo[x][y]!=-1) return memo[x][y];
    
    if(x==0) 
    {
       memo[x][y] = y;
       return y;
    }
    if(y==0) 
    {
       memo[x][y] = x;
       return x;
    }
    
    if(b.charAt(x-1)==a.charAt(y-1))
      return helper(a, b, x-1, y-1, memo);
    else
    {
      memo[x][y] = 1+Math.min(Math.min(helper(a, b, x-1, y-1, memo), helper(a, b, x-1, y, memo)), helper(a, b, x, y-1, memo));
      return memo[x][y];
    }
}
```

## Notes
https://www.youtube.com/watch?v=We3YDTzNXEk

First of all, if two characters are same, you don't do anything, that's clear right? If not, then there's 3 possible moves: delete, replace and insert. 

Suppose your rows represents str1, cols represents str2. If you wanna delete, you go back to previous column, which is T[i][j-1], because you'd like to retrieve the last character in str2. Similarly, if you wanna insert, you go back to previous row, which is T[i-1][j]. For replacing current character, you need to retrieve last character in both str1 and str2, which is T[i-1][j-1]. At last, you get the minimum among the above 3 moves and plus 1 to it to get T[i][j].

BTW， edit distance is symmetric (can be used to further improve the accuracy).
