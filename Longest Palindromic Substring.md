## Solution

```
public String longestPalSubstr(String str){
    if(str==null) return null;
    if(str.length()==0) return "";
    
    int l = str.length();
    boolean[][] res = new boolean[l][l];
    
    int max = 0;
    int start = 0;
    int end = 0;
    for(int i=0; i<l; i++)
    {
        res[i][i] = true;
        if(i+1<=l-1&&str.charAt(i)==str.charAt(i+1))
        {
           res[i][i+1] = true;
           start = i;
           end = i+1;
        }
    }
    
    for(int k=2; k<l; k++)
    {
        for(int i=0; i<l; i++)
        {
            int j = i+k;
            if(j<=l-1&&str.charAt(i)==str.charAt(j)&&res[i+1][j-1]==true)
            {
                res[i][j] = true;
                if(j-i>max)
                {
                    start = i;
                    end = j;
                }
            }
        }
    }
    
    return str.substring(start, end+1);
    
}

// public void helper(String str, boolean[][] res, int start, int end)
// {
//     if(start>end||start<0||end>str.length-1) return;
//     if(start == end)
//     {
//         res[start][end] = true;
//         return;
//     }
// }
```

## Notes
0. Brute-force: O(n3)
1. DP approach: https://www.youtube.com/watch?v=Fi5INvcmDos
(row-start, col-end)
Key: str.charAt(i)==str.charAt(j)&&res[i+1][j-1]==true

2.str.charAt(i) return char

3.can be improved through recursion (helper function)

4.Expand from center approach: https://leetcode.com/problems/longest-palindromic-substring/solution/



