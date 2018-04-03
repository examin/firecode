## Solution

```
public static ArrayList<ArrayList<Integer>> generatePascalTriangle(int numRows) {
    ArrayList<ArrayList<Integer>> lists = new ArrayList<>();
    if(numRows<1) return lists;
    
    for(int i=0; i<numRows; i++)
    {
        //ArrayList<Integer> list = new ArrayList<>(i+1);
        ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(new Integer[i+1]));
        helper(lists, list, i+1);
    }
    return lists;
}

public static void helper(ArrayList<ArrayList<Integer>> lists, ArrayList<Integer> list, int row)
{
    int size = list.size();
    list.set(0, 1);
    list.set(size -1, 1);
    for(int i=1; i<size-1&&row>2; i++)
    {
        list.set(i, lists.get(row-2).get(i-1) + lists.get(row-2).get(i));
    }
    lists.add(list);
}
```

## Notes
1. create a fixed size of list Arrays.asList(new Integer[i+1])
2. convert list to arraylist
new ArrayList<>(list)
3. set(index, val)
4. ArrayList<Integer> list = new ArrayList<>(i+1); is to set the capacity, not the size. set(0, val) can cause an error

Simpler solution:
public static ArrayList<ArrayList<Integer>> generatePascalTriangle(int numRows) {
    ArrayList<ArrayList<Integer>> result = new ArrayList<ArrayList<Integer>>();
    if (numRows <= 0)
      return result;
   
    ArrayList<Integer> pre = new ArrayList<Integer>();
    pre.add(1);
    result.add(pre);
   
    for (int i = 2; i <= numRows; i++) {
      ArrayList<Integer> cur = new ArrayList<Integer>();
   
      cur.add(1); //first
      for (int j = 0; j < pre.size() - 1; j++) {
        cur.add(pre.get(j) + pre.get(j + 1)); //middle
      }
      cur.add(1);//last
   
      result.add(cur);
      pre = cur;
    }
   
    return result;
  }


