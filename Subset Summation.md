## Solution

```
public static boolean groupSum(int[] arr, int target) {
    if(arr==null||arr.length==0) return false;
    return helper(arr, target, 0);
  
}

public static boolean helper(int[] arr, int target, int index) {
    if(index>arr.length-1||target<0) return false;
    
    if(target==0) return true;
    
    //break down the problem to 2 subproblems: one contains a[i], one does not
    if(helper(arr, target-arr[index], index+1)||helper(arr, target, index+1)) return true;

    return false;
}
```

## Notes
public static boolean groupSum(int[] arr, int target) {
    if(arr==null||arr.length==0) return false;
    return helper(arr, target, 0);
  
}

public static boolean helper(int[] arr, int target, int index) {
    if(index>arr.length-1||target<0) return false;

    for(int i=index; i<arr.length; i++)
    {
        int x = target-arr[i];
        for(int j=i+1; j<arr.length; j++)
        {
            if(x==arr[j]) 
              return true;
            else
              return helper(arr, x-arr[j], j+1);
        }
    }
    
    return false;
}

Related problem: https://www.youtube.com/watch?v=nqlNzOcnCfs
Find the # of sets of numbers that add up to a given target
