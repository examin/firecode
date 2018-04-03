## Solution

```
public static int[] maxContSequence(int[] arr) {
    if(arr==null) return null;
    if(arr.length==0) return new int[]{0, 0, -1};
    
    int pre = arr[0], start = 0, end = 0;
    int max = arr[0], max_start = 0, max_end = 0;
    
    for(int i=1; i<arr.length; i++)
    {
        if(pre + arr[i]>arr[i])
        {
           end = i;
           pre = pre + arr[i];
        }
        else{
           start = i;
           pre = arr[i];
        }
        
        if(pre>max)
        {
            max = pre;
            max_start = start;
            max_end = end;
        }
    }
    
    return new int[]{max, max_start, max_end};
}

// brute force solution: O(n3)    
//     int[] res = new int[3];
//     res[0] = Integer.MIN_VALUE;
//     helper(arr, res, 0);
//     return res;
// }

// public static void helper(int[] arr, int[] res, int start)
// {
//     if(start>arr.length-1) return;
//     for(int i=start; i<arr.length; i++)
//     {
//         int cur = 0;
//         for(int j=start;j<=i; j++)
//         {
//             cur += arr[j];
//         }
//         if(cur>res[0])
//         {
//             res[0] = cur;
//             res[1] = start;
//             res[2] = i;
//         }
//     }
//     helper(arr, res, start+1);
// }
```

## Notes
1. max sum ending at i is the maximum between "max sum ending at (i-1) + arr[i]" and "arr[i]"

This is called Kadane’s algorithm: https://www.youtube.com/watch?v=MUjOEJLtm6Y

https://leetcode.com/problems/maximum-subarray/discuss/20211/Accepted-O(n)-solution-in-java

2. Keep track of the max sum and its indexes

3. Can be solved with divide conquere approach: https://www.geeksforgeeks.org/divide-and-conquer-maximum-sum-subarray/ 


