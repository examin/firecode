## Solution

```
public static ArrayList<Interval> mergeIntervals(ArrayList<Interval> intervalsList) {
    class InterComp implements Comparator<Interval>{
        public int compare(Interval a, Interval b)
        {
            return Integer.compare(a.start, b.start);
        }
        
    }
    
    Collections.sort(intervalsList, new InterComp());
    
    ArrayList<Interval> list = new ArrayList<>();
    if(intervalsList==null||intervalsList.size()==0) return list;
    
    Interval pre = intervalsList.get(0);
    Interval cur = null;
    int i=1;
    while(i<intervalsList.size())
    {
        cur = intervalsList.get(i);
        if(pre.end<cur.start)
        {
            list.add(pre);
            pre = cur;
        }else{
            cur = new Interval(pre.start, Math.max(cur.end, pre.end));
            pre = cur;
        }
        i++;
    }
    
    list.add(pre);
    
    return list;
}

```

## Notes
Inner class cannot be public.

As soon as the loop ends, remember to add the last remaining prev to the list : out.add(prev)

you can create a boolean visited array or another variable in the interval class, remove items from the list
