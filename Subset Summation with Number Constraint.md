## Solution

```
public static boolean groupSumWithNum(int[] arr, int must_have, int target) {
    if(arr==null||arr.length==0) return false;
    boolean tag = false;
    for(int a:arr)
    {
        if(a==must_have)
        {
            tag= true;
            break;
        }
    }
    if(!tag)
      return helper(arr, must_have, target, arr.length-1);
    else
      return helper(arr, must_have, target-must_have, arr.length-1);
}
public static boolean helper(int[] arr, int must_have, int target, int i)
{
    if(target==0) return true;
    if(i<0) return false;
    
    if(arr[i]!=must_have)
      return helper(arr, must_have, target, i-1)||helper(arr, must_have, target-arr[i], i-1);
    else
      return helper(arr, must_have, target, i-1);
}
```

## Notes

