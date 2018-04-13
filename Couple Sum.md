## Solution

```
public static int[] coupleSum(int[] numbers, int target) {
    Map<Integer, Integer> map = new HashMap<Integer, Integer>();
    for(int i=0; i<numbers.length; i++)
    {
        int remain = target - numbers[i];
        if(map.get(remain)==null)
           map.put(numbers[i], i+1);
        else
           return new int[]{map.get(remain), i+1};
    }
    return null;
}
```

## Notes
Use Hashmap to do it in a single pass. 