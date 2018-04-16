## Solution

```
public static int makeChange(int[] coins, int amount) {
    if(coins==null||amount<=0) return 0;
    int[][] results = new int[amount][coins.length];
    for(int[] result:results)
    {
       Arrays.fill(result, -1); 
    }
    return helper(coins, coins.length-1, amount, results);

}

public static int helper(int[] coins, int endIndex, int amount, int[][] results)
{
    if(amount==0) return 1;
    if(amount<0) return 0;
    if(endIndex<0) return 0;
    
    int val = results[amount-1][endIndex];
    if(val!=-1) return val;
    
    val = helper(coins, endIndex-1, amount, results) + helper(coins, endIndex, amount-coins[endIndex], results);
    results[amount-1][endIndex] = val;
    
    return val;
}
```

## Notes
Use dynamic programming, O(amount*length(conins))
https://www.geeksforgeeks.org/dynamic-programming-set-7-coin-change/
DP properties: 1) Overlapping Subproblems
2) Optimal Substructure
Related problem: https://leetcode.com/problems/coin-change/discuss/77368/*Java*-Both-iterative-and-recursive-solutions-with-explanations
